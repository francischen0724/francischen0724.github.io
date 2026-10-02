---
layout: page
title: TAVO
description: Learning which training examples are useful for a target domain under a fixed data budget.
img:
importance: 2
category: research
---

**Learning which data is worth using**

TAVO studies training-data selection under distribution shift: which examples should a learner use when it cannot train on everything? The framework learns a selection strategy for each target domain and data budget, evaluated on cross-center tumor segmentation and a cross-task classification control.

**Role:** First author, USC; advisor: Prof. Ruishan Liu.<br>
**Status:** Manuscript under review at AAAI 2027. The anonymous repo is not available during peer review.

## The problem

A new clinical center may have only a small labeled dataset, alongside a much larger pool of annotated external cases. Differences in scanners, protocols, and patient populations mean that adding every available source case can increase training cost and cause negative transfer. The question is which cases are useful for this particular target center and training budget.

## The approach

**Target-Aware Valuation Optimization (TAVO)** curates the training set before segmentation training. It combines eight complementary signals for target similarity, gradient compatibility, source coverage, and diversity.

- A shared warm-up model provides representations and gradients for case-level source rankings.
- Rank normalization puts heterogeneous scores on a common scale.
- Validation-guided, multi-fidelity search learns target- and budget-specific weights for combining the rankings.
- The fused ranking produces a deterministic top-budget list of source cases for standard downstream training.

The selected cases can be used without changing the segmentation architecture, training loss, or inference procedure. Selection has a development cost, but adds no inference-time overhead.

## Evaluation and results

The study covers **eight held-out target centers or domains** across **BraTS 2021** brain tumor segmentation and **MAMA-MIA** breast tumor segmentation. EfficientViT and nnU-Net provide the medical segmentation backbones; OfficeHome serves as a cross-task classification control.

Across held-out targets at a **12% source-data budget**, the results summarized in my [CV]({{ '/cv/' | relative_url }}) are:

| Comparison                  | Dice improvement |
| --------------------------- | ---------------: |
| Fixed-selector baselines    |      +1.9 points |
| Domain-adaptation baselines |      +2.2 points |

The source budget applies to candidate and final training; the one-time warm-up and evidence extraction still access the full source pool. Selection also requires proxy-training runs, so reducing the final training set does not by itself establish a reduction in total development compute. Once the subset is fixed, the method adds no inference-time overhead.

**My work:** Method design, source-target split construction, selection and adaptation baselines, multi-budget experiments, backbone validation, and reproducible training and analysis pipelines.

**Stack:** PyTorch, CUDA, EfficientViT, nnU-Net, MONAI, NumPy, scikit-learn, and Linux/Slurm.

[View manuscript listing]({{ '/publications/' | relative_url }}) · [All projects]({{ '/projects/' | relative_url }})
