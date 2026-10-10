# Experiment 16 — Interactive Object Selection

**Status:** Core object selection across zoom levels and after panning verified on iPad. **Branch:** `research/object-selection`.

## Objective
Verify comfortable touch selection of scene objects, clear persistent highlights and information panel, and selection accuracy after panning and zooming.

## Implementation
PixiJS 8.21.0; a 1300×950 settlement in an 800×600 logical viewport, with three buildings, two trees and a pond. Simple explicit world-coordinate hit regions larger than the artwork, independent of PixiJS interaction routing; pointer movement threshold of 9 CSS pixels distinguishes tap from drag. Camera panning and three zoom presets (0.7×, 1×, 1.5×). Selection data and information panel live in JS/HTML, highlight is a separate Graphics overlay in world coordinates. Clear selection and reset. No game-state mutation.

## iPad test
Tap each type of object and confirm correct name, type, and highlight. Drag to pan; make sure drag does not accidentally select. Try Overview and Close-Up then tap objects again. Check highlight stays attached during camera movement and panel stays readable. Clear selection and Reset if convenient.

## Limitations
Hit regions are intentionally generous and may overlap; the reverse-order selection heuristic chooses the most recently defined matching object. The demo uses simple vector artwork, not production WebP sprites or irregular alpha-aware hit testing. This is an interaction prototype, not a reusable general-purpose picking engine. Pinch zoom, keyboard accessibility, and screen reader operation beyond basic labels have not been tested. **User-reported iPad results (2026-10-10):** The correct object was selected at every zoom level. Panning did not affect selection accuracy. User reported everything worked as intended. These observations verify the core touch-selection and camera integration on the tested iPad. Individual Clear selection / Reset operations, screen-reader accessibility, irregular hit shapes, and other devices were not separately verified.

## Potential reuse
Stranded Colony resource/building selection and Little Field Farm objects, subject to design review. No existing game modified.
