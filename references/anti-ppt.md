# Anti-PowerPoint Motion Design Laws

Video promos and kinetic motion graphics must NEVER feel like a slide deck.

## Violations & Fixes

| Violation (Looks like PPT) | Professional Motion Fix |
|---|---|
| Section fades (slide 1 fades out, slide 2 fades in) | **Continuous Camera Traveling** (push-through, continuous pan, orbit) |
| Three bullet points on screen at once | **One Statement Per Shot** (≤ 5 words per beat, dynamic text staggering) |
| OS emojis (🤖, ⚡, 🐙, 🕷) | **100% Inline SVG Vectors** with neon glow & brand colors |
| Static background with moving text | **Multi-layered Living Background** (subtle particles, gradient drift, WebGL core) |
| HUD controls, timers, or mouse cursor recorded in video | **Clean Capture Mode** (`body.clean-capture` hides all UI, `cursor: 'never'`) |
| Choppy 30fps screen capture | **Deterministic 144 FPS Offline Stepping** (`tl.time(t)`) |

## Attention Hierarchy

1. **Headline / Sentence first** (0.6 - 0.9s ease out).
2. **Hero Object / Visual anchor follows** (camera moves in to frame it).
3. **Detail chips / Stats come last** (staggered cascade).
