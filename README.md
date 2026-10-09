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
- **Experiment 08:** [Animated Production Activity](experiments/production-activity/index.html) — implemented, awaiting device test
- Demos use pinned online PixiJS 8.21.0 scripts. Offline hosting is not yet tested.
