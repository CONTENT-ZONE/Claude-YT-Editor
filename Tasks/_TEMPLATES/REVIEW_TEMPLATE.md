# Review — <execution NNN> · chunk <n> <slug>

> **Architect.** Validate the WALKTHROUGH against the HANDOFF, acceptance tests, and architecture.
> **Date:** <YYYY-MM-DD> · **Result: PASS / REVISE**

## Independent verification (reproduce — don't trust the WALKTHROUGH's prose)
> A "clean/done/tests pass" claim counts only once *you* reproduce it. Tick each before deciding.
- [ ] Re-ran the **full** lint/test gate myself from the **workspace root** (not the Executor's narrowed path) — result: `<paste tail / exit code>`.
- [ ] Ran `git diff HEAD` — diff is **in-scope only**; no unrequested files/UI/endpoints, nothing self-committed.
- [ ] Opened every artifact the WALKTHROUGH names (golden/screenshot/output) and confirmed it shows what's claimed.
- [ ] No secret/key/token appears in the diff or the WALKTHROUGH.

## Acceptance check
| AC | Pass? | Note |
|---|---|---|
| AC1 | | |
| AC2 | | |

## Architecture / quality check
- [ ] Layer + DI rules respected.
- [ ] Styling conventions respected.
- [ ] Scope respected (no out-of-scope changes); tests green.

## Findings (if REVISE — specific & minimal)
1. `<file:line>` — <issue> → <fix>.
2. …

## Decision
- **PASS** → tick the chunk in `TASKLIST`; proceed to next chunk.
- **REVISE** → issue a revised HANDOFF (same chunk) and loop.
