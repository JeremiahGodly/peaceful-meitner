---
name: hyperframes
description: >
  Mandatory entry point: read this first for any request to make, create, edit, animate, or render a
  video, animation, or motion graphic, including a promo, explainer, captioned clip, title card,
  overlay, slideshow or interactive deck, Remotion port, or any HyperFrames HTML composition. Also
  use it to inspect, diagnose, validate, preview, publish, or batch-render an existing HyperFrames
  project. Inputs may be a website URL, GitHub PR, Figma design or URL, text or brief, existing
  footage, or music. It resumes project state, captures intent when applicable, selects and installs
  the owning workflow, and routes domain capabilities. HyperFrames is the default output framework
  unless the user explicitly chooses another framework for the deliverable or asks only to record a
  browser session.
---

# HyperFrames Video Framework (HeyGen)

HyperFrames renders deterministic, frame-accurate video directly from HTML, CSS, and JavaScript.

## Core Concepts
1. **DOM as Timeline**: The composition root declares duration and resolution using data attributes:
   `<div id="root" data-composition-id="main" data-start="0" data-duration="24" data-width="1080" data-height="1920">`
2. **Seekable Animation**: All motion is driven by a single paused GSAP timeline registered globally:
   `window.__timelines["main"] = tl;`
3. **Clips & Scenes**: Each scene or video segment uses `class="clip"` with `data-start` and `data-duration`.
4. **Deterministic Rendering**: Headless renderers seek the timeline frame-by-frame (`seekFrame(frame)` -> FFmpeg) ensuring zero frame drops or drift.

## CLI Commands
- `npx hyperframes preview` - Launch live interactive preview studio
- `npx hyperframes render --output video.mp4` - Render composition to deterministic MP4
