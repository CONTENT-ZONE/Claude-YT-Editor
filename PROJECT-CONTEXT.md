# Project Context

> **Purpose:** Defines WHAT this project is so the entire AI Delivery Loop adapts its language, quality gates, and procedures to match. Every role charter and model boot file reads this to understand the domain.  
> **Edit this once** when you set up the project. Update if the project type or tools change.

## Project Type

> Pick one: `Software` | `Knowledge & Research` | `Content Creation` | `Design` | `Operations` | `Hybrid`

**Type:** Hybrid (Software + Content Creation)

## Project Description

Open-source pipeline (forked from hassancs91 / tracked as CONTENT-ZONE): record a talking-head, then produce a full YouTube video via Claude Code skills — cut, Remotion visuals, voice cleanup, SFX, packaging, upload. No traditional NLE.

## What "implementing" means here

> This tells the Executor what "doing the work" looks like in this project.

| Project Type | Implementation means… |
|-------------|----------------------|
| Software | Writing code, building features, fixing bugs |
| Knowledge & Research | Writing analysis, structuring frameworks, processing transcripts |
| Content Creation | Drafting scripts, editing media, building content systems |
| Design | Creating mockups, building design systems, prototyping |
| Operations | Writing processes, building automation, organizing systems |

**In this project:** Shipping pipeline skills/tools (Python + Remotion TSX), fixing cut/visual/audio bugs, authoring or refining shots and brand contracts, and running end-to-end video production steps without inventing out-of-scope product surface.

## Quality Gate

> This tells the Architect what to verify during REVIEW. Replace "lint/test gate" with whatever quality check fits your domain.

| Project Type | Quality gate looks like… |
|-------------|------------------------|
| Software | Lint clean, tests pass, no out-of-scope diffs |
| Knowledge & Research | Accuracy review, source verification, framework consistency |
| Content Creation | Editorial review, brand consistency, format compliance |
| Design | Design review, accessibility check, design system compliance |
| Operations | Process review, completeness check, no broken links |

**In this project:** Remotion shots render without crash; brand.md / brand.ts / fonts.ts stay in sync when brand changes; pipeline steps leave expected artifacts under `videos/<project>/`; no A/V drift or ghost speech before upload; diffs stay inside the requested chunk (skill, tool, shot, or packaging).

## Workspaces

> Some projects split "planning" and "execution" across two repos. Others do everything in one place.

- **Brain (specs, planning, tracking):** this repo (`Tasks/`, `AGENTS.md`, `.agents/LOCAL_CONTEXT.md`)
- **Execution (where work happens):** same repo (`tools/`, `remotion/`, `videos/`, skills)

## Tech Stack / Tools

_What tools, languages, frameworks, or formats does this project use?_

- Python 3.10+ (`tools/`, AssemblyAI cut path, upload)
- Node 18+ / Remotion (TSX shots, studio)
- ffmpeg / ffprobe
- Claude Code skills (`/clean-cut`, `/make-tsx`, `/fake-screencast`, `/clean-audio`, `/suggest-sfx`, `/packaging`, `/brand-setup`, `/vidtsx-2d-generator`)
- Optional: YouTube upload as private draft

## Domain-Specific Rules

- Pipeline order: **cut → visuals → voice → SFX → packaging → upload**
- You record talking head only; screen moments are code (Remotion), not screen capture
- `brand.md` is the style contract; `/brand-setup` owns brand.md + remotion brand/fonts together
- `remotion/src/shots/example/` is the worked example — read before inventing new kit patterns
- Matrix hub: Context-Matrix; this is a **CONTENT-ZONE project node** (`MATRIX_NODE_LINK.md`)
