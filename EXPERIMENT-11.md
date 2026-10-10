# Experiment 11 — The Living Landscape

**Status:** Implemented, awaiting real-device testing. **Branch:** `research/combined-scene`.

## Objective
Determine whether individually successful low-complexity PixiJS effects remain visually coherent when combined: ambient butterflies/fireflies, grass movement, light rain with pond ripples, and sunset lighting.

## Implementation
One static landscape; independently toggled ambient life, rain, sunset, reduced motion, pause, and reset. Quiet Scene disables life/rain/sunset; Living Scene enables all three. Weather and lighting blend over time. Bounded geometry counts: 3 butterflies, 6 fireflies, 13 grass blades, 75 rain strokes maximum, 6 pond ripples. One ticker, one PixiJS app, pinned 8.21.0. No gameplay state or assets from existing games.

## iPad test
1. Select **Quiet scene**, then **Living scene**. Is the combined scene attractive or too busy?
2. Turn rain OFF while keeping ambient life and sunset ON; compare clarity.
3. Turn ambient life OFF while rain and sunset remain ON; note what is lost or improved.
4. Try reduced motion, pause/resume, and reset if convenient. Report any visual defects or lag.

## Verification
Unverified on real devices. No measured frame rate, battery, memory, or other-device results. Avoid treating multiple effects running as proof of performance headroom.

## Limitations
This is a composition test, not a reusable weather/lighting engine. The three controls are independent but the scene has simplified geometric art and no audio. Rain and sunset interpolation is gradual; creature motion and grass are direct per-frame procedural graphics. Reduced motion holds creatures and rain strokes in static positions rather than hiding them; this should be evaluated for comfort. Pause freezes visual time and transitions. Weather is cosmetic and does not affect game rules. No existing games modified.

## Potential future application
A small outdoor scene in Little Field Farm or Stranded Colony could benefit from combinations selected by art direction and gameplay readability; Haven's Reach might use subtler lighting and isolated exterior effects. All require separate project approval.
