# 7. Content model and authoring pipeline

All game content is plain text files in the repository (YAML for structure, Markdown for prose), so it can be reviewed in pull requests, diffed, and checked by scripts. The engine loads them at startup.

## Folder layout

```
content/
├── objectives/sy0-701.yaml          # The 28 objectives and every concept id (source of truth for coverage)
├── cards/
│   ├── d1/1.1_controls.yaml         # Cards grouped by objective
│   ├── …
│   └── imported/                     # Cards converted from flashcard_app decks
├── scenarios/
│   ├── act1/S01_first_night.yaml
│   └── tickets/T01_phish_triage.yaml
├── machines/                         # Host definitions for the virtual computer
│   └── brightwater/jump-01.yaml
├── networks/                         # Site network diagrams
├── chores/chore_templates.yaml
├── dialogue/                         # Character lines, keyed by id
└── wiki/                             # In-game reference pages (Markdown), one per concept
```

## Objectives file

```yaml
- id: "1.1"
  title: Compare and contrast various types of security controls.
  domain: 1
  concepts:
    - id: 1.1.category.technical
      label: Technical
    - id: 1.1.control_type.compensating
      label: Compensating
```

## Card format

```yaml
- id: c.1.1.compensating.a
  concept: 1.1.control_type.compensating
  also: [4.3.response.compensating_controls]     # other concepts this card helps
  kind: cloze                                     # basic | cloze | typed | choice | order | match | hotspot
  intro: true                                     # the variant used when the concept is first met
  front: "A control used when the primary control cannot be implemented is called a {{c1::compensating}} control."
  back_extra: "Example: isolating an unpatchable PC on its own VLAN."
  explain:
    speaker: priya
    text: "If you can't do the thing the standard asks for, you do something else that gets you close. That's compensating."
  wiki: wiki/1.1_compensating.md
  source: original                                 # original | flashcard_app:Combined | flashcard_app:ShortAnswer | …
```

Rules:

- Every card has exactly one main `concept` and may list others in `also`.
- Backs are one sentence or less (the same rule as flashcard_app's Short Answer deck). Detail goes in `back_extra` and `wiki`.
- `explain.text` is three sentences or fewer.
- Choice cards list `choices` and `correct`; Order cards list `items` in the correct order; Match cards list `pairs`; Hotspot cards name an image and a target region.

## Scenario format

```yaml
id: S03
title: The USB in the Parking Lot
act: 1
client: copperline
prereqs: [S02]
introduces: [2.2.removable_device, 2.4.malware.trojan, 4.1.sandboxing, 1.4.hashing, 4.5.os_security.group_policy]
beats:
  - id: b1
    type: inspect
    target: copperline/parking_lot/usb_stick
    dialogue: walt.found_usb
  - id: b2
    type: card
    slot: { concept: 2.2.removable_device, framing: "Walt waits. 'So what is this, exactly?'" }
  - id: b3
    type: decision
    options:
      - { id: own_pc,  label: "Plug it into your workstation", goto: b3a }
      - { id: sandbox, label: "Take it to the lab sandbox",     goto: b4 }
      - { id: bag,     label: "Bag it and log it",              goto: b6, set: { trust.copperline: +1 } }
  - id: b4
    type: computer
    machine: lantern/lab-sandbox-01
    goal:
      all:
        - player_ran_hash_on("E:/Q3_Salaries.exe")
        - threat_feed_lookup_done(hash_of: "E:/Q3_Salaries.exe")
    hints:
      - "Look at what's on the drive first."
      - "The Files app or `ls` will show it. Then hash the .exe."
      - "Run: sha256sum /mnt/usb/Q3_Salaries.exe, then paste the hash into Threat Feed."
  # …
outcomes:
  registers:
    controls: [{ id: copperline.gpo.removable_media, category: technical, type: preventive }]
```

## Machine format

```yaml
id: brightwater/jump-01
os: linux
site: brightwater
interfaces: [{ ip: 10.20.0.5, vlan: mgmt }, { ip: 10.30.0.5, vlan: ot }]
users:
  - { name: hank, groups: [operators], mfa: totp }
services:
  - { name: sshd, port: 22, version: "OpenSSH 9.6" }
files:
  - { path: /etc/motd, content: "Authorized use only." }
logs:
  auth: generated                 # filled by the event bus
```

## Tagging and coverage

### Coverage check

A build script (`tools/coverage.py`) reads `objectives/sy0-701.yaml` and every card and scenario, then fails the build if any concept lacks:

1. at least one card with that `concept`,
2. at least one scenario that `introduces` it, and
3. for concepts flagged `hands_on: true` in the objectives file, at least one `computer` or `place` beat whose `teaches` list names it.

It also writes a coverage report (Markdown table: concept, cards, scenarios, hands-on beats) that is committed with each content change, so the [objective map](objective_map/README.md) can be checked against what is actually built.

### Exam revisions

When CompTIA publishes a new exam version, a new `objectives/<exam>.yaml` is added with a mapping file from old concept ids to new ones. The coverage script then lists concepts that are new and have no content, and concepts that were dropped (whose cards can be retired or kept as general knowledge).

## Reusing the existing Security+ decks

flashcard_app holds three SY0-701 Anki decks: Combined (5,613 cards in eight sub-decks: the five domains, Ports and Protocols, Key Terms, Acronyms), Short Answer (same cards, one-sentence backs), and Three-Word Answers (3,880 cards, backs of three words or fewer).

The import tool (`tools/import_apkg.py`) would:

1. Read the `.apkg` (SQLite inside a zip; flashcard_app's own importer already handles current and older Anki formats and Zstandard compression, and the same logic can be ported).
2. Prefer the **Short Answer** deck, because its backs already meet the one-sentence rule above.
3. Suggest a `concept` for each card by matching its sub-deck (domain) and keywords against concept labels, and write the suggestion to a review file. A person confirms or fixes each suggestion before the card enters `cards/imported/`.
4. Mark cards whose concept already has two or more original variants as `extra: true`. Extra cards are used in Free Shift and practice exams but are not required for coverage.
5. Keep `source:` on every imported card so the import can be re-run if the decks change.

The game also **exports** a player's deck back to `.apkg`, with review history, so a player can continue in Anki or flashcard_app on a phone.

## Authoring workflow

1. Pick a concept with low coverage from the coverage report.
2. Write two to four cards and the wiki page.
3. Attach the concept to a scenario beat (existing or new) with an action slot.
4. If it is hands-on, add or extend a machine and a goal predicate.
5. Run the coverage check and the scenario linter (beats reachable, goals satisfiable by the expert solution, every `goto` exists).
6. Run the **expert solution replay**: each computer beat has a recorded solution that the CI runs against the simulation to prove the goal can be reached.

## Writing rules

- Use CompTIA's terms and definitions. When a term has a different everyday meaning, the card follows CompTIA and the wiki page notes the difference.
- All organizations, people, domains and products are fictional. Fake domains use `.example`.
- No working exploit code. Attack examples are the same textbook stand-ins found in study guides.
- Card fronts read naturally as an action in at least one scenario. If a fact cannot be framed as an action, it can still be a chore card.
