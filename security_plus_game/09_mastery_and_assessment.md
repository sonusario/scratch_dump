# 9. Mastery, assessment and progression

## Concept mastery

Each concept's mastery is a number from 0 to 100 that combines three signals:

| Signal | Weight | Source |
|--------|--------|--------|
| **Recall** | 50% | Average predicted recall (FSRS retrievability) across the concept's cards right now, counting only cards the player has seen |
| **Application** | 35% | Best result on computer, place and decision beats that teach it (full goal = 100, partial = share of sub-goals, with hints reducing it by 10 each) |
| **Breadth** | 15% | Share of the concept's card variants and scenario contexts the player has met |

Concepts with no hands-on component use Recall 75% and Breadth 25%.

**Objective mastery** is the average of its concepts. **Domain mastery** is the average of its objectives. **Readiness** is domain mastery weighted by exam weight (12, 22, 18, 28, 20).

## The mastery map

A screen in the SOC (Priya's whiteboard) shows:

- Five domain bars with readiness and exam weight.
- Each objective as a tile, colored by mastery band (with the number and an icon, not color alone).
- Click an objective to see its concepts, cards due soon, weakest concept, and a **"practice this"** button that starts a side ticket or a remedial mini-scenario for it.
- Calibration score (see [scheduling](04_question_actions_and_scheduling.md#why-the-player-can-be-trusted-to-grade)).
- A forecast: due reviews per day for the next 14 days.

## Practice exams

Available from the SOC after Act 1. They are **separate from the story** and do not change world state.

| Mode | Contents |
|------|----------|
| **Quick quiz** | 10 choice cards weighted to the player's weakest objectives |
| **Domain drill** | 25 questions from one domain |
| **Full practice exam** | Up to 90 questions in 90 minutes, weighted by exam domain percentages, including 3 to 5 performance-based tasks run in the in-game computer |
| **PBQ only** | A set of 5 performance-based tasks |

Exam answers are auto-scored (no self-grading, since this is a test). After the exam, the player can send missed items to the review deck. Questions answered in an exam count as `exam` context in the review log and do not move the schedule unless the player chooses "Add to reviews".

**Score display:** a scaled 100 to 900 estimate (the real exam passes at 750) with a clear note that it is an estimate, not CompTIA's scoring.

## Performance-based questions

The exam's PBQs are hands-on simulations. The game's computer and place beats are designed to look like them. The PBQ pool includes, at least:

1. Order firewall rules to allow and deny listed traffic (4.5).
2. Match attack descriptions to log excerpts (2.4).
3. Place controls on a network diagram (3.2).
4. Classify controls by category and type (1.1).
5. Order incident response steps or order of volatility (4.8).
6. Choose secure protocols and ports for listed services (4.5).
7. Configure wireless security for an enterprise (4.1).
8. Read a certificate and identify its problem (1.4).
9. Calculate SLE, ARO and ALE (5.2).
10. Pick the data source for each investigation question (4.9).
11. Configure an IAM policy that meets stated access rules (4.6).
12. Identify social engineering in messages (2.2, 5.6).

## Progression and unlocks

Progression comes from the story, not from grinding. Unlocks are mostly **tools and access** that match the character's growing job:

| Unlock | When |
|--------|------|
| Lab sandbox | S03 |
| Directory Admin and GPO | S03 |
| Packet Viewer, Flow Viewer | S17 to S19 |
| Firewall Manager write access (before: read-only) | S09 |
| Cloud Console | S12 |
| Forensics Kit | S21 |
| PAM Vault | S31 |
| Automation Studio | S12, full features after T17 |
| Free Shift mode | After S40, or after 30 shifts for players who want it earlier |
| Job title (Analyst I → II → Senior → Lead) | End of each act |

Cosmetics (desk items, SOC wall art, character outfits) are earned from streaks and chores but never affect study.

## Streaks without guilt

- A **shift streak** counts days with at least one chore round done.
- **Leave days:** the player gets one free leave day per week that keeps the streak.
- Breaking a streak shows nothing negative; the next shift says "Welcome back" and offers the catch-up flow.
