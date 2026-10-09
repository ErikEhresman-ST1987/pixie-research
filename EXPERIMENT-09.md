# Experiment 09 — Time of Day and Lighting

**Status:** Implemented; real-device verification pending. **Branch:** `research/time-of-day-lighting`.

## Research question
Can a single unchanged landscape read as day, sunset, and night using only cheap tint overlays, warm window lighting, stars, and shadows, without a dynamic lighting engine?

## Implementation
PixiJS 8.21.0 CDN, one responsive scene with fixed hills, house, pond, trees and sky. A tinted translucent overlay changes atmosphere; window lights and stars are toggled by alpha, and shadows adjust. Day, Sunset, Night buttons choose state. Optional eased transitions use one ticker; Transitions OFF and Reduced Motion use instant changes. Reset returns to day. The scene artwork is not regenerated or swapped.

## iPad test
1. Compare Day, Sunset, Night. Does each read clearly and preserve scene visibility?
2. Are the warm house windows at night convincing or too bright?
3. Compare transitions ON/OFF; do gradual changes help, or distract?
4. Reduced Motion should change states instantly; Reset should return to day.

## Verification and limits
Awaiting user test. No performance or battery measurements; no other device tested. These are illustrative flat-color lighting overlays, not physically accurate light/shadow simulation. Color/tint switching is immediate even when alpha transitions are gradual; watch for noticeable color jumps between sunset and night. The scene's built-in lights do not affect actual world geometry.

## Potential reuse (not authorization)
Stranded Colony settlement time-of-day mood, Little Field Farm gentle dusk scene, and Haven's Reach exterior views only if compatible with approved art and mechanics. No changes to those projects.

## Decision pending
Evaluate visual readability and emotional payoff against one static scene. Keep, refine, or reject based on real-device observations.
