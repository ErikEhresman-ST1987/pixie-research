# Experiment 15 — Smooth Camera Zoom

**Status:** Core zoom transition and drag-panning behavior verified on iPad; raster-art clarity, pinch zoom, numerical FPS and reset not separately verified. **Branch:** `research/camera-zoom`.

## Objective
Evaluate camera zoom, smooth interpolation, and drag panning for a PixiJS 2D world without scaling HTML controls. Test comfort, edge clarity, and continuity.

## Implementation
PixiJS 8.21.0, one 1300×950 vector-based settlement, fixed logical viewport of 800×600, three zoom presets (0.65×, 1×, 1.65×), camera center clamping, pointer drag, exponential frame-time-based interpolation for zoom and target center, instant/smooth toggle, reset, approximate ticker FPS. World rendered as one PixiJS Container; controls remain ordinary responsive HTML outside the canvas. No production game files changed.

## iPad test
Try Overview, Normal, Close-Up, and drag at each level. Compare smooth transition ON/OFF. Does zooming feel natural and remain legible? Is drag smooth? Does artwork look crisp in Close-Up? Are any edges clipped, any jumps, or unintended blank areas? Observe approximate FPS if convenient. Test reset.

## Limitations
This uses vector Graphics only. It does **not** establish whether WebP raster art stays crisp at different scales, whether pinch-to-zoom works (not implemented), or how zoom affects complex sprite-heavy scenes. FPS is a ticker estimate, not a GPU benchmark. **User-reported iPad observations (2026-10-10):** Panning had no noticeable lag. Visual appearance was the same with smooth transitions ON or OFF. With smooth transitions OFF, zoom changes were instant; with smooth transitions ON, transitions were described as very pleasant. User considered the test successful. No numeric FPS, explicit Close-Up edge-clarity assessment, reset test, or pinch-to-zoom test was reported.

## Potential reuse
Stranded Colony map navigation, Little Field Farm expanding land views, or Haven's Reach spatial scenes, only if individually approved and suited to the canonical design.
