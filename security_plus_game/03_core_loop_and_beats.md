# 3. Core loop and scenario beats

## Three loops

| Loop | Length | What happens |
|------|--------|--------------|
| **Moment** | Seconds | Walk, inspect, answer a card, type a command, make a choice |
| **Shift** | 10 to 40 minutes | Clock in, clear due chores, play one story scenario (or a ticket in Free Shift), clock out with a shift report |
| **Campaign** | Weeks | Acts, client trust, the controls the player built, mastery growing across all 28 objectives |

## A shift, step by step

1. **Clock in at the SOC.** The shift board shows: due chores (review cards), the story scenario for today, and optional side tickets.
2. **Chores (due reviews).** Each due card is attached to a small task somewhere in the world: "verify last night's backup job" in the Lantern server room, "check the visitor log" in the lobby, "answer Femi's question about TLS" on the chat app. The player can walk to them or, to save time, open the **chore list** at their desk and do them in place. Walking is for flavor and is never required. See [due cards as chores](04_question_actions_and_scheduling.md#due-cards-as-world-chores).
3. **Story scenario.** A sequence of beats (below). New concepts are introduced here, so a scenario may add 5 to 15 new cards to the player's deck.
4. **Clock out.** The shift report shows: what happened, controls added to the controls register, cards learned and reviewed, mastery change by objective, client trust change, and a one-line preview of tomorrow.

The game stops offering new story when the due backlog is large (see [load management](04_question_actions_and_scheduling.md#load-management)). Players can always play side tickets.

## The six beat types

A scenario is a list of beats with branches. Every beat type can trigger cards and change world state.

### 1. Dialogue

Conversation with an NPC. Choices can be **knowledge-gated**: one option is only available as a card action ("Explain to Rosa why the backups need to be offline"). Dialogue is also how the game delivers short explanations after a card, always in a character's voice and never longer than three sentences.

### 2. Inspect

Walk up to something in the world and look at it: a door with a propped-open latch, an unlabelled USB stick in the parking lot, a server rack with a sticky note password, a camera pointed at a wall, an unescorted visitor. Inspecting may reveal a clue, start a card ("What kind of attack is this USB drop?"), or open a Place or Decision beat.

### 3. Place

Put a physical or logical thing in the right spot. Two views:

- **Floor plan view** for physical controls: place cameras, lighting, bollards, an access control vestibule, sensors (infrared, pressure, microwave, ultrasonic), fencing, guard posts. The game simulates sight lines and coverage and then runs a short intrusion attempt so the player sees what their placement did.
- **Network diagram view** for architecture: drag firewalls, IDS/IPS (inline vs tap), proxies, load balancers, jump servers, sensors, and draw security zones (screened subnet, internal, OT). The diagram is the same network the virtual computers live on, so placement here changes real behaviour in the simulation.

### 4. Computer

The character sits at a computer and the screen becomes the in-game OS. The player does a task with a checkable end state: write a firewall rule, find the beaconing host in NetFlow, revoke a certificate, disable a former employee's account, fix an SPF record. See [the virtual computer](05_virtual_computer.md). Computer beats are the game's version of the exam's performance-based questions.

### 5. Card action

The character is about to do something that rests on knowing a fact or a distinction. The game shows a card front, framed as the action:

> *The vendor's tech says the clinic's imaging PCs must keep running Windows 7 because the scanner software will not run on anything newer. You can't patch them. You write in the change request the kind of control you will put in place instead:*
> **Front:** A control used when the primary control cannot be implemented is called a ______ control.

The player recalls, flips (Space), sees the back (**compensating**), and grades themselves. The action then happens. See [question actions](04_question_actions_and_scheduling.md).

### 6. Decision

A choice with no single right answer on a card, where the outcome depends on trade-offs and on world state. Examples: accept, transfer, avoid or mitigate a risk; pay attention to a 2 a.m. alert or keep working the current incident; fail-open or fail-closed for a pump-station door lock; take the clinic's EHR offline to contain ransomware during clinic hours. Decisions update the risk register, client trust, and the controls register, and later scenarios read those.

## Beat example: "The USB in the parking lot" (Act 1, shift 3)

| # | Beat | Content | Concept |
|---|------|---------|---------|
| 1 | Inspect | Walt hands the player a USB stick labelled "Q3 Salaries" found in the Copperline lot. | 2.2 removable device |
| 2 | Card | "An attacker leaving infected drives where staff will find them uses which threat vector?" | 2.2 removable device / baiting |
| 3 | Decision | Plug it into your workstation, plug it into the lab sandbox, or bag it and log it. | 4.1 sandboxing |
| 4 | Computer (if sandbox) | In the lab sandbox, list the files, hash the executable (`sha256sum`), look up the hash in the threat feed app. | 1.4 hashing, 4.3 threat feeds |
| 5 | Card | "Malware that disguises itself as a legitimate file is a ______." | 2.4 trojan |
| 6 | Dialogue | Priya asks what control would have stopped it on a real workstation. Knowledge-gated option: "Disable autorun and block removable media through policy." | 2.5 hardening, 4.5 Group Policy |
| 7 | Computer | Set the removable media policy for Copperline's workstation group in the Group Policy editor. Checked: policy applied to the right OU. | 4.5 OS security |

If the player plugs it into their own workstation at step 3, the trojan runs, EDR quarantines it, Priya makes the player write the incident ticket, and the scenario continues with containment beats instead. Nothing is lost except a little trust and time, and the player has now seen EDR work (4.5).

## Failure and consequences

- **No hard fail state** in story scenarios. Bad outcomes cost client trust, add risks to the register, and change later scenarios.
- **Recoverable mistakes on the computer.** Most computer tasks allow retries. A few crisis tasks have a world clock (ransomware spreading each minute), and running out of time moves the story to the worse branch.
- **The "Again" path never blocks.** If the player grades Again on a card that gates an action, the character looks it up in the runbook (the back is shown with an explanation), some in-game time passes, and the action happens.
- **Replay.** Any completed scenario can be replayed from the case archive to try other branches. Replays introduce no new cards but do count as reviews if the cards are due.

## Pacing targets

| Element | Target |
|---------|--------|
| Cards answered per story scenario | 8 to 20 |
| Computer beats per story scenario | 1 to 3 |
| Longest stretch without player input in a cutscene or dialogue | 30 seconds |
| New cards per day (default) | 15, adjustable from 5 to 50 |
| Explanation text after a card | Three sentences or fewer, plus an optional "More" that opens the in-game wiki |
