# Experiment 04 — Simple Animation

**Status:** Core animation behavior user-verified on iPad (2026-10-09); wider device/performance testing pending. **Branch:** `research/simple-animation`.

## Objective
Test three inexpensive time-based presentation effects—floating, pulsing, and horizontal movement—without coupling gameplay state to animation frames. Test pause and reduced-motion controls.

## Implementation
PixiJS v8.21.0 via CDN. One Pixi ticker advances elapsed animation time (capped per frame to avoid giant jumps after a suspended tab). A single paint function derives three display properties from elapsed time: orb Y position, beacon halo scale, and marker X position. The underlying objects and their conceptual states are unchanged. Pause stops time advancement; reduced motion sets amplitude to zero and restores static reference positions; Reset restores defaults. Responsive canvas uses world scaling and a capped height.

## Test procedure
1. Open Experiment 04 from the [research dashboard](https://erikehresman-st1987.github.io/pixie-research/).
2. Observe smooth floating, pulsing, and horizontal motion simultaneously.
3. Tap Pause motion and verify all three stop; Resume should continue.
4. Toggle Reduced motion ON: all objects should hold still even while playing. Toggle OFF to resume animation.
5. Tap Reset motion: default motion should return.
6. Report clarity, smoothness, and any battery/heat or responsiveness concern noticed (no instrumented performance measurement).

## Verified results
- **User-reported iPad test (2026-10-09):** All three animations moved smoothly. Pause froze the objects at their current positions and Resume restarted motion. Reduced Motion stopped all motion and centered the objects at their static reference positions. Switching back allowed motion to resume. User reported everything worked as expected.
- These are qualitative observations, not measured frame rates, power consumption, or performance benchmarks. Reset was not separately described in the report.
- Cross-device behavior and OS-level reduced-motion integration remain unverified.

## Reusable candidates
- Single shared Pixi ticker with frame-time cap.
- Pure presentation updates based on elapsed time.
- Cheap sine-wave float, pulse, and positional animation.
- Pause, reset, and reduced-motion toggles.

## Limitations
Not a game system, physics engine, sprite-sheet animation, or performance benchmark. No audio, persistence, offline operation, or cross-device verification. Reduced motion is an explicit in-demo control, not yet wired to OS accessibility preferences. Rendering still uses an online CDN.

## Complexity / payoff
Expected low implementation complexity; value and device performance pending user testing.

## Next step
Keep this as a successful iPad-tested reference. Check Reset, other devices, and longer-running performance only when relevant to future reuse.
