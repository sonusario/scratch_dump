# 4. Question actions and spaced repetition

This is the system that makes the game a study tool. It has four parts: **cards**, **actions** that cards unlock, the **scheduler**, and **chores** that bring due cards back into the world.

## Cards

A card is a front (prompt) and a back (answer), tagged to one or more objective concepts. Fronts are written so they can be read as the character's next action; a plain version is kept for exam-style review.

### Card kinds

| Kind | Front | How it is answered | Checked by the game? |
|------|-------|--------------------|----------------------|
| **Basic** | A question | Recall, flip, self-grade | No |
| **Cloze** | A sentence with a blank | Recall, flip, self-grade | No |
| **Reversed pair** | Term to definition and definition to term (two cards) | Recall, flip, self-grade | No |
| **Typed** | A question with a short answer (a port number, an acronym) | Type, then flip | Yes, fuzzy match, shown as a hint |
| **Choice** | Exam-style multiple choice (one or several answers) | Pick, then flip | Yes, shown as a hint |
| **Order** | Steps to put in order (incident response phases, order of volatility) | Drag, then flip | Yes, shown as a hint |
| **Match** | Pairs to connect (port to protocol, control to type) | Connect, then flip | Yes, shown as a hint |
| **Hotspot** | An image or diagram: click the thing (the on-path device, the place for the IPS) | Click, then flip | Yes, shown as a hint |

**The player always grades.** Even on a checked card, the check result is shown as a suggested grade, and the player chooses the final one. This follows the request that players can grade themselves, and it also lets a player say "I guessed right" (grade Hard or Again even though the pick was correct).

### Variants

Each concept should have two to four cards with different wording, plus the same idea in at least two kinds (for example a basic card and a choice card). The scheduler treats variants of one concept as **siblings**: only one sibling is shown per day, so the player cannot answer from the wording of the card they saw five minutes ago.

## Cards as actions

### Action slots

A scenario beat never names one fixed card. It names an **action slot**:

```yaml
action_slot:
  concept: 1.1.control_type.compensating
  framing: "You write in the change request the kind of control you'll put in place instead."
  on_any_grade: set_flag(imaging_pcs_compensating_control)
```

When the beat runs, the game picks a card for that concept:

1. If the player has never seen the concept, pick its **intro card** (the simplest wording) and add it to the deck as a new card.
2. Otherwise, pick the sibling with the lowest predicted recall right now (it benefits most from a review).
3. If a sibling was already reviewed today, use it anyway but mark this review as **in-context practice**: it is logged but does not move the schedule. That keeps story play from distorting the scheduler.

### Framing

The framing line is spoken or written by the character, then the card front appears in a card frame on top of the scene. Fronts stay faithful to the exam, so the same card works in story mode, chore mode and practice exams.

### What the grade does

| Grade | Key | Scheduler | In the world |
|-------|-----|-----------|--------------|
| **Again** | 1 | Lapse: short relearning step (10 minutes, then 1 day) | The character checks the runbook. The back is shown with a short explanation in a cast member's voice. 5 in-game minutes pass. The action happens. |
| **Hard** | 2 | Interval grows a little | The action happens, with a hesitant animation and line |
| **Good** | 3 | Normal growth | The action happens |
| **Easy** | 4 | Larger growth | The action happens, sometimes with a bonus line from an NPC who noticed |

A **two-button mode** (Again and Good only) is available for players who prefer it, and it matches flashcard_app's "Didn't get it." and "Got it!" buttons.

### Why the player can be trusted to grade

The design removes every reason to grade dishonestly:

1. **No reward for a high grade.** The story outcome never depends on the grade. Outcomes depend on **decisions** and **computer tasks**, which are checked by the game.
2. **"Again" is cheap.** It costs a few in-game minutes and a short explanation, never trust or progress. In a timed crisis, the runbook lookup costs world-clock time, which is the only place a grade has a cost, and the cost is small (see below).
3. **Calibration feedback.** On checked cards the game logs both the check result and the self-grade. The mastery screen shows a **calibration score**: how often "Good/Easy" matched a correct pick and "Again" matched a wrong one. It is shown as information, never as a penalty. Most people over-grade at first and learn quickly once they see it.
4. **Optional strict mode.** For players who want it, strict mode uses the check result as the grade for checked cards.

**Timed crises.** During a timed beat (ransomware spreading), Again costs 20 seconds of world clock. Hard, Good and Easy cost nothing. Twenty seconds is small enough that it never decides the outcome by itself, but it gives the moment some tension.

## The scheduler

### Recommendation: FSRS

Use **FSRS** (Free Spaced Repetition Scheduler), the open-source scheduler that Anki has offered since 23.10. It models each card's **stability** (how long until recall drops to 90%) and **difficulty**, and schedules the next review for when predicted recall falls to the player's **desired retention** (default 90%). Reasons:

- It needs fewer reviews than SM-2 for the same retention in published benchmarks.
- It handles overdue cards well, which matters for a game people put down for a week.
- It gives a **predicted recall** for every card at any moment, which the game uses for action slots, chore placement and the mastery map.
- Open implementations exist in several languages (including Python, Rust, TypeScript and Go), and porting the core formulas to GDScript is about 200 lines.

Fallbacks, chosen in settings:

| Scheduler | When to use |
|-----------|-------------|
| FSRS (default) | Everyone |
| SM-2 (Anki's classic algorithm) | Players who want predictable, familiar intervals |
| Leitner, golden-ratio levels (1, 2, 3, 4, 7, 11, 18… days) | Matches flashcard_app, for players moving progress between the two |

### Settings

| Setting | Default | Range |
|---------|---------|-------|
| Desired retention | 0.90 | 0.80 to 0.97 |
| New cards per day | 15 | 5 to 50 |
| Maximum reviews per day before story is soft-gated | 150 | 50 to unlimited |
| Learning steps | 1 m, 10 m | Editable |
| Relearning steps | 10 m | Editable |
| Leech threshold | 6 lapses | 4 to 12 |
| Interval fuzz | On | On / off |
| Exam date | None | When set, the game raises desired retention as the date nears and makes sure every concept is introduced at least 14 days before it |

### Exam date mode

If the player sets an exam date, the planner works backwards: it counts the concepts not yet introduced, divides them by the days left minus 14, and raises the daily new-card count if needed. It warns when the pace would mean more than 60 minutes a day.

### Leeches

A card with 6 lapses becomes a **leech**. The game does not just suspend it. It offers:

1. A **remedial mini-scenario** for that concept (one to three beats from the scenario template library) so the player sees it in a new context.
2. A **mnemonic or comparison card** (for example, "Pressure, microwave, infrared, ultrasonic: what each sensor detects"), if one exists.
3. An option to **edit the card** in place (borrowed from flashcard_app's Edit during review), so the player can reword it in a way that sticks.

## Due cards as world chores

The scheduler decides **when** a card is due. The chore system decides **where** it shows up.

### Chore templates

Each concept tag maps to one or more chore templates, which name a location and a framing:

| Tag | Location | Chore framing |
|-----|----------|---------------|
| `backups`, `resilience` | Lantern server room, backup appliance | "Verify last night's backup job before you sign the log." |
| `physical` | Lobby, parking lot, client sites | "Walt asks you to walk the perimeter with him." |
| `crypto`, `pki` | Your desk, certificate manager app | "A cert renewal request needs a sanity check." |
| `governance`, `policy` | Conference room | "Marcus wants a quick answer before the board call." |
| `threat-actors`, `indicators` | SOC wall | "Priya points at an alert on the wall." |
| any | Your desk, chat app | "A message from a client lands in your chat." |

The chore board groups due cards into **rounds** of five to ten by location, so the player can walk one loop. A **"do all at desk"** button turns every chore into a plain review session with the framing line on each card, for players who just want to study.

### Due-card ordering

Within a round, cards are interleaved across objectives (never five cards from one objective in a row) and siblings are buried. Overdue cards with the lowest predicted recall go first.

## Load management

- **Soft gate:** when the due count is above the daily maximum, the shift board shows "Clear chores first" and the story scenario button is dimmed but still clickable (with a warning that it adds new cards).
- **New cards are paced by story:** a scenario that would add more cards than today's new-card allowance holds its extra intro cards for later shifts. Those concepts still appear in the story, and their action slots use a **preview** (the card is shown once as a runbook page and becomes a new card on a later day).
- **Back from a break:** after 7 or more days away, the game offers a **catch-up shift**: a short story beat ("You're back from leave, here's what you missed") and a capped review session, so the player is not met with 600 due cards at once.

## Logged per review

| Field | Why |
|-------|-----|
| Card id, concept tags | Scheduling, mastery |
| Timestamp, response time | FSRS, speed tracking |
| Self-grade | FSRS |
| Check result (checked cards) | Calibration |
| Context (`chore`, `story`, `in-context-practice`, `exam`, `remedial`) | Only `chore`, `story` and `remedial` move the schedule by default |
| Scheduler state before and after | Debugging, export |

Review logs export in Anki's revlog shape so a player's history can be loaded into Anki's FSRS optimizer to fit personal parameters, and the fitted parameters can be imported back.
