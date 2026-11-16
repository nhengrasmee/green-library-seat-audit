# Green library seat audit

Notebooks for a seat-level audit of green views in a room. They score every seat from a simple 3D model with one set of rays and report, for each seat, a line-of-sight result to indoor plants, the Green View Index (GVI), an exterior-view result, the distance to the nearest plant, and the share of floor area with a quality view. The tests follow the wording of WELL v2 (Q2 2025) feature M09 and LEED v5 EQc2 (Quality Views). A greedy search then proposes where to add plants.

These notebooks accompany a manuscript on this method (citation to be added when published).

## Notebooks

| File | Module | What it does |
|---|---|---|
| `module1_seat_audit_en.ipynb` | 1. 3D seat audit | Scores each seat (line of sight to plants, GVI, exterior view, 33 ft distance) and the credit results, with a sensitivity table |
| `ai_photo_audit_en.ipynb` | 2. AI photo audit | Crops a photo taken at each seat to the model's 60° × 60° view, segments it with SegFormer (ADE20K), and counts plant pixels |
| `module3_plant_optimiser_en.ipynb` | 3. Plant placement | Searches candidate positions for added plants under a chosen goal |

## How to run

Open a notebook in Google Colab (File, then Open notebook, then GitHub tab, then paste this repository's address) and run all cells. The notebooks need only numpy, pandas and matplotlib; Module 2 also needs the segmentation model and your photographs.

## Notes

- The example room, the scoring settings and the pass conditions (60° × 60° view, one clear point, 75% of seats) are project settings and assumptions, not values from WELL or LEED. Check the credit wording against the current standards before using the results.
- The results show how the method behaves in one modeled room. They are not a certification result.
- The hand check and ray-count convergence cells in Module 1 hold toy-room placeholder values until you enter your own seats.

## Licence

Code is released under the MIT licence (see `LICENSE`).
