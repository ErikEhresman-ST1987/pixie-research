# Experiment 01 — Scene Layering

**Status:** Core scene layering and touch selection verified on iPad Safari (user-reported, 2026-10-09); broader device/performance checks pending. **Branch:** `research/scene-layering`

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
- **User-reported iPad Safari test (2026-10-09), on the deployed GitHub Pages demonstration:** after the canvas sizing fix, the marker moved between positions and could be placed both behind and in front of the wall; the layering effect was visible and functional.
- This verifies the core single-marker visual layering interaction on that device. The user also confirmed selecting the yellow marker by touch on either side of the wall, with the marker both in front of and behind the wall. Status-text behavior, selection-state persistence, other devices, and measured performance have not been separately verified.
- **Deployment note:** The working demo tested by the user is hosted at `main/experiments/scene-layering/index.html`; the branch-root `index.html` remains the earlier exploratory version. Refer to the deployed demo for this observed result.

## Reusable portions
**Observed working on iPad Safari:** basic container layering, marker reparenting for occlusion, touch selection across tested positions/layers, and button-driven visual state changes in the deployed demonstration. **Not yet validated as general-purpose modules:** cross-device behavior, scalability, and performance.

## Limitations and open questions
- No artwork, persistence, animation, camera, or dynamic depth sorting.
- CDN dependency means this proof requires internet; local vendoring can be tested separately.
- iPad Safari core interaction was user-tested; iPhone, desktop, status-text updates, selection persistence, and resize/orientation checks remain unverified.
- Reparenting is demonstrated for one object only; performance with many moving objects is untested.

## Complexity / performance
Expected low complexity; actual performance not measured.

## Next step
Core iPad interaction goal achieved. Keep this as a working reference; optionally verify orientation and additional devices when needed. Do not assume broad performance or cross-device validation.
