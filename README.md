# Experiment 03 — Visual State Changes

**Status:** Core interaction verified on iPad (user-reported, 2026-10-09); broader testing pending. **Branch:** `research/visual-state-changes`.

## Objective
Test whether touch-driven state changes can update existing PixiJS display objects clearly without rebuilding the scene or making the renderer the authority for state.

## Implementation
Six independent interactive tiles cycle through Available, Selected, Active, and Complete. A plain JavaScript `data` array stores their authoritative state indices; PixiJS `Graphics` and `Text` objects are updated in place by `draw(i)`. Each state has a different color, outline, and symbol. A reset button returns all tiles to Available.

## Test
1. Open Experiment 03 from the [Pixie Research dashboard](https://erikehresman-st1987.github.io/pixie-research/).
2. Tap each tile repeatedly and confirm the four-state cycle is Available → Selected → Active → Complete → Available.
3. Change multiple tiles independently and check that other tiles retain their state.
4. Tap Reset all tiles; every tile should return to Available.
5. Observe whether colors, symbols, and touch targets are clear on iPad Safari.

## Verified results
- **User-reported iPad test (2026-10-09):** Everything worked as expected; visual appearance was described as beautiful and changes as instantaneous.
- This supports the core touch-driven visual state demonstration on the tested device, including the overall intended behavior. Exact timing was not instrumented or measured.
- Cross-device compatibility, performance at scale, and offline behavior remain unverified.

## Reusable candidates
- State-to-appearance mapping without duplicating game-state ownership.
- In-place Graphics redraw and Text update.
- Multiple independent touch targets with shared rendering logic.
- Redundant visual signals: color, outline, and symbol.

## Limitations
No persistence, animation, gameplay consequences, asset loading, performance benchmark, or cross-device verification beyond the reported iPad test. The tile labels are generic, and this is not a usability study of actual game art. Uses PixiJS 8.21.0 from a CDN; offline operation not tested.

## Complexity and payoff
Expected low complexity and high reuse potential, pending device observation.

## Next step
Keep as a successful iPad-tested reference. Test other devices or larger object counts only if future reuse requires it.
