# Experiment 11 — The Living Landscape

**Status:** Combined visual effect and individual feature on/off interactions positively user-verified on iPad; remaining controls and measured performance unverified. **Branch:** `research/combined-scene`.

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
**User-reported iPad observations (2026-10-09):** The combined scene was very effective visually. User played with switching features off and on. This supports successful visual composition and practical effect toggling, but does not establish that every toggle combination was exhaustively tested or that the scene achieved a measured frame rate. Reduced Motion, Pause/Resume, Reset, and other devices not separately reported. No measured frame rate, battery, or memory results. Avoid treating multiple effects running as proof of performance headroom.

## Limitations
This is a composition test, not a reusable weather/lighting engine. The three controls are independent but the scene has simplified geometric art and no audio. Rain and sunset interpolation is gradual; creature motion and grass are direct per-frame procedural graphics. Reduced motion holds creatures and rain strokes in static positions rather than hiding them; this should be evaluated for comfort. Pause freezes visual time and transitions. Weather is cosmetic and does not affect game rules. No existing games modified.

## Potential future application
A small outdoor scene in Little Field Farm or Stranded Colony could benefit from combinations selected by art direction and gameplay readability; Haven's Reach might use subtler lighting and isolated exterior effects. All require separate project approval.
