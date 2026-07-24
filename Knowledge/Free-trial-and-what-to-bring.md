# Free trial & what to bring

Practical guide for the **first use** of this repo — especially if you want to try it **without paying for API keys**.

Related: [Stop paying for video editors.md](./Stop%20paying%20for%20video%20editors.md) (source video transcript).  
Canonical pipeline docs: `CLAUDE.md` / skills under `.claude/skills/`.

---

## What this project is (one line)

You record a **talking head**. An AI agent + code does the rest: cut → visuals (Remotion TSX) → voice clean → SFX → packaging → YouTube upload. No traditional video editor required.

**Claude-branded, not Claude-locked.** Skills live under `.claude/skills/`, but any capable agent (Claude Code, Grok, Cursor, etc.) can read those `SKILL.md` files and drive the same Python/Remotion tools.

---

## Free path first (recommended)

### Do you need a video? A transcript?

| Goal | Video? | Transcript? | Paid APIs? |
|------|--------|-------------|------------|
| Title card / statement / simple motion graphic | **No** | **No** | **No** |
| Preview stock example shots (`remotion/src/shots/example/`) | **No** | **No** | **No** |
| Brand colors / wordmark proof (`BrandProof`) | **No** | Optional text | **No** |
| Fake browser / VS Code screencast from screenshots | Screenshots only | Optional | **No** (local render) |
| Clean-cut talking-head | **Yes** (raw footage) | Word-level timing (AssemblyAI *or* you supply) | **Usually yes** (AssemblyAI) |
| Voice isolate / generate new SFX-music | After cut | Helps SFX timing | **Yes** (ElevenLabs) unless local RNNoise + existing library clips only |
| AI face thumbnails | Face refs + idea | Optional | **Yes** (Gemini) |
| YouTube upload draft | Final file | Packaging text | **No** key — OAuth only |

**Bottom line for a free trial:** do **not** start with a video. Bring a **one-line title/statement** (and optional brand colors). Video + transcript matter for the full cut pipeline, which usually costs a few dollars in APIs.

### What to say to the agent (copy-paste examples)

1. **Simplest free shot**
   > Make a simple full-screen statement shot: **[YOUR LINE]**. Use the default brand. Free only — no APIs.

2. **Show the stock demos**
   > Open / render the example Remotion shots so I can see what the kit looks like. No new footage.

3. **Optional brand**
   > Brand: channel name **[X]**, accent **#______**, background **#______**. Render BrandProof. Keep free.

### Local deps only (free path)

From **repo root**:

- Node + once: `cd remotion && npm install`
- Optional later for bake/export: `ffmpeg` / `ffprobe` on PATH
- Python venv **not** required until you run `tools/*.py`

No `.env` keys needed for pure TSX authoring + Remotion Studio / frame renders.

### After the free shot

Pipeline order when you go further: **cut → visuals → voice → SFX → packaging → upload**.  
Do not skip a solid cut; later steps depend on its timing.

---

## When you *do* bring a video

### Minimum for a real clean-cut

1. **Raw talking-head file** under `videos/<project>/` (see `videos/README.md`; masters/raw are git-ignored).
2. **Word-level transcript** — happy path is AssemblyAI via `tools/transcribe.py` / `/clean-cut` skill.
   - Video alone is **not** enough for confident cuts.
   - Transcript alone is **not** enough (nothing to cut).
   - A self-provided timed transcript (e.g. Whisper with timestamps) *might* work free, but is not the repo’s default path and needs more agent care.

### Paid services (cheap, not free)

As noted by the project author: models are not free; a full edited video might be on the order of a few dollars vs. a human editor.

| Key / service | Used for |
|---------------|----------|
| `ASSEMBLYAI_API_KEY` | Transcription + cut confidence |
| `ELEVENLABS_API_KEY` | Voice isolate, SFX, music gen |
| `GEMINI_API_KEY` | Thumbnail generation |
| YouTube OAuth (not a key in `.env`) | `tools/yt_upload.py` / `yt_stats.py` → tokens under `.youtube/` |

Copy `.env.example` → `.env` at repo root. Never commit `.env`.

### Full pipeline (after free trial)

1. **Brand** — `/brand-setup` (or keep house default): `brand.md` + `remotion/src/brand.ts` + `fonts.ts` stay in sync.
2. **Cut** — `/clean-cut` → `cuts.json`, edited transcript, master cut.
3. **Visuals** — `/make-tsx` (+ `/fake-screencast`) → shots under `remotion/src/shots/<project>/`.
4. **Voice** — `/clean-audio` (ElevenLabs or local RNNoise).
5. **SFX** — `/suggest-sfx` (prefer library reuse before generating).
6. **Packaging** — `/packaging` (title + 3 thumbnail bets).
7. **Upload** — `python tools/yt_upload.py` after QA (`verify_cut.py`, frame checks).

Always run tools from **repo root**. Use the project venv for Python (`venv/Scripts/python` on Windows). After adding shots: `cd remotion && npm run gen`.

---

## Agent usage notes

- Skills are in `.claude/skills/<name>/SKILL.md`. In Claude Code they may be slash commands (`/clean-cut`); in other agents, say the same intent in plain language and point the agent at the skill file.
- **QA is not optional** for real videos: render frames and look at them; run `verify_cut.py` on cuts.
- Reuse `media/library/` assets before generating new ones; per-video media goes in `media/projects/<project>/`.

---

## Quick decision tree

```
Want to spend $0 right now?
  YES → Bring a title line (optional brand). Make a Remotion shot or open examples.
  NO  → Ready for cut pipeline?
         YES → Drop raw video in videos/<project>/, set ASSEMBLYAI_API_KEY, run clean-cut.
         PARTIAL → Video + your own timed transcript (advanced; not default).
```

---

## Changelog

| Date | Note |
|------|------|
| 2026-07-24 | Initial guide: free trial materials, when video/transcript matter, paid vs free, first prompts. |
