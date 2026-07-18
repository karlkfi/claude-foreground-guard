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
| <a id="Q1"></a>Q1 | Fix over-arming heredoc stripper | `bug` `parser` | 🔲 | S | Regex stripper over-arms on quoted `<<` and arithmetic `$((a<<b))`, dropping later lines and hiding a following poll. Port workspace-guard's quote/arith-aware stripper; add regression tests. |
| <a id="Q2"></a>Q2 | Add `exempt_watch_patterns` config allowlist | `config` `feature` | 🔲 | S | Config is add-only; no way to quiet a built-in watch pattern that false-positives short of disabling all of Class A. Add an allowlist, mirroring prod-guard's `classify()` suppression precedence. |
| <a id="Q3"></a>Q3 | Add friction-report command + script | `feature` `tests` | 🔲 | S | Fork prod-guard's `friction-report.py` + `commands/friction-report.md`; map finding signatures to categories, retarget extraction to backtick-wrapped commands. Adapt sibling tests. |
| <a id="Q4"></a>Q4 | Add `reduce-foreground-guard-prompts` skill | `docs` | 🔲 | S | Model on workspace-guard's skill: run the friction report, map finding categories to fixes, offer a CLAUDE.md playbook. Pairs with [Q3](#Q3); has a no-report fallback, so not strictly blocked. |
| <a id="Q5"></a>Q5 | Echo the override reason string | `feature` | 🔲 | S | `FOREGROUND_GUARD_OVERRIDE` reason is captured as a bool and discarded; echo the reason in the deny→ask downgrade message, per workspace-guard's idiom, for a better audit trail. |
| <a id="Q6"></a>Q6 | Assert hook script is executable in wiring test | `tests` | 🔲 | S | Wiring test checks the script exists but not that it is executable. Add an `os.access(script, os.X_OK)` assertion, per pr-sentinel's `test_wiring`. |
| <a id="Q7"></a>Q7 | Adopt the brand-image pipeline | `infra` `docs` | 🔲 | S | Adopt the sibling `docs/img` SVG-master → resvg pipeline (favicons, social-preview) + `docs/development/rendering-images.md`; swap the distinguishing glyph. |

## Deferred

| ID | Item | Labels | Sz | Trigger to revive |
|---|---|---|---|---|
| <a id="Q9"></a>Q9 | Stop-hook: detect stranded backgrounded wait | `feature` | M | **Decision:** foreground-guard grows completion-tracking — the agent backgrounds a wait per the guard's advice, then ends the turn without reading the task result. |
