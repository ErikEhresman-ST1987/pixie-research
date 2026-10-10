# Experiment 18 — Tap-to-Move and Obstacle Avoidance

**Status:** Implemented; iPad testing pending. **Branch:** `research/tap-to-move`.

## Objective
Test whether a single character can navigate naturally toward a tapped location without passing through buildings, water or trees, with clear route feedback and low-friction iPad input.

## Implementation
PixiJS 8.21.0, 800×600 vector scene, one moving settler, five blocked objects, fixed 20-pixel grid, an A*-style grid search with 8-direction movement, corner-cut prevention and inflated obstacle hit regions. Tap maps canvas coordinates to the grid; blocked destinations snap to the nearest open cell. A visible path overlay can be switched on/off. The settler moves along waypoints at normal or fast speed; tapping again replaces the route. Reset and approximate FPS readout included. Path computation occurs per tap, not each frame. No existing game modified.

## iPad test
Tap on the opposite side of a building or pond: does the settler route around it instead of walking through? Tap somewhere else while walking: does the route change naturally? Tap inside a building: is the destination moved to accessible ground? Compare route visibility ON/OFF, normal/fast walking, and reset. Report visual smoothness or any strange detours.

## Limitations
This is a deliberately small fixed grid, not a production pathfinding engine. The search uses a simple linear open-set scan rather than a priority queue. Paths can look angular, and nearest-open snapping does not guarantee the nearest **reachable** destination if there are disconnected regions. The world is static, with no crowd avoidance, collision physics, dynamic buildings, sprite animation, save/restore or camera pan/zoom. FPS is an approximation; no real-device results yet.

## Potential reuse
Settler navigation in Stranded Colony and character movement in Little Field Farm, only with separate game-specific design approval.
