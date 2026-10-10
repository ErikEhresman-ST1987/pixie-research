# Experiment 12 — Mobile Rendering Headroom

**Status:** Perceived smoothness and displayed 60 FPS at Quiet, Normal, and Busy verified by user on iPad; visual-value comparison pending. **Branch:** `research/rendering-headroom`.

## Research question
How does the approximate browser-observed frame rate respond to different counts of lightweight animated elements in an otherwise unchanged PixiJS scene? Can fewer effects preserve a convincing presentation?

## Implementation
Static landscape, one PixiJS Graphics effects layer redrawn per ticker, pinned PixiJS 8.21.0. Three fixed settings:
- Quiet: 2 butterflies, 4 fireflies, 0 rain strokes, 2 ripples = **8** animated elements.
- Normal: 5 butterflies, 12 fireflies, 25 rain strokes, 5 ripples = **47**.
- Busy: 12 butterflies, 35 fireflies, 100 rain strokes, 14 ripples = **161**.
Displays active element count, activity level, and approximate observed FPS over two-second windows. Pause/resume and reset.

## iPad test
Select Quiet, Normal, and Busy for about ten seconds each. Report FPS reading for each, whether motion appears smooth, and whether Busy adds worthwhile visual quality or mostly clutter. Try Pause/Resume and Reset if convenient. The user need not run any external tool or access a developer console.

## User-reported iPad results (2026-10-09)

User reported that **all three activity levels were smooth**, including Busy (161 animated elements). This establishes perceived smoothness on the tested iPad, not proof of sustained frame-rate stability across longer sessions, GPU load, battery cost, or unused performance headroom. Follow-up: user reported the displayed frame-rate reading was **60 FPS at Quiet (8 elements), Normal (47 elements), and Busy (161 elements)**. These are user-observed approximate on-device readings, not independently instrumented measurements. Whether Busy looks meaningfully better than Normal is also unreported. Pause/Resume and Reset were not separately verified.

## Measurement limitations
FPS is derived from PixiJS ticker callbacks divided by elapsed wall time, not GPU frame timings. It can be capped by display refresh rate, browser scheduling, thermal/power conditions, or backgrounding. It is not an objective measure of battery use, memory, GPU load, or performance headroom. On its own, equal FPS at all settings does **not** prove equal cost. A more meaningful stress test or frame-time distribution would be a separate approved increment if justified. Rebuilding one Graphics object per frame is a simple experiment, not necessarily the optimal production architecture.

## Reuse
Potential performance budgeting lesson for Little Field Farm, Stranded Colony, and Haven's Reach, but no game code changed and no transfer approved. Prefer least visual activity that achieves the intended mood.
