# CelebA Faces Dataset Analysis

This repository exclusively analyzes the CelebA Aligned & Cropped dataset and presents results via a reproducible script, a Jupyter notebook, and a presentation deck.

Dataset: CelebA (Aligned & Cropped)
- Images: `data/archive/img_align_celeba/`
- Annotations: `data/archive/list_attr_celeba.csv`, `list_eval_partition.csv`, `list_landmarks_align_celeba.csv`, `list_bbox_celeba.csv`

## Project Structure

- `src/celeba_analysis.py` — Loads annotations, computes attribute prevalence and correlations, and generates sample grids and overlays.
- `outputs/celeba_analysis/figures/` — Generated figures used by the presentation and reports.
- `reports/CelebA_Report.md` — Detailed report (methodology, results, and conclusions).
- `reports/celeba_summary.json` — Machine-readable summary for quick reference.
- `notebooks/celeba_analysis.ipynb` — Reproducible notebook of the full analysis.
- `presentation/` — Slides that display only CelebA results and visuals.

## Setup

1. Create and activate a virtual environment (Windows):
   - `python -m venv .venv`
   - `./.venv/Scripts/Activate.ps1`
2. Install dependencies:
   - `pip install -r requirements.txt`
3. Place the CelebA files under `data/archive/` maintaining the provided paths above.

## Run Analysis

- `python src/celeba_analysis.py`

Outputs:
- Figures to `outputs/celeba_analysis/figures/`
- Slide assets and manifest to `presentation/assets/celeba/` and `presentation/assets/celeba_manifest.json`
- Summary JSON to `reports/celeba_summary.json`

## Presentation

- Start local server to view slides:
  - `cd presentation`
  - `python -m http.server 8000`
  - Open `http://localhost:8000/`

## Notes

- All materials and code paths are CelebA-specific.
- If you need to refresh slides after rerunning analysis, reload the page; assets are updated in-place.