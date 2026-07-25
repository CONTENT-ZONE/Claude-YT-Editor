# Execution Roadmap — the deterministic build order

> **Purpose:** make "what's next" answerable **without asking**. The next execution is the lowest-numbered row below with status ⬜ whose dependencies are ✅. Open it via `.agents/workflows/start-execution.md`, decompose into chunks, and run the AI Delivery Loop per chunk.

## Ordered executions

| # | Execution | Milestone | Depends on | Status |
|---|---|---|---|---|
| 001 | [First Execution] | M0 | — | ⬜ Not started |

## The rule (no asking)
1. Find the first ⬜ row whose deps are ✅ → that's the active execution.
2. Open its packet (`start-execution`): CONTRACT → PLAN → TASKLIST (the TASKLIST = the **chunks**).
3. Run the AI Delivery Loop per chunk; validate; mark chunk done.
4. When all chunks pass `VALIDATION`, mark the execution ✅ and advance.

## Notes
- This roadmap is the source of truth for **order**; the build plan is the source for **milestone scope**.
