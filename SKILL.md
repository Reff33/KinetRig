---
name: kinet-rig
description: Zero-dependency 144 FPS kinetic motion graphics & video engine for browser (openers, explainers, data animations, ecommerce showcase, chat simulation) using pure HTML, GSAP, and Three.js with clean studio render.
license: MIT
metadata:
  author: Reff33
  homepage: https://github.com/Reff33/KinetRig
  version: "1.0.0"
---

# KinetRig — Zero-Dependency 144 FPS Browser Motion Engine

Motion graphics that move like real studio cinema, not PowerPoint slides. Built natively for AI coding agents (Claude Code, Cursor, Copilot, ChatGPT, OpenCode).

## Core Principles

1. **Zero Runtime Dependencies:** Deliverable (`index.html`) requires ONLY a modern browser. No Node build step, no React/Remotion bloat, no Python Manim setup.
2. **Deterministic 144 FPS Timeline:** All animations driven strictly by `tl.time()`. No `Date.now()`, no `Math.random()`. Allows frame-accurate offline rendering with 0 dropped frames.
3. **Zero OS Emojis (Strict Vector Quality):** NEVER use system emojis (🤖, ⚡, 🐙, 🧠, 🕷). ALWAYS use resolution-independent Inline SVG vectors (`<svg viewBox="0 0 24 24">`) with `currentColor` or brand colors with neon glow. Emojis look amateurish and pixelate on 1080p/4K; inline SVGs guarantee crisp studio finish with zero external dependencies.
4. **Anti-PowerPoint Motion:** No static slide deck fades. Scenes transition through continuous camera traveling (push-through, whip pan, yaw 3D) or motivated object wipes.
5. **Clean Video Export:** `body.clean-capture` auto-hides all UI, scrubber, and HUD buttons during recording. Passes `cursor: 'never'` to stream capture.

---

## 6-Phase Agent Workflow

### Phase 1: Brief
Identify:
- Topic / Product
- Duration (15-30s for opener/teaser, 30-60s for explainer/data)
- Aspect Ratio: `16:9` (Web, YouTube, Desktop) or `9:16` (TikTok, Reels, Shorts)
- Audio / Voiceover (optional)

### Phase 2: Style Brief (Three Candidates, One Pick)
DO NOT write code yet. Inspect project context (README, package.json, tech stack, domain) and propose 3 concept candidates:
- **Concept:** Pick from 5 categories:
  1. Opener & Brand Teaser (`starter-opener.html`)
  2. Explainer & Narrative (`starter-explainer.html`)
  3. Animated Data & Metrics (`starter-data.html`)
  4. Product & E-Commerce Showcase (`starter-ecommerce.html`)
  5. Diegetic Chat & Text Message (`starter-chat.html`)
- **Style Direction:**
  1. *Cinematic Dark* (near-black, neon bloom, bold grotesk)
  2. *Poster Color-Block* (solid color fields, giant cropped letters)
  3. *Editorial Light* (cream/white, luxury display serif, hairlines)
  4. *Brutalist Mono* (B&W hard grid, monospace, high contrast)
  5. *Grainy Gradient* (saturated glowing shapes, fine grain, camera depth)
- **Palette with Source:** 1 Primary Brand HEX, 1 Background HEX, 1 Accent HEX.
- **Rationale:** Why each candidate fits the product.

### Phase 3: User Approval
Wait for the user to confirm 1 candidate or adjust parameters before generating code.

### Phase 4: Build from Official Starter
Adapt the chosen starter template from `assets/` into a single self-contained `index.html`:
- Link GSAP v3 & Three.js via CDN (jsdelivr / unpkg).
- Keep all styles and scripts inline for instant double-click viewing.
- Mount `window.OPENER = { tl, DURATION, seek, ready }` for offline renderers.

### Phase 5: Anti-PowerPoint Rules
- Persistent subject or shared world across transitions.
- Max 2 text levels per scene (min 30px font on 1080p).
- 1 shot = 1 statement (≤ 5 words per beat).

### Phase 6: Clean 144 FPS Export
- Autoplay, loop, and `?debug=1` timeline scrubber.
- One-Click In-Browser Capture: floating '🎥 Download Video' button recording at 144 FPS, 40 Mbps bitrate with `body.clean-capture`.
- Headless Studio Render:
  ```bash
  node scripts/export-frames.mjs
  ffmpeg -framerate 144 -i frames/f%05d.png -c:v libx264 -pix_fmt yuv420p -crf 14 output_144fps.mp4
  ```
