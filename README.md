# Pixie Research

A lightweight, incremental PixiJS learning laboratory and reference library.

## One-place testing

- **Dashboard source:** [index.html](index.html)
- **Experiment 01:** [Scene Layering](experiments/scene-layering/index.html)
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

- Scene Layering: implemented, not yet browser/device verified.
- The demo currently uses a pinned online PixiJS 8.21.0 script. Offline hosting is not yet tested.
