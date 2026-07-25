# Handoff — <execution NNN> · chunk <n> <slug>

> **Architect → Executor.** Implement **this chunk only**; do not exceed scope.
> **Execution:** <NNN-name> · **Milestone:** <Mx> · **Surface:** <S#> · **Date:** <YYYY-MM-DD>

## Plan first (gate — do this before any code)
1. Produce an **implementation plan** (write it to `implementation_plan.md` in the code repo) covering the files you'll change, the tests you'll add, and how you'll verify.
2. **Pause.** Submit the plan to the Architect for a scope/approach check; you'll get corrections back.
3. **Only after the plan is approved**, implement the chunk and reply with a **WALKTHROUGH**.
> Catching plan-stage errors is far cheaper than a post-code REVISE round.

## Objective
One sentence — what this chunk delivers.

## Scope (in)
Exact files/modules to create or change.

## Out of scope
What must NOT be touched in this chunk.

## Architecture constraints (must follow)
- [Your architecture constraints here, e.g., Layering, Dependency Injection]
- [Any specific rules for the tech stack]
- Name the surface; respect the feature's `_technical` rules.

## Acceptance tests (must pass — write/extend first)
- [ ] AC1 — Given/When/Then (or test name)
- [ ] AC2 — …
- Reference: `02 Features/[Your App Surface]/<feature>/_technical/ACCEPTANCE_TESTS_v00.00.md`

## Done definition
- Compiles; `[your lint command]` clean **from the workspace root**; listed tests green (`[your test command]`); no out-of-scope diffs.
- WALKTHROUGH **pastes the actual lint + test output** as evidence (not a prose "clean" claim); any visual claim names the reference to open. If a check isn't clean, say so — don't report it clean.
- **Do not commit/push/tag** — leave changes in the working tree; the founder owns the commit flow.
- **No credentials** in code, the WALKTHROUGH, or commits — if this chunk needs a secret/key, raise it as a blocker (founder supplies it via gitignored env / CI secrets).

## Inputs / references
- Feature spec / UI design / data model links for this chunk.
