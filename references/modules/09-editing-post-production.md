# 09 — Editing & Post-Production (Remotion Production Engine)

Code-driven Non-Linear Editing (Code-Driven NLE) using Remotion (React). Rhythm structures, kinetic subtitles, frame-accurate pacing, and broadcast MP4 export optimization.

---

## 1. Speed Ramping (Temporal Velocity Manipulation)

Speed ramping accelerates through transitional movements and brakes precisely on climax frames using cubic Bezier curves in Remotion:

```tsx
import { interpolate, Easing } from 'remotion';

// Smooth velocity snap followed by sustained glide
const scale = interpolate(frame, [0, 45], [0.8, 1.0], {
  extrapolateLeft: 'clamp',
  extrapolateRight: 'clamp',
  easing: Easing.bezier(0.16, 1, 0.3, 1),
});
```

---

## 2. Kinetic Subtitle & Caption Stacker

Modern dynamic subtitles with real-time word highlighting (Karaoke Glow / Kinetic Word Stacker):

```tsx
import React from 'react';
import { useCurrentFrame, interpolate } from 'remotion';

export const KineticCaption: React.FC<{ words: { text: string; startFrame: number; endFrame: number }[] }> = ({ words }) => {
  const frame = useCurrentFrame();

  return (
    <div style={{ display: 'flex', gap: 12, justifyContent: 'center', fontSize: 44, fontWeight: 800 }}>
      {words.map((w, i) => {
        const isActive = frame >= w.startFrame && frame <= w.endFrame;
        const scale = isActive ? interpolate(frame, [w.startFrame, w.startFrame + 5], [1, 1.15], { extrapolateRight: 'clamp' }) : 1;
        const color = isActive ? '#00F0FF' : 'rgba(255, 255, 255, 0.6)';
        const textShadow = isActive ? '0 0 24px rgba(0, 240, 255, 0.6)' : 'none';

        return (
          <span key={i} style={{ color, transform: `scale(${scale})`, textShadow, transition: 'color 0.1s' }}>
            {w.text}
          </span>
        );
      })}
    </div>
  );
};
```

---

## 3. Remotion CLI Production Rendering & Export Pipeline

### Studio Master MP4 Render Pipeline

```bash
# Render directly to H.264 broadcast MP4 using the automated pipeline:
node scripts/render-remotion.mjs <CompositionId> '[props]'

# Or manual Remotion CLI command:
npx remotion render remotion/index.ts <CompositionId> renders/<CompositionId>.mp4 --gl=angle
```

### Essential Export Parameters

- **Framerate:** 60 FPS standard (or 120 FPS for high-refresh devices).
- **Pixel Format & Codec:** H.264 `yuv420p` (100% universal compatibility across mobile players, web, Twitter/X, and YouTube).
- **GPU Backend:** `--gl=angle` for native Windows hardware rendering acceleration.
