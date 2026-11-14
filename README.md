<div align="center">

<img src="assets/image/KinetRig%20Icon.png" alt="KinetRig Icon" width="128" />

# KinetRig

**AI-powered kinetic motion graphics & video production engine built on Remotion (React).**<br>
Openers, promos, product demos, kinetic typography, and explainers — choreographed by AI intelligence and rendered directly to broadcast-quality MP4 with automatic desktop player preview.

[![Version](https://img.shields.io/badge/version-2.0.0-2f6fd6?style=flat-square)](README.md)
[![License: MIT](https://img.shields.io/badge/license-MIT-3fa34d?style=flat-square)](LICENSE)
[![Engine](https://img.shields.io/badge/engine-Remotion%20(React)-00c853?style=flat-square)](#why)
[![Works with](https://img.shields.io/badge/works%20with-Claude%20Code%20%C2%B7%20Cursor%20%C2%B7%20Codex-7a5af5?style=flat-square)](#quick-start)

[Why](#why) · [Quick Start](#quick-start) · [Remotion Templates](#remotion-templates) · [FAQ](#faq)

</div>

---

## Why

Ask an AI agent for "a video" and you usually get **slides**: static cards, plain fades, and amateur presentation styling. **KinetRig** combines cinematic creative directing with **Remotion (React)**:

- **100% Remotion Powered:** Video compositions are authored as real React components. Frame-by-frame interpolation, zero dropped frames.
- **Continuous 3D Motion:** Camera travel, vertigo dolly-zooms, continuous perspective, and smooth velocity curves.
- **Zero OS Emojis:** Resolution-independent inline SVG vectors, glowing typography, and high-fidelity graphics.
- **Automatic Preview:** Video renders directly to `.mp4` and automatically opens in your default media player.

---

## Quick Start

### 1. Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/Reff33/KinetRig.git
cd KinetRig
npm install
```

### 2. Render & Auto-Launch

Render the default Cinematic Title template and automatically pop open the result:

```bash
node scripts/render-remotion.mjs CinematicTitle '{"title":"KINETRIG 2.0","subtitle":"AI REMOTION PRODUCTION ENGINE"}'
```

The output file is saved to `renders/CinematicTitle.mp4` and instantly launched in your system player (Movies & TV, VLC, QuickTime).

---

## Remotion Templates

Templates live inside `templates/remotion/`:

| Template | File | Description |
| :--- | :--- | :--- |
| 🎬 **Cinematic Title** | `templates/remotion/CinematicTitle.tsx` | Full-bleed kinetic headline with character-by-character reveal, slow cinematic push-in, glowing accent beam, and vignette. |

To add or register custom compositions, add entries to `remotion/Root.tsx`.

---

## Core Motion Laws

1. **Deterministic Frames:** Animations strictly driven by `useCurrentFrame()` and `interpolate()`. Never use `Math.random()` or `Date.now()`.
2. **One Statement Per Shot:** Keep text under 5 words per beat.
3. **Smooth Chromatic Interpolation:** Ambient colors and lighting tween smoothly over 0.4s–0.8s.
4. **9:16 Vertical Safe-Zone:** For Reels/TikTok/Shorts, keep core titles within the center 80% box (864px width).

---

## Repository Structure

```text
KinetRig/
├── SKILL.md                         Primary AI Agent specification & instructions
├── README.md                        Documentation & usage guide
├── remotion/                        Remotion entry point & composition root
│   ├── index.ts                     Root register
│   └── Root.tsx                     Composition definitions
├── templates/remotion/              Reusable React motion templates
│   └── CinematicTitle.tsx           Cinematic Title opener
├── scripts/
│   └── render-remotion.mjs          CLI renderer with automatic player launch
├── references/                      Motion design laws & cinematography guides
└── tsconfig.json                    TypeScript bundler configuration
```

---

## FAQ

<details>
<summary><b>Does it render a real video file?</b></summary>

Yes. It uses Remotion CLI to render actual H.264 MP4 videos frame-by-frame and immediately launches the video in your OS media player for instant review.
</details>

<details>
<summary><b>Can I customize colors, fonts, and timing?</b></summary>

Yes. Every template accepts props (e.g. `title`, `subtitle`, `primaryColor`, `accentColor`, `fontSize`, `zoomIntensity`) passed via CLI JSON or directly in `remotion/Root.tsx`.
</details>
