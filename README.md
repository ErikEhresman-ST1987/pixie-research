# Pixie Research

A lightweight, incremental PixiJS learning laboratory and reference library.

## One-place testing

- **Dashboard source:** [index.html](index.html)
- **Experiment 01:** [Scene Layering](experiments/scene-layering/index.html) — core interaction user-verified on iPad Safari
- **Experiment 02:** [Automatic Depth Sorting](experiments/automatic-depth-sorting/index.html) — core dragging and depth ordering user-verified on iPad Safari
- **Experiment 03:** [Visual State Changes](experiments/visual-state-changes/index.html) — core interaction user-verified on iPad Safari
- **Experiment 04:** [Simple Animation](experiments/simple-animation/index.html) — core motion and controls user-verified on iPad
- **Experiment 05:** [Environmental Atmosphere](experiments/environmental-atmosphere/index.html) — visual atmosphere user-verified on iPad; controls/performance unverified
- **Research history and detailed experiment README:** [research/scene-layering branch](../../tree/research/scene-layering)

**Website activation:** GitHub Pages must be enabled once in repository Settings → Pages → Build and deployment → Deploy from a branch → `main` → `/(root)`. Until then, GitHub shows source files, not a playable website. Expected Pages address once activated: `https://erikehresman-st1987.github.io/pixie-research/` (not yet verified live).

## Working method

1. Choose one capability, beginning with Level 1.
2. Work in a `research/*` branch with a current README: objective, implementation, verified and unverified results, reusable parts, failures, and limitations.
3. Make the current test accessible from the single dashboard. This is a **test preview**, not promotion of the technique as validated.
4. Run the experiment in a browser on the actual device; record what happened.
5. Keep useful, verified examples as references; discard or label unsuccessful work. Extract a shared module only when genuine reuse justifies it.
6. Favor high payoff with low total complexity and comfortable device headroom.

The existing games are not modified by this research. The dashboard can display unverified experiments; **validation status belongs to each experiment, not its location in the repository**.

## Current status

- Scene Layering: core interaction user-verified on iPad Safari.
- Automatic Depth Sorting: core interaction user-verified on iPad Safari; [research branch](../../tree/research/automatic-depth-sorting).
- Visual State Changes: core interaction user-verified on iPad; [research branch](../../tree/research/visual-state-changes).
- Simple Animation: core motion and controls user-verified on iPad; [research branch](../../tree/research/simple-animation).
- Environmental Atmosphere: visual payoff user-verified on iPad; controls/performance unverified; [research branch](../../tree/research/environmental-atmosphere).
- **Experiment 06:** [Local Environmental Reactions](experiments/local-environmental-reactions/index.html) — implemented, awaiting device test
- **Research synthesis:** [Findings 01–05 and future game examples](RESEARCH-FINDINGS-01-05.md)
- **Experiment 07:** [Ambient Life](experiments/ambient-life/index.html) — creature visuals user-verified on iPad; controls/activity comparison pending
- **Experiment 08:** [Animated Production Activity](experiments/production-activity/index.html) — visuals, pause, effects-off progress independence, and reset user-verified on iPad; reduced-motion unverified
- **Experiment 09:** [Time of Day and Lighting](experiments/time-of-day-lighting/index.html) — sunset, night, and refined lighting transitions positively verified on iPad; other controls and performance unverified
- **Experiment 10:** [Weather and Rain](experiments/weather-rain/index.html) — light/heavy rain and weather transitions visually verified on iPad; other controls and performance unverified
- Demos use pinned online PixiJS 8.21.0 scripts. Offline hosting is not yet tested.

- **Experiment 11:** [The Living Landscape](experiments/combined-scene/index.html) — combined visual effect and feature toggles positively verified on iPad; measured performance and remaining controls unverified. [Research branch](../../tree/research/combined-scene).

- **Experiment 12:** [Mobile Rendering Headroom](experiments/rendering-headroom/index.html) — Quiet (8), Normal (47), and Busy (161) all reported smooth at displayed 60 FPS on iPad; visual-value comparison and sustained performance unverified. [Research branch](../../tree/research/rendering-headroom).

- **Experiment 13:** [Viewport Culling](experiments/viewport-culling/index.html) — iPad reported ~50 updates/frame with optimization ON versus designed 300 OFF, smooth panning and no visible difference; measured FPS and resource savings unverified. [Research branch](../../tree/research/viewport-culling).

- **Experiment 14:** [Reusable Particle Effects](experiments/particle-recycling/index.html) — Reuse ON showed fixed 65/180 Graphics, zero destroyed, and 60 FPS in Gentle/Busy screenshots; Reuse OFF counter grew rapidly on iPad. OFF-mode FPS and resource savings unverified. [Research branch](../../tree/research/particle-recycling).

- **Experiment 15:** [Smooth Camera Zoom](experiments/camera-zoom/index.html) — iPad verified lag-free-feeling pan, pleasant smooth zoom, instant zoom when smooth disabled, and unchanged visual appearance; numeric FPS, pinch and raster clarity unverified. [Research branch](../../tree/research/camera-zoom).

- **Experiment 16:** [Interactive Object Selection](experiments/object-selection/index.html) — iPad verified correct selection at every zoom level and after panning; additional controls and other devices unverified. [Research branch](../../tree/research/object-selection).

- **Experiment 17:** [Contextual Actions](experiments/contextual-actions/index.html) — iPad verified wood/water collection, inventory updates, and workshop supplies produced while water was selected; remaining controls not separately verified. [Research branch](../../tree/research/contextual-actions).

- **Experiment 18:** [Tap-to-Move and Obstacle Avoidance](experiments/tap-to-move/index.html) — iPad verified obstacle avoidance, two speeds and route toggles; roof and tree canopy collision corrections both verified on iPad; core experiment complete. [Research branch](../../tree/research/tap-to-move).
