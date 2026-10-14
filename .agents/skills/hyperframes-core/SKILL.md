---
name: hyperframes-core
description: The HyperFrames composition contract — build one renderable project. Use for composition structure, the `data-*` timing attributes, `class="clip"`, tracks, sub-compositions, variables, framework-owned media playback, deterministic-render rules, and validation. Read before writing composition HTML.
---

# HyperFrames Core Composition Contract

## Rules & Standards
1. **Composition Root**:
   Top-level `index.html` must contain a root `<div>` element with:
   - `id="root"`
   - `data-composition-id="main"`
   - `data-start="0"`
   - `data-duration="<seconds>"`
   - `data-width="1080"` (for 9:16 vertical)
   - `data-height="1920"` (for 9:16 vertical)

2. **Clips**:
   Individual video scenes use `<section class="clip" data-start="x" data-duration="y">`.

3. **Determinism Rules**:
   - No unseeded random numbers (`Math.random()`).
   - No reliance on wall-clock time (`Date.now()`).
   - Single paused GSAP timeline: `const tl = gsap.timeline({ paused: true });`.
   - Register the timeline: `window.__timelines["main"] = tl;`.
   - Avoid CSS `transform: translate(-50%, -50%)` on elements animated with GSAP `x`/`y`. Use flex centering or `xPercent`/`yPercent`.
