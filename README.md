# KinetRig 🎬

> Zero-dependency 144 FPS kinetic motion graphics & video engine built for AI coding agents (Claude Code, Cursor, Copilot, ChatGPT, OpenCode).

Ultra-fluid 144 FPS motion engine with zero frame drops. Uses deterministic timeline stepping (`tl.time`) to render every frame offline, paired with a 40 Mbps clean capture pipeline for razor-sharp 3D camera travels, kinetic typography, and WebGL particles on high-refresh displays.

---

## ⚡ Why KinetRig?

| Traditional Tools | KinetRig |
|---|---|
| Heavy node dependencies (React, Remotion, Manim) | **Pure Browser Native** (HTML5 + GSAP + Three.js, zero build step) |
| Dropped frames during real-time screen recording | **Deterministic 144 FPS** offline timeline stepping (0% frame drop) |
| OS emojis that pixelate on 1080p/4K (🤖, ⚡, 🐙) | **100% Inline SVG Vectors** with neon glow & brand colors |
| Slideshow deck fades (feels like PowerPoint) | **Continuous 3D Camera** traveling, whip-pans & push-throughs |
| HUD buttons, scrubber & mouse cursor in recordings | **Automatic Clean Capture** (`body.clean-capture` hides all UI & cursor) |

---

## 🚀 Quick Install

### For AI Coding Agents (Claude Code, Cursor, etc.)
```bash
npx -y skills@latest add https://github.com/Reff33/KinetRig --copy --yes
```

### Manual Usage
Clone this repository and open any starter from `assets/` in your browser:
```bash
git clone https://github.com/Reff33/KinetRig.git
cd KinetRig
```

---

## 📦 Curated Starters (`assets/`)

### Brand Openers & Narrative
1. **`starter-opener.html`** — High-impact brand opener with continuous 3D camera, macro zoom, Three.js particle space, and kinetic text.
2. **`starter-explainer.html`** — Continuous action explainer with camera traveling through a unified world.

### Explainer Styles
3. **`starter-explainer-kartun.html`** — Paper & print cartoon collage explainer with cutout illustrations and drop shadows.
4. **`starter-explainer-jurnalisme.html`** — Visual journalism explainer with editorial framing and data evidence.
5. **`starter-explainer-katalog.html`** — Clean white catalog explainer for minimalist product or portfolio showcases.
6. **`starter-explainer-panggung.html`** — Cartoon stage explainer with proscenium depth, curtains, and spotlight entries.
7. **`starter-explainer-sketsa.html`** — Vintage sketch explainer with textured blueprints and architectural hatching.

### Interactive & Product Simulation
8. **`starter-data.html`** — Data animation with animated metric counters, dynamic SVG bar/line charts, and KPI pulse cards.
9. **`starter-ecommerce.html`** — 3D product showcase card with price badge, specs matrix, and CTA glow.
10. **`starter-chat.html`** — Diegetic text message & conversational chat simulation with realistic typing cadence.

---

## 🎥 144 FPS Lossless Video Export

### Option A: In-Browser One-Click Download (144 FPS)
Every starter includes a floating **Download Video** button (styled with inline camera SVG). When clicked:
- Automatically hides all UI controls, timeline scrubbers, and HUD (`body.clean-capture`).
- Passes `cursor: 'never'` to getDisplayMedia so the mouse pointer never appears in the output.
- Records directly at **144 FPS** and **40 Mbps** bitrate.

### Option B: Studio Offline Render (Zero Drops Guaranteed)
```bash
# 1. Start local server
npx serve . -p 5178

# 2. Render clean frames frame-by-frame (default 144 FPS)
node scripts/export-frames.mjs

# 3. Assemble lossless MP4 with ffmpeg
ffmpeg -framerate 144 -i frames/f%05d.png -c:v libx264 -pix_fmt yuv420p -crf 14 output_144fps.mp4
```

---

## 📜 Core Motion Laws (Anti-PowerPoint)

1. **Continuous World:** Scenes never fade like static slides. Transitions are driven by continuous camera travel, push-throughs, or motivated object wipes.
2. **Zero Emojis:** Never use OS emojis. Always use resolution-independent inline SVG vectors (`<svg viewBox="0 0 24 24">`).
3. **Deterministic Timelines:** All animations are driven strictly by `tl.time()`. Never use `Date.now()` or `Math.random()`.
4. **One Statement Per Shot:** Keep text under 5 words per beat. Let motion and depth convey emotion.

---

## 📄 License
MIT © Reff33
