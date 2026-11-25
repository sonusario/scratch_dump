# Night Shift: a game that teaches every Security+ concept

Design plans for a game that teaches all of CompTIA Security+ (exam **SY0-701**) by having the player live through the situations each concept is about. This folder holds plans only. There is no code yet.

*Night Shift* is a working title.

## The idea in one paragraph

You are a new analyst at a small managed security provider that looks after five very different clients. You walk around their offices, server rooms, loading docks and parking lots. When the work is on a computer, your character sits down at that computer and you use a simulated operating system: a shell, a mail client, a SIEM, a firewall console, a cloud console. When the work is knowledge (choosing the right control, naming the attack, picking the cipher), your character does it by **answering a question**. That question is the front of a flashcard. You recall the answer, flip the card, and **grade yourself** (Again, Hard, Good, Easy). The grade sets when the card comes back, Anki-style, and the action still happens either way. Cards that are due come back as chores in the world (a backup check, a badge audit, a patch window), so reviewing is part of the job and not a separate menu.

## Documents

Read them in order the first time.

| # | Document | What it covers |
|---|----------|----------------|
| 1 | [Vision and pillars](01_vision_and_pillars.md) | Who it is for, what "teaches every concept" means, design pillars, what the game is not |
| 2 | [World, cast and campaign](02_world_cast_and_campaign.md) | The provider, the five clients, the cast, the campaign arc and how it spans all five domains |
| 3 | [Core loop and scenario beats](03_core_loop_and_beats.md) | Shift structure, the six beat types, consequences, failure, pacing |
| 4 | [Question actions and spaced repetition](04_question_actions_and_scheduling.md) | Cards as actions, self-grading, the scheduler, due cards as world chores, honesty and calibration |
| 5 | [The in-game computer (LanternOS)](05_virtual_computer.md) | The simulated OS, network model, the apps, command set, how tasks are checked |
| 6 | [Objective-to-scenario map](objective_map/README.md) | Every SY0-701 objective and sub-concept mapped to scenarios, mechanics and cards |
| 7 | [Content model and authoring pipeline](07_content_model_and_pipeline.md) | Card, scenario and machine file formats, tagging, coverage checks, reuse of existing decks |
| 8 | [Technology plan](08_technology_plan.md) | Engine choice, architecture, save data, platforms, accessibility |
| 9 | [Mastery, assessment and progression](09_mastery_and_assessment.md) | How the game knows what you know, practice exams, performance-based questions, unlocks |
| 10 | [Roadmap](10_roadmap.md) | Vertical slice, milestones, content budget |
| 11 | [Risks and open questions](11_risks_and_open_questions.md) | What could go wrong and the decisions still open |

## The objective map

| Domain | Exam weight | File | Objectives |
|--------|-------------|------|------------|
| 1. General Security Concepts | 12% | [domain_1_general_security_concepts.md](objective_map/domain_1_general_security_concepts.md) | 1.1 to 1.4 |
| 2. Threats, Vulnerabilities, and Mitigations | 22% | [domain_2_threats_vulnerabilities_mitigations.md](objective_map/domain_2_threats_vulnerabilities_mitigations.md) | 2.1 to 2.5 |
| 3. Security Architecture | 18% | [domain_3_security_architecture.md](objective_map/domain_3_security_architecture.md) | 3.1 to 3.4 |
| 4. Security Operations | 28% | [domain_4_security_operations.md](objective_map/domain_4_security_operations.md) | 4.1 to 4.9 |
| 5. Security Program Management and Oversight | 20% | [domain_5_program_management_oversight.md](objective_map/domain_5_program_management_oversight.md) | 5.1 to 5.6 |

All 28 objectives are mapped, down to each concept CompTIA lists under them. The [acronyms, ports and protocols appendix](objective_map/appendix_acronyms_ports_protocols.md) covers the exam's acronym list, which is not tied to one objective.

## Related work in this project

- [flashcard_app](https://github.com/sonusario/flashcard_app) already holds three SY0-701 decks (Combined, Short Answer, Three-Word Answers) and a Leitner scheduler. The game can import those decks as its starting card pool. See [Content model](07_content_model_and_pipeline.md#reusing-the-existing-security-decks).
- [build_your_own_idle_game_in_godot](https://github.com/sonusario/build_your_own_idle_game_in_godot) is a Godot 4 tutorial. Godot 4 is the recommended engine here too, so the same skills carry over. See [Technology plan](08_technology_plan.md).

Neither is a dependency. The plan stands on its own.

## A note on the exam outline

The objective wording here follows the public CompTIA Security+ SY0-701 exam objectives (version 1.0 era, five domains, 28 objectives). CompTIA's own PDF is the source of truth. If CompTIA publishes a revision (SY0-801 or similar), the [coverage check](07_content_model_and_pipeline.md#coverage-check) is how the game finds the gaps.
