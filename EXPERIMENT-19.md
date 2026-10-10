# Experiment 19 — Walk to an Object and Act

**Status:** Implemented; awaiting iPad verification. **Branch:** `research/walk-and-act`.

## Objective
Combine contextual object actions and grid pathfinding so an action changes authoritative state only when the settler reaches a safe nearby location. Verify replacing and canceling pending commands.

## Implementation
PixiJS 8.21.0, fixed 800×600 settlement, 20px navigation grid, pond/tree/workshop with art-aware inflated obstacle blockers, and one settler. Tap selects an object and exposes a single relevant action in a separate HTML panel. Action requests compute a path to an unblocked adjacent approach cell. The settler follows the route; on arrival the JavaScript inventory is updated. Replacing a command overwrites the prior route and pending action. Cancel removes pending command and route. Route overlay and normal/fast speeds are independently adjustable. No persistent save or changes to existing games.

## iPad test
1. Tap pond and Collect Water; check that water remains 0 while walking, then increases by one only upon arrival.
2. Repeat for Old Oak and Workshop. Character should stop near the artwork, not inside foliage or roofs.
3. From far away, issue Collect Water, then before arrival tap Old Oak and Collect Wood. Only wood should increase; water should not.
4. Try Cancel while moving; no action should complete. Try route ON/OFF, normal/fast speed and Reset if convenient.

## Limits
The grid search uses a linear minimum-distance scan, adequate for this small scene but not a production navigation engine. A new command replaces a prior one; there is no queue. Objects can be harvested indefinitely, and inventory is in memory only. No camera pan/zoom, moving obstacles, crowd avoidance, persistence, offline progression or production art. A route is computed once per issued command; no dynamic replanning. No real-device verification yet.

## Potential reuse
Stranded Colony settler tasks or Little Field Farm workers if approved in the relevant game's own design process.
