# Pixie Research — Findings and Future Game Connections (Experiments 01–05)

**Date:** 2026-10-09 · **Status:** Research reference, not implementation authorization.

## Purpose and decision boundary
Preserve actual iPad observations and credible examples of future reuse. These examples are *candidates*, not changes to existing games, art direction, approved scopes, or repositories. Any transfer into Little Field Farm, Stranded Colony, or Haven’s Reach requires a separate project-specific review, approval, and smallest meaningful increment. Follow the project graphical principles: the renderer presents; authoritative game state owns truth. Favor high benefit per total complexity, comfortable mobile headroom, and real-device proof.

## Observed results versus inference

| Experiment | Tested observation | Reusable technique | Evidence limit |
|---|---|---|---|
| 01 Scene Layering | On iPad Safari, the marker moved, touch selection worked, and foreground/background wall ordering worked | Small, purposeful world layers and occlusion | Other devices and busy scenes not verified |
| 02 Automatic Depth Sorting | On iPad Safari, dragging was smooth; moving character passed correctly in front of/behind scenery; ON/OFF comparison worked | Ground-contact Y-based z-order in a sortable container | Larger scenes and other devices not verified |
| 03 Visual State Changes | User reported tiles and state changes worked as expected, looked beautiful, and felt instant | Data-driven state appearance, updating existing display objects | No instrumented latency, other devices not verified |
| 04 Simple Animation | On iPad, float/pulse/move looked smooth; Pause froze current positions; Resume continued; Reduced Motion stopped and centered objects | One shared ticker, transform/alpha motion, pause and reduced-motion modes | Reset not independently reported; no FPS/battery metrics |
| 05 Environmental Atmosphere | On iPad, ripples suggested fish or breeze, light suggested a subtle setting sun, and drifting mist created strong atmosphere; user rated this the coolest experiment yet | Inexpensive ripples, drifting translucent layers, simple lighting overlay | Strong qualitative visual-payoff result; control tests and long-term performance unverified |

**Finding:** A few selective visual cues can suggest a living world without simulating all implied activity. This is a user-observed payoff and a design hypothesis worth reusing, **not** a measured performance or general cross-device guarantee.

## Candidate connections for existing games (examples only)

| Game | Potential use of validated techniques | What it could improve | Boundary / review before transfer |
|---|---|---|---|
| **Little Field Farm** | Scene layering for crops, animals, and structures; visual states for growing/ready/producing; small bakery/creamery activity pulse; restrained pond/stream ripples or morning mist **only if such scenery belongs in approved art** | Clear progress, spatial coherence, cozy sense of life | Do not replace approved assets or invent scenery; preserve existing farming logic and local saves; use restrained motion and touch-size checks |
| **Stranded Colony** | Ground-based depth sorting for explorers and trees; state appearance for research/buildings/harvestable objects; localized water, fog or warm-light effects where scenes justify them | Readable consequences, believable exploration, environmental identity | Honor approved top-down tile presentation and existing PixiJS architecture; no game-state changes from graphics; do not treat decorative fog as gameplay fog-of-war |
| **Haven’s Reach** | Stable Wayfarer cockpit foreground with independently changing external view; status-indicator state changes; subtle beacon, starfield or exterior haze/light effects | Ship identity, location feedback, lived-in atmosphere | Preserve approved command-deck reference, existing navigation/state ownership, and project pause; avoid unnecessary whole-screen redraws or dramatic lighting |
 
### Transfer rule
For each future candidate, write: (1) the actual player benefit; (2) simplest static/no-effect baseline; (3) assets and engineering cost; (4) mobile performance/visibility checks; (5) how to disable/remove it without corrupting state; (6) explicit project approval. Reuse a **small recipe**, not a general effects engine.

## Next research step
Experiment 06 — **Local Environmental Reactions**: compare a still scene against short, localized responses to pointer/touch (grass bending, a water ripple, and a soft touch highlight). Measure qualitatively whether the world feels responsive without overwhelming the scene. Keep interactions visual only, and document controls and device observations separately.
