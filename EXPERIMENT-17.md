# Experiment 17 — Contextual Actions

**Status:** Implemented; iPad testing pending. **Branch:** `research/contextual-actions`.

## Research question
Can object-specific actions be exposed in a readable HTML panel without covering the PixiJS scene, while selection, zoom, pan, and an independent timed activity remain reliable?

## Implementation
PixiJS 8.21.0. Four objects: workshop (Start Work, Inspect), pond (Collect Water, Inspect), tree (Collect Wood, Inspect), storehouse (View Inventory, Inspect). Touch selection uses world-coordinate hit regions and drag threshold, with a scene highlight and HTML action panel. Camera supports three zoom presets and drag panning. Plain JavaScript game state tracks supplies, water, wood and an eight-second simulated workshop job; the job advances via ticker even when another object is selected. Actions update state and refresh the panel, without requiring an animation to finish. Reset clears state; no persistence.

## iPad test
1. Tap each object. Are only its relevant actions shown, and are they readable?
2. Collect water and wood, inspect storehouse and verify the totals.
3. Start Workshop job, select the pond or storehouse while it runs, and return after about eight seconds. Has a supply been produced without needing to keep the workshop selected?
4. Pan and zoom; select and act again. Confirm the panel remains separate from the scene.
5. Clear selection and Reset if convenient.

## Limits
This is a minimal action-state experiment, not a production action system. Resource gathering is unlimited, inventory is ephemeral, and the job advances only while the page's ticker runs (no background/offline completion). There are no queues, save/restore, game balancing, or complex accessibility validations. No real-device results yet.

## Potential reuse
Stranded Colony's building/resource actions and Little Field Farm's machines, subject to separate game-specific approval. No existing games changed.
