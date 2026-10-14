---
name: hyperframes-animation
description: "All animation knowledge for HyperFrames — atomic motion rules, multi-phase scene blueprints, scene transitions, broader motion-design techniques, AND the seven runtime adapters (GSAP default, plus Lottie, Three.js, Anime.js, CSS keyframes, Web Animations API, TypeGPU). Use for any motion or animation task."
---

# HyperFrames Animation & Motion Design

## Key Guidelines
1. **Paused GSAP Timeline**:
   Always create the animation timeline with `{ paused: true }` so it is frame-seekable.
   ```javascript
   window.__timelines = window.__timelines || {};
   const tl = gsap.timeline({ paused: true });
   // Add synchronized tweens
   window.__timelines["main"] = tl;
   ```
2. **Easing Standards**:
   - Entrances: `power3.out`, `expo.out`, `back.out(1.4)`
   - Clicks: `power2.inOut`, `elastic.out(1, 0.4)`
   - Transitions: `power4.inOut`, `circ.inOut`
3. **Motion Graphics Layering**:
   - Background ambient gradient mesh / aurora glow
   - Midground UI panels with subtle glassmorphism and soft border glow
   - Foreground protagonist (cursor, active highlights, click ripples, badges)
