# Experiment 01 — Scene Layering

**Status:** Implemented; awaiting browser/device verification. **Branch:** `research/scene-layering`

## Objective
Learn PixiJS v8 container hierarchy, drawing order, interactive objects, and state-driven visual changes with the smallest useful demonstration.

## How to run
Open `index.html` in a modern browser with internet access. It loads PixiJS **8.21.0** from a pinned CDN URL. If local-file browser restrictions interfere, serve the directory with a basic static HTTP server. This first proof is **not offline-ready**.

## What to test
1. The blue pond stays behind the path and objects.
2. The yellow marker begins in front of the gray wall; use **Send marker behind wall** to switch its layer.
3. Click/tap the marker to select/deselect it; the status text updates.
4. Use **Move marker** to reposition it; its selection and layer state should persist.
5. Resize the viewport and confirm the canvas fits without clipping its controls.

## Implementation
- `world` contains separate `terrain`, `behindWall`, `structures`, and `foreground` containers.
- Reparenting the marker changes occlusion without duplicating its drawing code.
- Plain JavaScript owns marker position, selected state, and layer choice. Pixi renders that state.
- Controls are HTML buttons for clear touch targets.

## Verified results
None yet. Successful commit is **not** browser or device verification.

## Reusable portions
**Candidates, not yet validated:** container-based scene layering, reparenting for depth changes, simple state-to-render updates, and HTML/Pixi separation.

## Limitations and open questions
- No artwork, persistence, animation, camera, or dynamic depth sorting.
- CDN dependency means this proof requires internet; local vendoring can be tested separately.
- Needs iPhone/iPad/desktop interaction and resize checks.
- Reparenting is demonstrated for one object only; performance with many moving objects is untested.

## Complexity / performance
Expected low complexity; actual performance not measured.

## Next step
Run the demo, record observed results here, and decide what (if anything) to promote to `main`.
