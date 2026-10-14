---
name: oversized-cursor
description: House-style oversized cursor technique for HyperFrames launch videos and UI walkthroughs. Load whenever a scene involves cursors or a pointer-led action, when kicking off a UI scene, when igniting a morph/transition/typing run with a click, or when a scene needs a high-yield source of motion.
---

# Oversized Cursor — The Motion Protagonist

A deliberately oversized macOS-style pointer that acts as the viewer's eye-carrier across the screen.

## Anatomy & Specs
- **Scale**: ~5.5% to 7% of composition width (for 1080px width: 60px–75px).
- **Styling**: Sleek SVG arrow with crisp drop shadow (`filter: drop-shadow(0 8px 16px rgba(0,0,0,0.4))`).
- **Entry Law**: Always enters physically from off-screen with a natural deceleration curve (`power2.out` or `power3.out`).
- **Tip-Targeting**: Cursor's exact tip point aligns with target interactive elements.
- **Click Tap & Shockwave**:
  - Pointer squashes slightly (`scale: 0.85` for 80-100ms) then bounces back to 1.0.
  - Generates an expanding neon click ring / ripple wave (`scale: 0 -> 2.5`, `opacity: 0.8 -> 0`).
  - Causal Ignition: The click instantly triggers the target element's action (active button depression, code generation, terminal output, page transitions).
