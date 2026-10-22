# STARWEAVER — Stitch export

## What is included
- `index.html`: exported Stitch screen/code (renamed from `code.html` for easier local opening)
- `code.html`: original exported file, preserved unchanged
- `screen.png`: screenshot exported by Stitch
- `DESIGN.md`: design system and visual specifications
- `AI_LOG.md`: initial AI-use evidence log

## Run locally
1. Open `index.html` in Chrome or Edge.
2. If external fonts or Tailwind CDN are used, an internet connection may be needed for those assets.
3. Test Undo, Reset, Hint, tile rotation and victory behaviour. This export is a generated starting point, not yet verified as a complete production-ready game.

## Before the hackathon submission
- Verify every control and level manually.
- Add any PixelLab art and generated sound files only after checking the game still works.
- Update `AI_LOG.md` with actual prompts, tool outputs, mistakes and fixes.
- Initialise Git and commit each meaningful working version.
- Publish a public GitHub repository if required by the event instructions.
