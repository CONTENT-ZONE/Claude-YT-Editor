# Tasks — Execution Packets

> **What this folder is:** the home of **executions** — scoped initiatives that turn plans into shipped reality. **Every execution is a packet** with the same four files, so nothing is started without a contract and nothing is "done" without validation.

## The rule (non-negotiable)

> **Contract first. Validation last. No exceptions for meaningful work.**

For every new execution, **before any work begins**, create a packet:

```text
Tasks/NNN-execution-name/
  CONTRACT.md     # created FIRST — what must be true at the end (the success condition)
  PLAN.md         # the approach: steps, dependencies, sequencing
  TASKLIST.md     # the live tracker: checkboxes, status, owner
  VALIDATION.md   # created/completed LAST — each acceptance criterion checked PASS/FAIL with evidence
```

Scaffold it with the workflow: `.agents/workflows/start-execution.md`. Templates live in `_TEMPLATES/`. The CONTRACT reuses the `internal-contracts` fields; acceptance criteria use `deliver-acceptance-criteria`.

## Lifecycle

```
DRAFT ─► create CONTRACT + PLAN + TASKLIST ─► (human gate: contract approved?) ─►
  IN PROGRESS ─► work; keep TASKLIST current each session ─►
  VALIDATING ─► complete VALIDATION.md (every acceptance criterion PASS/FAIL + evidence) ─►
  DONE (all PASS, signed off) | BLOCKED | DROPPED
```

An execution is **DONE only when `VALIDATION.md` shows every acceptance criterion passing.** A finished tasklist is *not* done; a validated contract is.

## Execution index

| # | Execution | Status | Packet |
|---|---|---|---|
| — | *(Add rows when you open packets)* | — | — |

## Order & execution
- **What's next is deterministic:** `EXECUTION_ROADMAP.md` — the ordered execution list (open the first ⬜ whose deps are done; don't ask).
- **How chunks get built:** the AI Delivery Loop (`.agents/workflows/ai-delivery-loop.md`) (Architect HANDOFF → Executor WALKTHROUGH → Architect REVIEW). Per-chunk templates: `_TEMPLATES/{HANDOFF,WALKTHROUGH,REVIEW}_TEMPLATE.md`. Chunk artifacts + execution log live in the **code repo** `docs/delivery/`; this `TASKLIST` is the board.
