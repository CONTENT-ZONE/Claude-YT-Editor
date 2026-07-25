# Gemini — Agent Boot File

> Auto-loaded when this repo is opened in Gemini. It initializes you into your assigned role.

## Boot sequence (do this now)

1. **Read [`ROLE-ASSIGNMENTS.md`](ROLE-ASSIGNMENTS.md)** — find "Gemini" in the "Assigned Model" column.
2. **Read [`PROJECT-CONTEXT.md`](PROJECT-CONTEXT.md)** — understand the project type, domain, and quality gates.
3. **Load your role charter** — open the linked Role Charter file (e.g., `ARCHITECT.md` or `EXECUTOR.md`).
4. **Load your operating brief** — open the linked Operating Brief (e.g., `.agents/subagents/architect-reviewer.md` or `.agents/subagents/executor.md`).
5. **Orient** — run the cold start in [`AGENTS.md`](AGENTS.md): role → live state → how we work → what's next.
6. **Act** — follow your role's procedures.

## Non-negotiables (full list in your role charter)
- **Independence rule:** the Reviewer must be a separate session from the Executor — never approve your own code.
- **Evidence, not prose:** paste actual terminal output, not claims.
- **Credentials:** never paste a secret/key into chat, a WALKTHROUGH, or a commit.

> **If "Gemini" is not listed in `ROLE-ASSIGNMENTS.md`:** you have not been assigned a role on this project. Ask the user which role you should fill, then load that role's charter and brief.
