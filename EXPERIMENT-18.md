# Experiment 18 — Tap-to-Move and Obstacle Avoidance

**Status:** Core navigation and both roof/tree collision corrections verified on iPad. **Branch:** `research/tap-to-move`.

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
User reported the test was fun; pathfinding avoided obstacles, normal and fast walking both worked, and route display ON/OFF both worked. Destinations did not stop on obstacles, except that the settler could walk into the visually drawn house roofs while avoiding the main house bodies. This is a genuine discrepancy between collision rectangles and drawn artwork. Corrected both house navigation rectangles to include full visible roof extents (with existing 14px cell inflation unchanged), on the research branch and published preview. **Roof retest passed:** user reported roof avoidance worked perfectly. A follow-up screenshot showed the settler at the top of a tree canopy, revealing the same artwork-vs-collision mismatch for trees. Both tree blockers were enlarged to include visible canopy extents plus existing grid inflation. **Tree retest passed:** user reported the correction worked and everything was working well.

## Follow-up: tree canopy correction
User's iPad screenshot showed the yellow settler apparently overlapping the top of the lower tree. Enlarged both tree navigation rectangles to encompass the full drawn foliage and trunk, rather than only the smaller central region. The pathfinding algorithm and movement settings are unchanged. This update is implemented on the research branch and published preview; canopy avoidance subsequently verified by user on iPad.

## Final iPad verification — 2026-10-10
After the expanded tree-canopy collision bounds were published, the user confirmed: “That fix worked everything is working well.” The core tap-to-move experiment is complete: navigation around obstacles, normal/fast speed, route overlay ON/OFF, roof avoidance after correction, and tree-canopy avoidance after correction were user-tested successfully. No quantitative pathfinding timings or cross-device results were collected. **Reusable lesson:** validate navigation blockers against complete visible art (including roof overhangs and foliage), not merely central object footprints.
