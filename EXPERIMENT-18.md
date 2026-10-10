# Experiment 18 — Tap-to-Move and Obstacle Avoidance

**Status:** Core navigation behavior verified on iPad; roof collision issue identified and correction published, awaiting focused retest. **Branch:** `research/tap-to-move`.

## Objective
Test whether a single character can navigate naturally toward a tapped location without passing through buildings, water or trees, with clear route feedback and low-friction iPad input.

## Implementation
PixiJS 8.21.0, 800×600 vector scene, one moving settler, five blocked objects, fixed 20-pixel grid, an A*-style grid search with 8-direction movement, corner-cut prevention and inflated obstacle hit regions. Tap maps canvas coordinates to the grid; blocked destinations snap to the nearest open cell. A visible path overlay can be switched on/off. The settler moves along waypoints at normal or fast speed; tapping again replaces the route. Reset and approximate FPS readout included. Path computation occurs per tap, not each frame. No existing game modified.

## iPad test
Tap on the opposite side of a building or pond: does the settler route around it instead of walking through? Tap somewhere else while walking: does the route change naturally? Tap inside a building: is the destination moved to accessible ground? Compare route visibility ON/OFF, normal/fast walking, and reset. Report visual smoothness or any strange detours.

## Limitations
This is a deliberately small fixed grid, not a production pathfinding engine. The search uses a simple linear open-set scan rather than a priority queue. Paths can look angular, and nearest-open snapping does not guarantee the nearest **reachable** destination if there are disconnected regions. The world is static, with no crowd avoidance, collision physics, dynamic buildings, sprite animation, save/restore or camera pan/zoom. FPS is an approximation; iPad user-reported core behavior verified; roof-overhang correction not yet retested.

## Potential reuse
Settler navigation in Stranded Colony and character movement in Little Field Farm, only with separate game-specific design approval.

## iPad results and correction — 2026-10-10
User reported the test was fun; pathfinding avoided obstacles, normal and fast walking both worked, and route display ON/OFF both worked. Destinations did not stop on obstacles, except that the settler could walk into the visually drawn house roofs while avoiding the main house bodies. This is a genuine discrepancy between collision rectangles and drawn artwork. Corrected both house navigation rectangles to include full visible roof extents (with existing 14px cell inflation unchanged), on the research branch and published preview. **Retest pending** for roof avoidance and any new awkward detours. Do not classify the collision fix as user-verified yet.
