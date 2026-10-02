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
**Status:** Manuscript under review.

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

At a **150-case source budget**, the manuscript reports:

| Target-averaged result                                 |  BraTS 2021 |    MAMA-MIA |
| ------------------------------------------------------ | ----------: | ----------: |
| Dice score                                             |        77.9 |        71.4 |
| Gain over strongest fixed selector                     | +1.0 points | +1.9 points |
| Gain over strongest budget-matched adaptation baseline | +1.0 points | +2.2 points |
| Gain over Target + Full Source                         | +2.9 points | +2.0 points |

TAVO ranks first on five targets and second on the remaining three at this budget. The source budget applies to candidate and final training; the one-time warm-up and evidence extraction still access the full source pool. This distinction matters when comparing training-set size with total development cost.

**My work:** Method design, source-target split construction, selection and adaptation baselines, multi-budget experiments, backbone validation, and reproducible training and analysis pipelines.

**Stack:** PyTorch, CUDA, EfficientViT, nnU-Net, MONAI, NumPy, scikit-learn, and Linux/Slurm.

[View manuscript listing]({{ '/publications/' | relative_url }}) · [All projects]({{ '/projects/' | relative_url }})
