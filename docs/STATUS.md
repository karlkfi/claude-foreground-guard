# Project Status

Single source of truth for progress and priorities. Pick the next task from
the top of the Queue.

**Status:** 🔲 ready · 🚫 blocked
**Size:**   S = one session/PR · M = 2–3 sessions · L = needs a plan doc under `docs/plan/`
**Labels:** `bug` `parser` `config` `feature` `tests` `docs` `infra`
**Next ID:** Q10

## Queue

_No open items._

| ID | Item | Labels | St | Sz | Notes |
|---|---|---|---|---|---|

## Deferred

| ID | Item | Labels | Sz | Trigger to revive |
|---|---|---|---|---|
| <a id="Q9"></a>Q9 | Stop-hook: detect stranded backgrounded wait | `feature` | M | **Decision:** foreground-guard grows completion-tracking — the agent backgrounds a wait per the guard's advice, then ends the turn without reading the task result. |
