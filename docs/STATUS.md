# Project Status

Single source of truth for progress and priorities. Pick the next task from
the top of the Queue.

**Status:** 🔲 ready · 🚫 blocked
**Size:**   S = one session/PR · M = 2–3 sessions · L = needs a plan doc under `docs/plan/`
**Labels:** `bug` `parser` `config` `feature` `tests` `docs` `infra`
**Next ID:** Q10

## Queue

| ID | Item | Labels | St | Sz | Notes |
|---|---|---|---|---|---|
| <a id="Q4"></a>Q4 | Add `reduce-foreground-guard-prompts` skill | `docs` | 🔲 | S | Model on workspace-guard's skill: run the friction report, map finding categories to fixes, offer a CLAUDE.md playbook. Has a no-report fallback, so not strictly blocked. |
| <a id="Q6"></a>Q6 | Assert hook script is executable in wiring test | `tests` | 🔲 | S | Wiring test checks the script exists but not that it is executable. Add an `os.access(script, os.X_OK)` assertion, per pr-sentinel's `test_wiring`. |
| <a id="Q7"></a>Q7 | Adopt the brand-image pipeline | `infra` `docs` | 🔲 | S | Adopt the sibling `docs/img` SVG-master → resvg pipeline (favicons, social-preview) + `docs/development/rendering-images.md`; swap the distinguishing glyph. |

## Deferred

| ID | Item | Labels | Sz | Trigger to revive |
|---|---|---|---|---|
| <a id="Q9"></a>Q9 | Stop-hook: detect stranded backgrounded wait | `feature` | M | **Decision:** foreground-guard grows completion-tracking — the agent backgrounds a wait per the guard's advice, then ends the turn without reading the task result. |
