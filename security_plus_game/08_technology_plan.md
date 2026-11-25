# 8. Technology plan

## Engine: Godot 4 (recommended)

| Option | For | Against |
|--------|-----|---------|
| **Godot 4** (recommended) | Free and open source; strong 2D; good UI system (needed for the many apps); exports to Windows, macOS, Linux, Android, iOS and the web; GDScript is easy to learn; the [Godot idle-game tutorial](https://github.com/sonusario/build_your_own_idle_game_in_godot) in this project already teaches it | Web export is heavier than a native web app; text rendering of large logs needs care |
| Web (TypeScript + a canvas/WebGL library) | Best for a browser-first PWA like the other apps in this project; easy text-heavy UI | Building a walkable world and tooling from scratch is more work |
| Unity | Mature, big ecosystem | Licensing history, heavier, nothing in this project uses it |

**Recommendation:** Godot 4 for the game, with the simulation core written so it has no Godot dependencies (pure GDScript classes, or C# if performance needs it), so it can be unit-tested headlessly and, later, reused in a web version.

## Architecture

```
┌──────────────────────────────────────────────────────────────┐
│                         Presentation                          │
│  World scenes (top-down 2D)  │  Desktop/OS UI  │  Card overlay │
│  Floor plan & diagram views  │  Docs/Forms     │  Menus, HUD   │
└───────────────▲──────────────┴────────▲────────┴───────▲──────┘
                │                       │                │
┌───────────────┴───────────────────────┴────────────────┴──────┐
│                         Game services                          │
│  Scenario runner (beats, branches, flags)                      │
│  Card service (action slots, variants, siblings)               │
│  Scheduler (FSRS / SM-2 / Leitner behind one interface)        │
│  Chore placer   │  Mastery & coverage   │  Registers (controls, │
│  Dialogue       │  Save/load, export    │  risk, evidence)      │
└───────────────▲────────────────────────────────────────────────┘
                │
┌───────────────┴────────────────────────────────────────────────┐
│                Simulation core (no engine dependency)           │
│  World network model │ Event bus │ Log generators │ Shells      │
│  App back ends (firewall, SIEM query engine, PKI, IAM, cloud)   │
│  Attacker and NPC scripts │ Goal predicate evaluator │ Sim clock │
└─────────────────────────────────────────────────────────────────┘
```

### Key components

- **Scenario runner:** loads scenario YAML, runs beats, evaluates conditions against flags and registers, and hands beats to the right view.
- **Scheduler interface:** `schedule(card_state, grade, now) -> card_state` and `retrievability(card_state, now) -> float`. FSRS, SM-2 and Leitner implement it. Unit tests check FSRS against reference values from the open-source FSRS implementations.
- **Shell:** a tokenizer and command table. Each command is a function over the world model that returns text and emits events. Commands share a small flag parser so `--help` and errors look consistent.
- **SIEM query engine:** a tiny query language (`source=auth action=fail | stats count by user`) over the event store, enough to teach filtering, counting, time ranges and correlation.
- **Packet model:** packets are generated from events with realistic header fields; payloads are synthetic. The viewer supports display filters like `ip.addr==10.0.0.5 && tcp.port==443`.
- **Goal evaluator:** predicates in YAML compile to functions over the world model.

## Save data

- One save file per profile: world state (registers, flags, trust, completed scenarios), the card collection, scheduler state per card, and the review log.
- JSON, compressed. Autosave at the end of each beat and at clock-out.
- **Backup and restore** to a single file (like flashcard_app's Back Up…), and optional sync through a user-chosen folder (no game-run server needed).
- Review log export in Anki's revlog shape; deck export as `.apkg`.

## Platforms and input

| Platform | Notes |
|----------|-------|
| Windows, macOS, Linux | Primary. Keyboard needed for the terminal. |
| Web | Godot web export, installable as a PWA if hosted on the Pages hub (follow this project's same-origin PWA rules: unique manifest id and scope, cache names prefixed by app). |
| Android / iOS tablets | Supported with on-screen keyboard and a command palette that builds commands from taps. |
| Phones | **Chore mode only** at first: reviews with framing, no world or desktop. Syncs with the main save. |

## Accessibility

- Full keyboard play; every world interaction reachable from a list as well as by walking.
- Screen reader labels on all UI (Godot 4's accessibility support plus text alternatives for the floor plan and diagram views, which list placed items and coverage in text).
- Font size and dyslexia-friendly font options; high-contrast theme; no information carried by color alone (alerts have icons and text).
- No time pressure outside optional crisis beats, and an "untimed" setting that removes it.
- Reduced motion setting.

## Testing

- Unit tests for the scheduler, shell commands, goal predicates and SIEM queries.
- **Expert replay CI:** every computer beat's recorded solution must reach its goal.
- **Coverage CI:** see [coverage check](07_content_model_and_pipeline.md#coverage-check).
- **Playtests** with people at three levels: no IT background, IT but no security, and recent Security+ passers.
