# Experiment 13 — Viewport Culling

**Status:** Core viewport-culling behavior and smooth panning positively verified on iPad; numerical FPS and other devices unverified. **Branch:** `research/viewport-culling`.

## Objective
Compare animated-object updates for a fixed larger-than-viewport world, with and without skipping animation updates for offscreen objects. Test whether panning and re-entry remain visually correct.

## Implementation
PixiJS 8.21.0; 2400×1500 geometric landscape with 300 independently animated butterfly-like markers; 800×600 logical viewport. Touch drag and directional pan buttons move camera. Both modes hide offscreen sprites from drawing; **optimization ON** additionally skips their position/scale animation updates, while **OFF** updates all 300 each frame. Animations are functions of shared elapsed time, so re-entering objects should immediately display the current phase. Two-second approximate ticker FPS and number of animated objects updated each frame. No external profiling or GPU measurements.

## iPad test
1. Drag to explore. Does panning feel natural and do creatures appear correctly as you move?
2. At one location, compare optimization ON versus OFF. Updated/frame should be much lower with ON, 300 with OFF. Visible scene should look unchanged.
3. Compare approximate FPS readings. If both read 60, that does not invalidate the optimization; count reduction is the direct test.
4. Move far away and return. Look for frozen, jumping, or disappearing creatures.
5. Try directional buttons and Reset if convenient.

## Limitations
This isolates **animation update culling**, not full rendering optimization. Offscreen PixiJS objects are hidden in both modes. There is still a loop over all 300 objects to determine visibility, and the test does not measure CPU time, GPU load, memory, or battery. For very large worlds a spatial index or chunking may eventually be appropriate, but is outside this experiment. **User-reported iPad results (2026-10-10):** With visibility optimization ON, approximately 50 of 300 objects were updated per frame at the observed location. Scrolling was smooth with zero noticeable lag, and user could not see any visual difference between optimization ON and OFF. Relative to the OFF mode's designed 300 updates, this represents approximately 83% fewer object animation updates at that location. The user did not supply FPS numbers or separately describe return-to-area behavior. This does not establish an 83% reduction in CPU/GPU work, frame time, or battery use.

## Potential use
Large maps in Stranded Colony and Little Field Farm, if their actual scenes and approved architecture warrant it. No existing game modified.
