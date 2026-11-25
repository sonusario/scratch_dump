# 10. Roadmap

Sizes assume one or two developers working part time with occasional help on art and writing. They are rough and are mainly useful for comparing phases.

## Phase 0: Paper prototype (2 to 3 weeks)

Goal: check that cards-as-actions and self-grading feel good before building anything.

- Run S03 (USB in the parking lot) and S09 (Segment the Plant) as a tabletop with printed cards, a printed network diagram, and a person playing the "computer" by answering commands from a script.
- Try three framings for card actions and pick the one testers like best.
- Measure: do testers grade honestly when Again has only a time cost?

## Phase 1: Core systems (2 to 3 months)

- Scheduler (FSRS with SM-2 and Leitner fallbacks) with unit tests.
- Card service, action slots, siblings, chores at the desk only.
- Simulation core: world model, event bus, shell with 30 commands, Files, Mail, SIEM with basic queries, Firewall Manager.
- Scenario runner with all six beat types (place view can start with the network diagram only).
- Content pipeline, coverage check, expert replay CI.
- Import of flashcard_app's Short Answer deck with concept tagging review.

## Phase 2: Vertical slice (2 months)

Act 1 complete (S01 to S06) plus S09, at final quality, on desktop.

- Covers all of Domain 1 and parts of Domains 2, 3, 4 and 5.
- About 250 original cards plus imported extras.
- Playtest with 10 to 20 people. Go/no-go on the full build based on fun, learning (pre/post quiz on Domain 1), and calibration data.

## Phase 3: Content production (6 to 9 months)

Acts 2 to 5, all side tickets, all apps.

| Act | Scenarios | New apps needed |
|-----|-----------|-----------------|
| 2 | S07 to S15 | Cloud Console, MDM, Wireless Planner, Config Auditor, Asset Inventory, floor plan Place view |
| 3 | S16 to S24 | Packet Viewer, Flow Viewer, EDR, Forensics Kit, Backup Manager |
| 4 | S25 to S33 | Vuln Scanner, Docs templates (risk register, BIA, agreements), PAM Vault, Certificate Manager CA admin |
| 5 | S34 to S40 | SCADA HMI, Automation Studio full |

Content budget: about 1,000 original cards (two to four per concept across roughly 350 concepts), 40 story scenarios, 20 ticket templates, about 60 machines, 6 site maps.

## Phase 4: Free Shift, practice exams, polish (2 months)

- Free Shift generator from ticket templates and attacker scripts.
- Practice exams and the PBQ pool.
- Phone chore mode, web export, accessibility pass, localization hooks.

## Phase 5: Release and upkeep

- Release on desktop and web.
- Watch for a new Security+ version and run the [exam revision process](07_content_model_and_pipeline.md#exam-revisions).
- Collect anonymous, opt-in learning data (recall by concept) to find cards that are confusing.

## First week of real work, if this goes ahead

1. Write `content/objectives/sy0-701.yaml` with every concept id from the [objective map](objective_map/README.md).
2. Write the coverage script so progress is measurable from day one.
3. Port FSRS to GDScript with tests.
4. Build the shell with `ls`, `cat`, `sha256sum`, `ss` and the goal evaluator, and make S03's computer beat pass its expert replay.
