# A Night in the Blitz — Project Rules

## The only files in this project
- `index.html` — the A-Frame scene
- `blitz_alley8.glb` — the Blender export (replaced when user exports a new version)
- `vr-placer.js` — movement and material components

## NEVER touch
- Anything in `/Users/emilylilywhitty/Desktop/The royal oak/` — that is the OLD project folder
- The old GitHub repo: https://github.com/emilywhitty224-ctrl/blitz-alley

## Workflow
- User builds the scene in Blender (`Blitz Alley.blend` on their Desktop)
- Exports as GLB → replaces `blitz_alley8.glb` in this folder
- All code changes go in `index.html` or `vr-placer.js` only
- Push to: https://github.com/emilywhitty224-ctrl/a-night-in-the-blitz
- Live URL: https://emilywhitty224-ctrl.github.io/a-night-in-the-blitz/

## Scene
- WWII London 1940, Blitz blackout night walking experience
- Quest VR — must stay WebXR compatible
- 1 A-Frame unit = 1 metre, strict rule, never scale parent entities
- Scene starts in night mode, no day/night toggle needed
- Torch in right hand, A button toggles it on/off
- Left stick = walk, right stick = smooth turn
