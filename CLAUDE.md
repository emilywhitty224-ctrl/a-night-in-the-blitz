# A Night in the Blitz — Project Rules

## The only files in this project
- `index.html` — the A-Frame scene (all components + markup live here)
- `a_night_in_the_blitz_25.glb` — the current Blender export (replaced on re-export; bump the `<a-asset-item>` src if the filename changes)
- `torch.glb` — the torch model held in the right hand
- `blitz_audio_test.m4a` — placeholder audio clip (kept on disk; not currently wired into the scene)
- `navmesh.glb` — navmesh (if/when used for locomotion)

## NEVER touch
- Anything in `/Users/emilylilywhitty/Desktop/The royal oak/` — that is the OLD project folder
- The old GitHub repo: https://github.com/emilywhitty224-ctrl/blitz-alley

## Workflow
- User builds the scene in Blender (`Blitz Alley.blend` on their Desktop) with Draco mesh compression + JPEG textures on export
- Exports as GLB → saves over the current numbered scene GLB (or new numbered file; 100 MB GitHub limit applies)
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

## FROZEN — do NOT modify without explicit instruction
These systems have been iterated many times and are working. When adding new features, build **alongside** them. If a task would require editing anything in this list, STOP and ask first.

### Components / JS in `index.html`
- Draco decoder setup (`DOMContentLoaded` handler at the top)
- Error suppression (`unhandledrejection`, `window.onerror`)
- `_mergeVertsByPosUV()` geometry helper
- `night-darken` component (scene shading, wet-cobble roughness pass)
- `matte-darken` component (torch GLB material override)
- `scene-materials-fix` component
- `torch-flicker` component
- `torch-toggle` component (right A-button on/off)
- Locomotion: `movement-controls` (left-stick walk). `oculus-touch-controls` on both hands (smooth-turn is still being tuned — OK to touch)
- Fog, moonlight, ambient light setup
- Searchlights: `searchlight-sweep`, `arc-flicker`, and the 3-shell cone stack
- `audio-unlock-vr` component and `_unlockAudio()`
- Version overlay `<div id="version-overlay">`
- Desktop-only Day/Night panel and its VR show/hide hooks

### Assets (always keep loading)
- `<a-asset-item id="scene-glb">` — scene GLB (filename bumps are fine; the element stays)
- `<a-asset-item id="torch-glb">` — torch GLB
- `torch.glb` file
- Current numbered scene GLB file

### OK to change (still being tuned)
- Barrage balloons: `barrage-balloon` component + balloon entities (shape/fins iterated through v71; expect more tuning)
- Smooth-turn behavior on `oculus-touch-controls` (turn-in-place fix landed v71; may need more)
- `blitz_audio_test.m4a` — placeholder, may be replaced
- Entity positions/parameters when explicitly tuning (ask first if it affects a frozen system)
- Any NEW components or entities added for new features

### Rule of thumb
If in doubt, ask. Don't "clean up" or "modernise" frozen code as a side-effect of another task.
