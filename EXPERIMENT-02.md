# Experiment 02 — Automatic Depth Sorting

**Status:** Implemented, awaiting real-device testing. **Branch:** `research/automatic-depth-sorting`.

## Objective
Test whether sorting scene objects by their ground-contact Y coordinate makes a character naturally appear in front of or behind obstacles without manual layer buttons.

## Implementation
PixiJS v8.21.0. A world container contains ground and a sortable object container. Three obstacles and a draggable character each use their ground-contact point as their container origin. When automatic sorting is enabled, the character's `zIndex` follows its Y position; obstacle `zIndex` values use their fixed Y positions. PixiJS `sortableChildren` and `sortChildren()` establish drawing order. Fixed mode sets the character above everything to provide a comparison. Plain HTML controls and a capped canvas support touch-first use.

## How to run
From the [single research dashboard](https://erikehresman-st1987.github.io/pixie-research/), choose Experiment 02. It currently loads PixiJS from a pinned CDN and requires internet access.

## Test procedure
1. Drag the yellow character upward behind the tree at left; it should be partly hidden when its feet are above the tree's base.
2. Drag downward below that tree; the character should appear in front.
3. Repeat with the central tree and gray stone.
4. Switch automatic sorting OFF. The character should remain in front regardless of position.
5. Switch sorting ON and use Reset. Verify controls and drag behavior on iPad Safari.

## Results
Not yet tested on a real device. Committed code is not proof of browser execution.

## Reusable candidates
- `sortableChildren` and `zIndex` using world Y coordinates.
- Consistent ground-contact anchor convention for illustrated objects.
- Touch dragging with coordinate conversion from screen to world.
- Toggle between comparison modes for visual research.

## Limitations
- Works as a simple 2.5D visual illusion, not collision detection or pathfinding.
- Single movable character, three static obstacles; no performance or scale benchmark.
- Tall or irregular artwork can require more precise sorting anchors or multiple visual parts.
- No persistence, animation, artwork pipeline, offline mode, or verified cross-device behavior.

## Complexity / payoff
Expected low-to-moderate implementation complexity with potentially high reuse; practical value and performance remain unverified.

## Next step
Collect actual iPad observations, record any failures, then decide whether this is a useful reference example.
