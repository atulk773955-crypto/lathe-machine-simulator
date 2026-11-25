# Centre Lathe Simulator — Virtual Engineering Workshop

![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white) ![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black) ![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)

An interactive, browser-based centre lathe simulator that helps engineering students understand machine construction, tool motions and common workshop machining operations through animated 2.5D illustrations and live workpiece geometry.

![Centre lathe simulator interface](preview.png)

## Overview

The simulator models a conventional geared centre lathe. Students can explore labelled components, select tools, adjust machining parameters, start the spindle and observe automated machining cycles. It is intended for workshop practice, engineering education and viva revision.

## Features

- 18 interactive component descriptions, covering the headstock, spindle, chuck, bed, saddle, cross-slide, compound rest, tool post, apron, rack and pinion, lead screw, feed rod, gearbox, half-nut, tailstock, quill, workpiece and cutting tool.
- 12 selectable machining operations with corresponding tools, motion explanations and expected outcomes.
- Animated spindle and workpiece rotation, carriage motion, quill travel and illustrative chip formation during selected operations.
- Adjustable spindle speed (100–1200 RPM), feed (0.05–0.50 mm/rev) and depth setting (0.5–5 mm).
- Manual jogging of carriage, cross-slide, tailstock and quill while the spindle is stopped.
- Live workpiece profile, cross-sectional view, operation progress and machining readouts.
- Responsive interface; no external runtime libraries, installation, account or backend required.

## Machining operations

| Operation | Tool | Result |
| --- | --- | --- |
| Plain turning | Right-hand turning tool | Reduced external diameter |
| Facing | Facing tool | Flat end surface |
| Step turning | Turning tool | Stepped shaft |
| Taper turning | Turning tool / compound rest | Conical surface |
| Grooving | Grooving tool | Circumferential recess |
| Parting-off | Parting blade | Separated end segment |
| Thread cutting | 60° V threading tool | Illustrative external thread |
| Knurling | Diamond knurling rollers | Textured gripping surface |
| Drilling | Twist drill | Axial blind hole |
| Boring | Boring bar | Enlarged existing hole |
| Reaming | Machine reamer | Finished hole |
| Chamfering | 45° chamfer tool | Bevelled edge |

## Getting started

1. Download this repository using **Code → Download ZIP** and extract the files, or clone it with Git.
2. Open `index.html` in a modern browser (Chrome, Edge or Firefox).
3. No `npm install`, build step or server is required. The simulator itself works offline; the README badges are external images.

Optional: serve the folder locally using Python 3:

```bash
python -m http.server 8000
```

Open `http://localhost:8000` in a browser.

## How to use

1. Click a machine label or select a component in the explorer to learn its function.
2. Select an operation from the tool rack or operation menu. Changing operations resets the simulated workpiece.
3. Adjust the RPM, feed and depth controls before starting. The meaning of the depth setting depends on the selected operation; see its guide.
4. Use the jog controls with the spindle stopped to explore component motion. Automatic feed resets the jog offsets to the demonstration path.
5. Click **Start spindle** to see rotation, then **Auto feed** to begin machining. Auto feed can also start the spindle.
6. Observe the tool path, changing workpiece profile and machining readouts.
7. Click **Stop** to stop the spindle and feed, or **Reset workpiece** to restart the demonstration.

### Keyboard shortcuts

| Key | Action |
| --- | --- |
| Space | Toggle spindle start/stop |
| R | Reset workpiece |

Shortcuts are ignored while an input, select menu or button has focus.

## Engineering concepts

For an external cylindrical turning operation, the standard relationships are:

- Cutting speed: `V = πDN / 1000` (m/min)
- Feed rate: `F = fN` (mm/min)
- Radial depth of cut: `t = (D − d) / 2` (mm)

Here, `D` is the initial diameter in mm, `d` the final diameter in mm, `N` the spindle speed in RPM, and `f` the feed in mm/rev. These relations provide educational context; animation timing is not a real machining-time prediction.

## Technology stack

| Technology | Purpose |
| --- | --- |
| HTML5 | Application structure |
| CSS | Responsive styling and controls |
| Vanilla JavaScript | State management, interactions and animation |
| SVG | Scalable machine drawing and workpiece profiles |

## Project structure

```text
.
├── index.html      # Complete simulator: HTML, CSS, JavaScript and SVG
├── preview.png     # Screenshot of the simulator interface
├── README.md       # Documentation and usage guide
├── LICENSE         # MIT open-source license
├── .gitignore      # Excludes local/editor files
└── .nojekyll       # Optional static GitHub Pages configuration
```

## Publish with GitHub Pages

1. Create a public GitHub repository, for example `lathe-machine-simulator`.
2. Upload the project files to the root of the `main` branch and commit them.
3. Go to **Settings → Pages**.
4. Under **Build and deployment**, select **Deploy from a branch**.
5. Select `main` and `/(root)`, then click **Save**.
6. When deployment succeeds, open the website link shown on the Pages settings screen. A typical URL is `https://YOUR-USERNAME.github.io/lathe-machine-simulator/`.

See [GitHub Pages documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

## Limitations and safety

This is an educational 2.5D visualization, not a validated industrial machining simulator. Geometry and motion are simplified or exaggerated, and timing is accelerated. It does not calculate cutting forces, tool wear, vibration, thermal effects or collisions, and it does not reproduce exact helical thread geometry. Settings are not recommendations for operating a real machine. Use actual workshop equipment only with appropriate training, guarding and instructor supervision.

## Future improvements

- Full 3D machine model and camera controls.
- Material-specific cutting parameters and tool selection.
- More accurate multi-pass machining and thread geometry.
- Collision checks, cutting-force estimates and interactive workshop assessments.

## Contributing

Suggestions, bug reports and improvements are welcome. Open an issue or submit a pull request describing the proposed change and how it was tested. For technical changes, include the machining assumptions and units.

## License

Released under the [MIT License](LICENSE).
