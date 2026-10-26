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

**Role:** Co-first author, USC; advisor: [Prof. Ruishan Liu](https://viterbi-web.usc.edu/~ruishanl/).<br>
**Status:** Accepted to **WACV 2027**.<br>
**Authors:** Xiwen Chen<sup>_</sup>, Tong Miao<sup>_</sup>, Yueqi Dong, Divya Rajparia, Sai Praneeth Karimireddy, and [Ruishan Liu](https://viterbi-web.usc.edu/~ruishanl/). \* Equal contribution.

<div class="links">
  <a href="{{ '/assets/pdf/TAVO_WACV_2027_Camera_Ready.pdf' | relative_url }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener" aria-label="Read TAVO camera-ready PDF">PDF</a>
  <a href="https://github.com/francischen0724/TAVO" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener" aria-label="TAVO code on GitHub">Code</a>
</div>

## The problem

A new clinical center may have only a small labeled dataset, alongside a much larger pool of annotated external cases. Differences in scanners, protocols, and patient populations mean that adding every available source case can increase training cost and cause negative transfer. The question is which cases are useful for this particular target center and training budget.

## The approach

**Target-Aware Valuation Optimization (TAVO)** curates the training set before segmentation training. It combines eight complementary signals for target similarity, gradient compatibility, source coverage, and diversity.

- A shared warm-up model provides representations and gradients for case-level source rankings.
- Rank normalization puts heterogeneous scores on a common scale.
- Validation-guided, multi-fidelity **CMA-ES search** learns target- and budget-specific weights for combining the rankings.
- The fused ranking produces a deterministic top-budget list of source cases for standard downstream training.

The selected cases can be used without changing the segmentation architecture, training loss, or inference procedure. Selection has a development cost, but adds no inference-time overhead.

## Evaluation and results

The study covers **eight held-out target centers or domains** across **BraTS 2021** brain tumor segmentation and **MAMA-MIA** breast tumor segmentation. EfficientViT and nnU-Net provide the medical segmentation backbones; OfficeHome serves as a cross-task classification control.

At the representative **150-case source budget**, the camera-ready paper reports the following target-averaged gains in Dice points:

| Comparison                                   | BraTS 2021 | MAMA-MIA |
| -------------------------------------------- | ---------: | -------: |
| Strongest fixed selector                     |       +1.0 |     +1.9 |
| Strongest budget-matched adaptation baseline |       +1.0 |     +2.2 |

TAVO achieves **77.9 Macro Dice on BraTS** and **71.4 foreground Dice on MAMA-MIA** at this budget. See the [camera-ready paper]({{ '/assets/pdf/TAVO_WACV_2027_Camera_Ready.pdf' | relative_url }}) for per-target results, additional budgets, and ablations.

The source budget applies to candidate and final training; the one-time warm-up and evidence extraction still access the full source pool. Selection also requires proxy-training runs, so reducing the final training set does not by itself establish a reduction in total development compute. Once the subset is fixed, the method adds no inference-time overhead.

**My work:** Method design, source-target split construction, selection and adaptation baselines, multi-budget experiments, backbone validation, and reproducible training and analysis pipelines.

**Stack:** PyTorch, CUDA, EfficientViT, nnU-Net, MONAI, NumPy, scikit-learn, and Linux/Slurm.

[Camera-ready PDF]({{ '/assets/pdf/TAVO_WACV_2027_Camera_Ready.pdf' | relative_url }}) · [Code](https://github.com/francischen0724/TAVO) · [All projects]({{ '/projects/' | relative_url }})
