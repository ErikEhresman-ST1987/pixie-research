# Experiment 10 — Weather and Rain

**Status:** Light rain, heavy rain, and weather transitions visually verified on iPad; remaining controls and performance unverified. **Branch:** `research/weather-rain`.

## Research question
Can an unchanged landscape convincingly communicate clear weather, light rain, and heavy rain using simple falling strokes, pond ripples, and a cool overlay rather than a particle engine or weather simulation?

## Implementation
PixiJS 8.21.0; static landscape with pond, tree, and cabin. Ninety-five deterministic raindrop positions are reused, with count scaled by weather intensity. Seven simple expanding ellipse ripples appear on the pond. A cool translucent overlay increases with intensity. A single ticker updates movement and transitions. Clear/Light/Heavy buttons, Transitions ON/OFF, Reduced Motion, Pause/Resume, and Reset. Reduced Motion freezes raindrops and ripples but preserves the selected visual density.

## iPad test
1. Compare Clear, Light rain, Heavy rain. Does the weather read immediately and does the cabin remain visible?
2. Observe water ripples. Do they make the rain more believable?
3. Switch Clear → Heavy → Light with Transitions ON; is the change gradual and visually natural?
4. Switch Transitions OFF and compare.
5. Pause/Resume, Reduced Motion, Reset. Look for distracting or stuck artifacts.

## Verification
**User-reported iPad results (2026-10-09):** Light rain and heavy rain looked excellent, and transitions between conditions worked well. This verifies qualitative visual effectiveness of both rainfall intensities and perceived transition behavior. The user did not separately report pond ripple quality, Pause/Resume, Reduced Motion, Reset, or precise performance. No frame-rate, memory, battery, or cross-device measurements.

## Potential reuse (examples, not authorization)
Stranded Colony weather mood in explored areas; Little Field Farm rainfall around fields/pond; Haven's Reach exterior views only if appropriate to location and approved art. No game code modified.

## Limitations
Geometric placeholder art; no rain sound, splash physics, wind model, puddle growth, gameplay weather effects, or persistent state. Rendering redraws the rain graphics per frame, which is acceptable for a bounded prototype but should be measured before production reuse. Rain speed uses selected weather category rather than interpolated intensity, so motion speed may shift immediately even when visual density fades. This test is about visual believability, not meteorology.

## Decision pending
Record actual iPad visual response, perceived naturalness, distraction, and any control issues.
