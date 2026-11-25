# 11. Risks and open questions

## Risks

| Risk | Why it matters | Mitigation |
|------|----------------|------------|
| **Scope.** A simulated OS with 30 apps is a lot to build. | The project never finishes. | Build apps only as scenarios need them (see [roadmap](10_roadmap.md)). Every app starts as the smallest version that one scenario needs. Reuse one table/list/detail UI pattern across most apps. |
| **Cards feel bolted on.** | Players see a quiz, not an action, and the game becomes a flashcard app with a costume. | Paper-prototype framings in Phase 0. Keep framing lines short and specific. Measure in playtests whether players describe answering as "doing". |
| **Self-grading gets gamed.** | Weak scheduling, false sense of readiness. | No reward for high grades, cheap Again, calibration feedback, strict mode, and practice exams that are auto-scored. |
| **Exam drift.** | CompTIA revises the exam roughly every three years. | Concept ids, objectives file, and the revision process. Keep story scenarios about situations, not exam wording, so most survive a revision. |
| **Technical accuracy.** | Wrong facts teach wrong answers. | Every card cites a concept and a wiki page; technical review by someone who holds Security+; a "report a card" button that opens an issue. |
| **Too much reading.** | Logs, emails and docs are text-heavy. | Short logs with highlights after the first look, voiced key lines, visual dashboards, and a "summarize this" hint that costs a little time. |
| **Teaching attack techniques.** | Some players may want offensive detail. | Attacks are conceptual and stay inside a fictional range with rules of engagement. No working payloads for real systems. |
| **Trademark.** | "Security+" and "CompTIA" are CompTIA trademarks. | Use them only descriptively ("prepares you for the CompTIA Security+ exam"), no logos, and a disclaimer that the game is not affiliated with or endorsed by CompTIA. |
| **Load spikes.** | A scenario that adds 20 cards can create a review wall later. | New-card pacing tied to the daily allowance, previews for extra concepts, and the catch-up flow. |

## Open questions

1. **Art direction.** Top-down pixel art (cheap, readable, fits Godot) or clean vector illustration? Recommendation: top-down pixel art for the world and a clean flat style for the desktop OS, so the two modes feel different.
2. **Voice acting.** None, key lines only, or full? Recommendation: key lines only, for the cast's explanation lines after Again, because hearing the explanation helps memory.
3. **Single player only, or a classroom mode?** A teacher dashboard that shows class-wide mastery would help bootcamps. It needs a server, so it is out of scope for the first release.
4. **Price and distribution.** Free and open source like the other projects here, or paid? This affects whether to invest in voice and art.
5. **Should story outcomes ever depend on recall?** The design says no (only decisions and computer tasks matter). A "hardcore" setting could let Again cost more in crisis beats. Worth testing in Phase 0.
6. **How much real syntax in the shell?** Enough to transfer, but each real flag adds work. Proposed rule: support the flags that appear in common Security+ study material, and print a helpful note for others.
7. **Should the in-game OS mirror a real distribution's look?** Recommendation: no. Use a neutral, fictional look with real command names, to avoid trademark issues and to age well.
8. **Working title.** *Night Shift* is a placeholder.
