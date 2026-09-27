# Crimson Wraith XV-01
A Daniel Martins concept — interactive vehicle presentation.

## Open
Extract the complete ZIP, then open `index.html` in a modern browser with WebGL enabled. Keep app.js, model-data.js and style.css beside index.html. All rendering code, model data and reference images are included; no CDN or internet connection is required. On Android, extract the ZIP with a file manager and open index.html in a browser. If that file manager blocks companion JavaScript, use the hosted presentation instead.

## Controls
Drag to orbit, scroll or pinch to zoom. Camera presets include the underbody. Choose Obsidian, Studio white or Night vision. Change paint, roughness, lights and wireframe. Select an assembly name under Model analysis to isolate it visually; click again to clear. Cinematic demo follows a repeating 32-second orbit, hover, support and separation sequence. Manual sliders stop the demo. Reset restores the original presentation settings. Capture PNG saves the current viewport at the device's rendering resolution.

## Model analysis
The included source FBX contains 15 mesh objects and 474,672 triangles, with no authored animation clips or skeleton. The supplied geometry is used directly, centered and normalized to 12 display units along its long axis; this does not assert real-world dimensions. External texture filenames are resolved to the supplied images embedded in model-data.js.

The main `Cube` object joins the fuselage, canopy, fins and other surfaces; it is intentionally not torn apart to fabricate independent hinges. All 14 remaining authored meshes participate in an illustrative exploded assembly view. `Cube005`, `Torus003` and `Cylinder003` form a small central support grouping with an illustrative vertical retraction. Mechanical constraints, clearances, gear linkages and structural loads have not been validated. Rear propulsion plumes, hover, turntable motion and the demo camera are presentation effects, not simulation or source-authored motion. Descriptive part names are inferred, not verified engineering classifications.

The browser renderer uses Three.js physical materials, environment reflections, ACES tone mapping, soft directional shadows, studio lights and an antialiased WebGL canvas. Night vision is a stylized green overlay, not sensor simulation. This is not Unreal Engine. HD capture depends on viewport size and device capability. The detailed source geometry may reduce frame rate on lower-powered phones.

## Contents
- index.html, style.css, app.js, model-data.js: offline presentation
- assets/: original supplied reference images
- source-model/: original FBX and supplied textures
- model-analysis.json: per-object bounds, vertex counts and material names
- app-source.js: editable renderer source (build using Three.js and esbuild)
- package.json, package-lock.json: reproducible JavaScript dependencies

To rebuild: `npm ci`, then `npx esbuild app-source.js --bundle --minify --format=iife --outfile=app.js`.
