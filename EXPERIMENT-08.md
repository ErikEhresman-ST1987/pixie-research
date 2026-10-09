# Experiment 08 — Animated Production Activity

**Status:** Implemented, awaiting real-device verification. **Branch:** `research/production-activity`.

## Objective
Test whether lightweight production animation makes work status readable and appealing, while ensuring presentation follows authoritative activity state rather than creating it.

## Implementation
PixiJS 8.21.0 pinned CDN. A static workshop with a rotating wheel, rising/fading smoke puffs, and a visible progress bar. Plain JavaScript state tracks ready/working/complete, progress, paused, effects visibility, and reduced motion. A 12-second simulated job provides a testable sequence. A single ticker advances progress independently of the optional visual effects; animations are updated in-place, not recreated per frame. Start, Pause/Resume, Effects ON/OFF, Reduced Motion, and Reset are controls.

## iPad test
1. Open Experiment 08 via dashboard and start a job.
2. Verify the wheel turns, smoke rises, and the progress bar advances to COMPLETE.
3. Pause partway through; progress and motion should stop. Resume and verify both continue.
4. Start a new job, switch Effects OFF; progress should still advance and finish.
5. Turn Reduced Motion ON; progress should continue while wheel and smoke stop moving.
6. Reset; confirm ready state and empty progress bar.

## Verification
Not yet tested by the user. No measured FPS, long-term battery, cross-device compatibility, or offline verification.

## Reuse candidates
- Little Field Farm bakery/creamery: display activity while existing production state remains authoritative.
- Stranded Colony crafting/building: show progress and equipment activity without coupling animations to work simulation.
- Haven’s Reach: subtle equipment status if consistent with the approved cockpit design.

**All candidates are examples only, not authorization to modify existing projects.**

## Limitations
A simplified decorative workshop, not a game production model. No offline catch-up, persistence, recipe logic, inventory, NPC workers, sprite assets, or particle engine. Timer duration is only a demo convenience, not a gameplay recommendation. Smoke is a handful of simple shapes, not realistic fluid simulation. Reduced Motion holds static smoke in place; test visual clarity.

## Decision pending
Record user observations about readability, visual payoff, and whether animations distract from the progress display.
