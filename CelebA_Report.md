# CelebA Dataset Analysis: Methodology, Results, and Insights

Author: Project Team

## Overview

This document presents a comprehensive analysis of the CelebA dataset (Aligned & Cropped). We examine attribute distributions, correlations, dataset splits, and provide qualitative visuals such as bounding box and landmark overlays. All results are reproducible via the project notebook and the analysis script.

- Dataset root: `data/archive/`
- Images: `data/archive/img_align_celeba/`
- Annotations: `list_attr_celeba.csv`, `list_eval_partition.csv`, `list_landmarks_align_celeba.csv`, `list_bbox_celeba.csv`
- Analysis figures: `outputs/celeba_analysis/figures/`

## Methodology

- Loading & Normalization
  - Parse CelebA annotation CSVs with `pandas`.
  - Convert attributes from {-1, 1} to {0, 1} for interpretability.
- Quantitative Analysis
  - Prevalence: fraction of images with each attribute set to 1.
  - Splits: mapping `partition` values to train/val/test and reporting counts.
  - Correlation: Pearson correlation on binary attributes to identify relationships.
- Qualitative Visuals
  - Random grids of positive examples for selected attributes.
  - Landmark and bounding box overlays for representative images.
- Reproducibility
  - All steps implemented in `src/celeba_analysis.py` and mirrored in the Jupyter notebook.

## Dataset Summary

- Total images: computed from annotation files.
- Split sizes: train/val/test image counts.
- Top attributes by prevalence (example chart below).

Refer to `reports/celeba_summary.json` for machine-readable metrics.

## Results

- Attribute Prevalence (Top 12)
  - File: `outputs/celeba_analysis/figures/attr_prevalence_top12.png`
  - Interpretation: Highlights common visual traits (e.g., Young, Smiling) and less frequent ones (e.g., Bald, Goatee).

- Attribute Correlation
  - File: `outputs/celeba_analysis/figures/attr_correlation.png`
  - Interpretation: Positive/negative associations across attributes (e.g., Wearing_Lipstick with Heavy_Makeup; Male negatively correlated with Wearing_Lipstick).

- Samples for Selected Attributes
  - Files: `outputs/celeba_analysis/figures/samples_smiling.png`, `samples_male.png`, `samples_young.png`
  - Interpretation: Qualitative sense of attribute appearance and variety across samples.

- BBoxes & Landmarks (Samples)
  - File: `outputs/celeba_analysis/figures/bbox_landmarks_samples.png`
  - Interpretation: Confirms alignment quality and annotation consistency across the dataset.

## Discussion

- Class Imbalance
  - Certain attributes are highly imbalanced; downstream models require strategies (reweighting, sampling) for balanced learning.
- Attribute Interactions
  - Correlations can guide feature selection and model design (e.g., avoid redundant signals or capture interactions).
- Data Quality
  - Landmarks and bboxes look consistent for aligned images; misalignments are rare but can occur.

## Conclusions

- CelebA provides rich attribute supervision with consistent alignment and annotations.
- Attribute prevalence and correlation analyses inform modeling choices and evaluation baselines.
- The dataset is suitable for multi-label classification, attribute discovery, and face analysis pipelines.

## Reproducibility

- Script: `python src/celeba_analysis.py`
- Notebook: `notebooks/celeba_analysis.ipynb`
- Figures: `outputs/celeba_analysis/figures/`
- Slide assets: `presentation/assets/celeba/` with `celeba_manifest.json`

## Citations

- Liu, Z., Luo, P., Wang, X., & Tang, X. (2015). Deep Learning Face Attributes in the Wild. ICCV.
- CelebA dataset: http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html

## Appendix

- Raw summary JSON: `reports/celeba_summary.json`
- Environment: see `requirements.txt`