# Experiment 03 — Visual State Changes

**Status:** Implemented, awaiting real-device verification. **Branch:** `research/visual-state-changes`.

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
None yet; committed code is not a device test.

## Reusable candidates
- State-to-appearance mapping without duplicating game-state ownership.
- In-place Graphics redraw and Text update.
- Multiple independent touch targets with shared rendering logic.
- Redundant visual signals: color, outline, and symbol.

## Limitations
No persistence, animation, gameplay consequences, asset loading, performance benchmark, or cross-device verification. The tile labels are generic, and this is not a usability study of actual game art. Uses PixiJS 8.21.0 from a CDN; offline operation not tested.

## Complexity and payoff
Expected low complexity and high reuse potential, pending device observation.

## Next step
Record the user's actual test results, including any interaction or clarity problems, before declaring the technique verified.
