# Jane Street ASIC Puzzle 2026

My solution to [Jane Street's ASIC puzzle](https://github.com/janestreet/asic-puzzle-2026): reverse engineering `puzzle.gds` until `success` goes high.

- [solution.ipynb](solution.ipynb) - the full solve. GitHub renders it inline, but strips the interactive 3D figures and the replay scrubbers.
- [Interactive version](https://f4t4nt.github.io/asic-puzzle) - the same notebook with every figure working.
- [Jane_Street_ASIC_Puzzle_2026.pdf](Jane_Street_ASIC_Puzzle_2026.pdf) - the writeup.
- `repo/` - the original puzzle repository.

To run the notebook yourself:

```
git clone --recursive https://github.com/f4t4nt/jane-street-asic-puzzle-2026
```

Install the notebook dependencies (`numpy`, `matplotlib`, `gdstk`, `shapely`,
`mapbox-earcut`, `z3-solver`, `k3d`, and `ipython`), then open `solution.ipynb`
and run all cells. It exports the interactive figures into `figs/`.

The 3D figures use Three.js with an orientation cube, Ctrl-drag panning,
layer filters, and simulation playback. K3D supplies the Python mesh objects;
`scene_export.py` writes their geometry and signal states for the browser.
The viewer bundle is included. To rebuild it after editing `tools/viewer-three.js`:

```sh
npm ci --prefix tools
node tools/build_viewer.mjs .
```
