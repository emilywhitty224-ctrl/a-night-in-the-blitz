# A Night in the Blitz — Project Rules

## The only files in this project
- `index.html` — the A-Frame scene (all components + markup live here)
- `a_night_in_the_blitz_14.glb` — the current Blender export (replaced on re-export; bump the `<a-asset-item>` src if the filename changes)
- `torch.glb` — the torch model held in the right hand
- `blitz_audio_test.m4a` — positional radio audio (32 kbps mono AAC, ~213 KB)

## NEVER touch
- Anything in `/Users/emilylilywhitty/Desktop/The royal oak/` — that is the OLD project folder
- The old GitHub repo: https://github.com/emilywhitty224-ctrl/blitz-alley

## Workflow
- User builds the scene in Blender (`Blitz Alley.blend` on their Desktop) with Draco mesh compression + JPEG textures on export
- Exports as GLB → saves over `a_night_in_the_blitz_14.glb` (or new numbered file; 100 MB GitHub limit applies)
- All code changes go in `index.html`
- Push to: https://github.com/emilywhitty224-ctrl/a-night-in-the-blitz
- Live URL: https://emilywhitty224-ctrl.github.io/a-night-in-the-blitz/

## Scene
- WWII London 1940, Blitz blackout night walking experience
- Quest VR — must stay WebXR compatible
- 1 A-Frame unit = 1 metre, strict rule, never scale parent entities
- Scene starts in night mode, no day/night toggle needed
- Torch in right hand, A button toggles it on/off
- Left stick = walk, right stick = smooth turn
