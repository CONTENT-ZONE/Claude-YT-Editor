# Role Assignments

> **Purpose:** Single source of truth for which AI model fills which role in this project's delivery loop.  
> **To swap roles:** Edit the table below. Every model boot file (`CLAUDE.md`, `GEMINI.md`, `GROK.md`, `CHATGPT.md`) reads this config to know which role to load. No other files need to change.

## Current Assignments

| Role | Assigned Model | Role Charter | Operating Brief |
|------|---------------|--------------|-----------------|
| **Architect / Reviewer** | Claude | [`ARCHITECT.md`](ARCHITECT.md) | [`.agents/subagents/architect-reviewer.md`](.agents/subagents/architect-reviewer.md) |
| **Executor** | Gemini | [`EXECUTOR.md`](EXECUTOR.md) | [`.agents/subagents/executor.md`](.agents/subagents/executor.md) |

## Available Roles

- **Architect / Reviewer** — The senior PM + tech lead. Owns specs, contracts, chunk decomposition, HANDOFFs, and REVIEW (PASS/REVISE). Does not write app code in the normal flow.
- **Executor** — The staff-level engineer. Implements one chunk at a time per the HANDOFF, runs tests, writes a WALKTHROUGH. Does not edit the product brain.

## Rules

- **Independence rule:** The Reviewer must be a separate session from the Executor — never the same context approving its own code.
- **Any model can fill any role.** The assignments above are defaults, not constraints.
- **If one model covers both roles**, run them as two independent sessions so review stays honest.

## How Model Boot Files Use This

Each model boot file (e.g., `CLAUDE.md`) instructs the model to:
1. Read this `ROLE-ASSIGNMENTS.md` file
2. Find its name in the "Assigned Model" column
3. Load the corresponding Role Charter and Operating Brief
4. Begin acting in that role
