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

### 2. Live Preview in Remotion Studio

Launch the interactive Remotion Studio in your browser:

```bash
npm run preview
# or: node scripts/preview-remotion.mjs
```

---

## Remotion Templates

Templates live inside `templates/remotion/`:

| Template | File | Description |
| :--- | :--- | :--- |
| 🎬 **Cinematic Title** | `templates/remotion/CinematicTitle.tsx` | Full-bleed kinetic headline with character-by-character reveal, slow cinematic push-in, glowing accent beam, and vignette. |
| ⚡ **Glitch Terminal** | `templates/remotion/GlitchTerminal.tsx` | Exact 6.0s cybernetic terminal with memory hex stream, live memory bar, decrypting text scramble with RGB split glitch chromatic aberration. |
| 📊 **SaaS Macro** | `templates/remotion/SaasMacro.tsx` | Exact 7.0s 3D browser mockup perspective with dynamic SVG metric chart, animated drawing line, and sidebar rack focus blur swap. |
| 🔲 **Bento Grid** | `templates/remotion/BentoGrid.tsx` | 3x2 glassmorphic modular bento card layout with staggered spring pop entries and animated progress telemetry. |
| 💬 **Chat Dialogue** | `templates/remotion/ChatDialogue.tsx` | Diegetic AI chat device with 3D perspective tilt, human keystroke typing cadence, pulsing typing dots, and reaction badges. |
| 📈 **Data Metrics** | `templates/remotion/DataMetrics.tsx` | Exact 8.0s KPI dashboard with 3 popup metric cards, animated number counter, and 6 elastic animated SVG bar charts. |

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
│   ├── CinematicTitle.tsx           Cinematic Title opener
│   ├── GlitchTerminal.tsx           Decrypt Glitch Terminal
│   ├── SaasMacro.tsx                SaaS Macro UI tour
│   ├── BentoGrid.tsx                Modular Bento Grid architecture
│   ├── ChatDialogue.tsx             Diegetic AI chat simulation
│   └── DataMetrics.tsx              KPI & Data Metrics visualizer
├── scripts/
│   ├── preview-remotion.mjs         CLI to launch Remotion Studio in browser
│   └── render-remotion.mjs          CLI renderer with automatic player launch
├── references/                      Motion design laws & cinematography guides
└── tsconfig.json                    TypeScript bundler configuration
```

---

## FAQ

<details>
<summary><b>Does it render a real video file?</b></summary>

Yes. You can preview in browser or use Remotion CLI to render actual H.264 MP4 videos frame-by-frame.
</details>

<details>
<summary><b>Can I customize colors, fonts, and timing?</b></summary>

Yes. Every template accepts props (e.g. `title`, `subtitle`, `primaryColor`, `accentColor`, `fontSize`, `zoomIntensity`) passed via CLI JSON or directly in `remotion/Root.tsx`.
</details>
