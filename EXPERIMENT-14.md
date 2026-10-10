# Experiment 14 — Reusable Particle Effects

**Status:** Reuse ON in Gentle and Busy observed at 60 FPS on iPad; reuse OFF comparison pending. **Branch:** `research/particle-recycling`.

## Research question
Can simple smoke, spark, and drifting-leaf effects reuse PixiJS Graphics objects instead of allocating and destroying replacements continuously, without visible changes or operator complexity?

## Implementation
PixiJS 8.21.0. A workshop scene with smoke, sparks, and leaves; 65 particles in Gentle mode and 180 in Busy. In Reuse ON, each particle's existing Graphics object is reset after its lifetime. In Reuse OFF, its Graphics is removed and destroyed and a new Graphics is created on expiry. Both modes share the same visual motion equations and a single ticker. The UI reports actual graphics creation and destruction counts since last reset, live particle count, and approximate observed FPS. Switching modes or density resets the counters and restarts effects. Reset does not change selected mode/density; pause freezes effects.

## iPad test
Watch Gentle with Reuse ON for 15–20 seconds; record New graphics created and approximate FPS. Toggle Reuse OFF and wait similarly; record counts and FPS. Repeat Busy if convenient. Are the effects visually similar and smooth? Do creation/destruction counters increase continually only when Reuse OFF? Test pause/resume if convenient.

## User-observed iPad results (2026-10-10)

Screenshots show **Reuse ON** in both activity modes: Gentle displayed 65 new Graphics, 0 destroyed, 65 live particles, and 60 approximate FPS; Busy displayed 180 new Graphics, 0 destroyed, 180 live particles, and 60 approximate FPS. User reports the appearance is not different. These screenshots compare density settings, not ON vs OFF recycling. It is not yet confirmed whether counters continually rise in OFF mode, whether visual quality is identical across recycling modes, or whether both sustain 60 FPS. A screenshot cannot establish how long the counters were observed.

## Interpretation and limits
The pool retains exactly the current active particle objects rather than dynamically sizing or sharing a generic reusable engine. With Reuse ON, allocations should stop after initial population; OFF continuously replaces particles. The displayed counters count Graphics construction/destruction only, not actual heap allocation or garbage collector activity. Both modes redraw per object via position/alpha/scale/rotation updates. A 60 FPS reading in both does not prove equivalent cost or long-session behavior. Device memory, battery, GC pauses, and sustained performance are not instrumented. The scene uses simple primitives, not approved production art.

## Potential reuse
Localized smoke, sparks, dust, leaves, or similar lightweight effects in existing games, subject to separate review and approval. No existing game files modified.
