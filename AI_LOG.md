# AI_LOG.md — STARWEAVER practice build

## Tool: Google Stitch
- Purpose: Generate a visual design and HTML export for an original puzzle-arcade interface.
- Output files received: `code.html`, `screen.png`, `DESIGN.md`.
- Export action: Stitch `.zip` export.
- Date: 2026-10-23 (local date; based on the work session).

## Prompt evidence
The initial prompt described a responsive cosmic puzzle arcade named STARWEAVER, with a midnight-indigo background, cyan/turquoise paths, violet/coral accents, a mascot, start/level/gameplay/success screens, and a tile-rotation puzzle guiding energy from a comet to a portal. It requested clear instructions, move count, Hint, Undo, Restart, sound controls, desktop/mobile usability, animation states, and a vanilla HTML/CSS/JavaScript implementation.

A follow-up refinement prompt requested a larger puzzle board, clearer objective and controls, less decorative clutter, and preservation of the existing visual identity.

## What was generated
- A single exported HTML file, a screenshot, and a design-system Markdown file.
- The HTML contains JavaScript interactions for tile rotation and several controls; this must be tested before relying on it.
- The Stitch preview page showed an error, but the canvas and ZIP export were still available.

## AI mistakes / fixes
The following genuine issues were identified in the Google Stitch export:
- Observed issue 1 (Fake Single-Tile Path Validation): Victory was triggered solely by checking `tile.id === 'criticalTile'` and `nextRot === 180`. Breaking earlier nodes in the circuit (e.g. Node 0,0 or Node 0,1) did not interrupt flow, and rotating Node 2,3 falsely triggered completion even on broken circuits.
  - How it was reproduced: In `index.html`, rotating Node 0,0 disconnected the source from the grid, but clicking Node 2,3 still popped the victory modal and declared the stream harmonized.
  - AI prompt used to fix it: "Implement genuine path validation from the source to the portal using compatible connections between neighbouring tiles."
  - Verification performed: Automated BFS circuit simulation in Chrome verified that rotating Node 0,0 immediately drops stream integrity from 71% to 0% and turns all downstream conduits dormant.
- Observed issue 2 (Tile 11 Base Geometry Mismatch): Tile 11 had base SVG path `M 0 50 L 50 50 L 50 0` with initial `rotate-90`. Rotating 90° clockwise to 180° oriented its ports to East and South, facing away from incoming Tile 10 (West) and outgoing Tile 15 (South).
  - How it was reproduced: Calculated port vectors for SVG path rotated to 180°; ports were East (1) and South (2) rather than required West (3) and South (2).
  - AI prompt used to fix it: Calibrated base path to `M 50 0 L 50 50 L 100 50` so initial 90° rotation points East & South, and 1 clockwise turn (180°) points South & West to bridge the conduit in exactly one turn as Astra instructs.
  - Verification performed: Chrome CDP test verified full connection upon 1 turn to 180°.
- Observed issue 3 (Flawed Undo): Undo only recorded `{ tile, prevRot }` for a single tile, decremented move counter naively, did not recalculate board energy states, and was disabled once `isSolved` was true.
  - How it was reproduced: Rotated multiple tiles and clicked Undo; subsequent tile states and board energy flow were not restored.
  - AI prompt used to fix it: "Make Undo restore the entire previous board state and move counter."
  - Verification performed: Multi-step undo test verified all 16 tile rotations and move counter restored cleanly across multiple sequential moves.
- Observed issue 4 (Flawed Reset): `restartBtn` only reset `criticalTile` to 90° and set moves to 0; any other rotated tiles remained altered.
  - How it was reproduced: Rotated tiles 1, 3, 5, 8, 11 and pressed Reset; tiles 1, 3, 5, 8 remained rotated.
  - AI prompt used to fix it: "Make Reset restore every tile and all game state to the initial level."
  - Verification performed: Scrambled board test verified Reset restored all 16 tiles to exact Level 04 initial orientations, moves to 6, and circuit to 71%.
- Observed issue 5 (Hardcoded Cosmic Hint & Astra Typo): Hint button always flashed `#criticalTile` with static speech text even if earlier nodes were broken. Static HTML dialogue also showed `Node [3,2]` instead of `[2,3]`.
  - How it was reproduced: Rotated Node 0,1 to break flow, clicked Hint; Astra still incorrectly advised rotating Node 2,3.
  - AI prompt used to fix it: "Make Cosmic Hint calculate a valid next move rather than displaying hardcoded text."
  - Verification performed: Chrome CDP test broke Node 0,1; Hint dynamically targeted Node 0,1 with speech "Rotate Node [0,1] once clockwise".
- Observed issue 6 (Missing Audio System): Audio toggle buttons had no implementation; no Web Audio API or audio assets were wired up.
  - How it was reproduced: Clicked `#soundToggle` and header audio button; no audio context existed and no sound played.
  - AI prompt used to fix it: "Implement working mute/unmute controls and move, connection and victory sounds using the Web Audio API."
  - Verification performed: Synth oscillators verified for move, connection, undo, reset, hint, and victory fanfare; mute toggle tested and verified in browser.

## Tool: Google Antigravity
- Purpose: Inspect code, repair gameplay architecture, implement genuine circuit BFS simulation, Web Audio API synthesis, dynamic hint solver, full undo/reset state management, and execute end-to-end browser tests.
- Date: 2026-10-23.
- Output files modified: `index.html`, `AI_LOG.md`.
- Automated Verification: Executed test suite (`scratch/run_tests.py`) in Google Chrome via Chrome DevTools Protocol (CDP), passing all 9 unit and integration tests across path validation, undo, reset, dynamic hint, audio mute, and victory states.

## Mascot Asset Integration
- Purpose: Safely integrate the new cosmic star mascot into the game's interface without server dependencies or gameplay disruption.
- Date: 2026-10-23.
- Selected Asset: `assets/mascot/south.png` (48×48px transparent PNG, front-facing celestial star).
- Target Location: Header brand block (`<header>` &rarr; `<div class="flex items-center gap-space-sm">`), positioned directly beside the `STARWEAVER` title.
- Changes Made:
  - Replaced external remote Google Stitch placeholder URL (`https://lh3.googleusercontent.com/...`) with the local relative path `assets/mascot/south.png`.
  - Added accessible alt text: `alt="STARWEAVER Cosmic Star Mascot"`.
  - Applied responsive dimensions: `class="h-8 w-8 object-contain ..."` (32×32px).
  - Maintained theme consistency with `drop-shadow-[0_0_8px_rgba(0,242,254,0.5)]` and subtle interactive `hover:scale-110 transition-transform`.
  - Preserved 100% of existing puzzle mechanics, audio engine, event handlers, and HUD elements with zero layout shifts.
- Genuine Verification Performed:
  - File existence verified via PowerShell (`Test-Path "assets/mascot/south.png"` &rarr; `True`).
  - Dimensions confirmed via Python Pillow (`(48, 48)` RGBA).
  - Headless Chrome DevTools Protocol (CDP) test executed:
    - DOM element query confirmed `attrSrc: "assets/mascot/south.png"`.
    - Image loading status confirmed `complete: true`.
    - Intrinsic dimensions confirmed: `naturalWidth: 48`, `naturalHeight: 48`.
    - Rendered dimensions confirmed: `renderedWidth: 32`, `renderedHeight: 32`.
    - Visual rendering verified via headless browser screenshot capture.
    - Regression tests executed and passed: Tile rotation (90° &rarr; 180°), move counter increment, circuit BFS solution validation, victory modal presentation (550ms delay), undo state restoration, reset to Level 04 defaults, and hint counter decrement.

