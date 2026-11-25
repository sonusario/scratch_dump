# 1. Vision and pillars

## Who it is for

1. **Primary:** someone studying for Security+ who has 20 to 60 minutes a day and wants study time that does not feel like a stack of flashcards. They may have no IT job yet, so many concepts (a SIEM, a jump server, a CSR) are words they have never seen in use.
2. **Secondary:** people who already passed and want to keep the knowledge fresh, and teachers or bootcamps who want a lab-like activity that needs no real lab.

## What "teaches every concept" means

The game is finished only when all three of these are true for every concept in the SY0-701 objectives:

1. **Encountered in context.** The concept shows up in at least one scenario where it matters to what happens next. A player who never reads a glossary still meets it.
2. **Practiced by recall.** At least one card asks for it, and the scheduler brings that card back until the player knows it.
3. **Applied.** For "given a scenario" objectives (2.4, 3.2, 4.1, 4.5, 4.6, 4.9, 5.6) and anything that can be done on a computer, the player does it, in the in-game OS or in the world, and the game checks the result, not only an answer.

The [coverage check](07_content_model_and_pipeline.md#coverage-check) enforces this. A concept tagged in the objective map with no card, or with no scenario, fails the build.

## Design pillars

1. **Do it, don't read about it.** If a concept is a thing someone does (writes a firewall rule, revokes a certificate, places a sensor), the player does it. If it is a thing someone decides (accept or transfer a risk), the player decides and sees what follows. If it is a fact (port 636 is LDAPS), it becomes a card that is the key to an action.
2. **Every answer moves the world.** A card is never a quiz screen bolted on. Each card is framed as what the character is about to do: "You reach for the right tool to stop the badge cloner from working on this reader. What is it?" Recalling the answer is doing the action.
3. **Honest self-grading costs nothing.** Grading yourself "Again" never blocks progress or loses the scenario. It costs a little in-game time (your character checks the runbook) and brings the card back soon. Lying to yourself earns nothing but a weaker review schedule. See [scheduling](04_question_actions_and_scheduling.md#why-the-player-can-be-trusted-to-grade).
4. **Consequences, not game-overs.** Wrong decisions in scenarios play out: the ransomware spreads to another VLAN, the auditor writes a finding, the client's trust meter drops. The player recovers in later scenarios. Nobody restarts a level because they forgot what MTBF means.
5. **Small world, deep systems.** Five client sites and one office, reused across many scenarios, rather than many shallow maps. The same server room gets hardened, audited, broken into, recovered and decommissioned over the campaign, so the player sees the life cycle.
6. **Exam-faithful, not exam-shaped.** Terms, definitions and distinctions match the exam (CompTIA's meaning of "compensating control" wins over any other). The game also includes exam-style practice so players can see readiness, but the main experience is a story.

## What the game is not

- **Not a hacking simulator.** The player is on the defending side (blue team) for most of the game. Offensive concepts (reconnaissance, privilege escalation, injection) appear when the player reviews an attack, runs an authorized penetration test in a scoped engagement, or watches a red-team NPC. Commands and payloads are simplified and stay inside the simulation. The game never teaches how to attack real systems beyond what the exam objectives describe at a conceptual level.
- **Not a real VM.** The in-game computer is a simulation built for teaching. It looks and behaves enough like Linux and Windows that skills transfer, without the cost and risk of real virtual machines. See [the virtual computer](05_virtual_computer.md#why-a-simulation-and-not-real-vms).
- **Not a replacement for the official objectives.** The game links to them and tracks coverage against them.

## Success measures

| Measure | Target |
|---------|--------|
| Concepts with at least one scenario, one card and (where applicable) one checked task | 100% |
| Players who finish the campaign and say they felt ready for the exam (survey) | Above 70% |
| Retention: average recall on cards 30 days after first seen, for players who keep a daily habit | Above 85% |
| Calibration: gap between self-grade and checked answers on objective cards | Under 10 percentage points after the first 2 weeks |
| Daily session length for the median player | 20 to 40 minutes |
