# Experiment 07 — Ambient Life

**Status:** Implemented; real-device testing pending. **Branch:** `research/ambient-life`.

## Question
Can a few small, independently animated creatures make a static meadow feel inhabited, without animal AI, pathfinding, gameplay simulation, or visual clutter?

## Implementation
PixiJS 8.21.0 pinned online. Static meadow/flowers built with Graphics; 5 butterflies, 12 fireflies and 3 distant birds are reusable display objects. One ticker updates positions, wing scales, and firefly alpha via simple periodic functions. Gentle activity shows 3 butterflies, 6 fireflies, 1 bird; Busy shows all. Ambient Life OFF hides creatures. Reduced Motion leaves them visible in static poses; Pause freezes current animation positions; Reset restores defaults. Mobile-responsive canvas and capped delta time.

## Test procedure
1. Open Experiment 07 through the dashboard; observe butterflies, fireflies, birds.
2. Compare Ambient Life ON versus OFF. Does the meadow feel more inhabited, and is any movement distracting?
3. Switch Activity Gentle / Busy. Which feels better? Does Busy become cluttered?
4. Enable Reduced Motion: creatures should remain visible but stationary.
5. Pause and Resume: positions should freeze and then continue.
6. Reset. Confirm default Gentle/ON/normal motion.

## Verification
Source implemented, but no user-reported device results yet. No measured FPS, battery, memory, accessibility preference detection, or cross-device testing.

## Candidate reuse
Little Field Farm: sparing butterflies near flowers or a few birds in the background, if approved and compatible with existing artwork. Stranded Colony: a little ambient life around safe, habitable biomes, without implying collectible wildlife or simulation. Haven's Reach: probably not appropriate for the command deck; consider only if a future location explicitly calls for visible distant life. These are **examples**, not authorizations.

## Limitations
Geometric placeholder creatures, not production sprites. Simple loops are not ecological behavior or physically realistic flight. More activity is intentionally offered for comparison, not presumed superior. The birds loop position rather than follow actual world paths. Reduced motion is an in-demo toggle, not OS setting. Avoid adopting a general entity/AI system based on this demo.

## Decision pending
Observe actual device behavior and compare perceived liveliness versus distraction; retain only the simplest useful technique.
