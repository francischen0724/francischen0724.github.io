---
layout: page
title: TAVO
description: Learning which training examples are useful for a target domain under a fixed data budget.
img:
importance: 2
category: research
toc:
  sidebar: left
---

<ul class="project-badges" aria-label="Project status">
  <li>WACV 2027</li>
  <li>Co-first author</li>
  <li>Data-centric ML</li>
</ul>

TAVO learns which labeled source cases to use for each target center and training budget.

<div class="portfolio-actions">
  <a class="portfolio-action portfolio-action-primary" href="{{ '/assets/pdf/TAVO_WACV_2027_Camera_Ready.pdf' | relative_url }}" target="_blank" rel="noopener">TAVO paper (PDF)</a>
  <a class="portfolio-action" href="https://github.com/francischen0724/TAVO" target="_blank" rel="noopener">Code</a>
</div>

## Key results

With a budget of **150 source cases**, TAVO improved target-averaged Dice over the strongest fixed selector on both benchmarks.

<div class="project-metrics">
  <div class="project-metric">
    <p class="project-metric-label">BraTS 2021 · macro Dice</p>
    <p class="project-metric-value">77.9%</p>
    <p class="project-metric-delta">+1.0 points</p>
  </div>
  <div class="project-metric">
    <p class="project-metric-label">MAMA-MIA · foreground Dice</p>
    <p class="project-metric-value">71.4%</p>
    <p class="project-metric-delta">+1.9 points</p>
  </div>
</div>

Against the strongest budget-matched adaptation baselines, TAVO gains **1.0 Dice point on BraTS 2021** and **2.2 on MAMA-MIA**.

**Role:** Co-first author, USC; advisor: [Prof. Ruishan Liu](https://viterbi-web.usc.edu/~ruishanl/).<br>
**Status:** Accepted to **WACV 2027**.<br>
**Authors:** Xiwen Chen<sup>\*</sup>, Tong Miao<sup>\*</sup>, Yueqi Dong, Divya Rajparia, Sai Praneeth Karimireddy, and [Ruishan Liu](https://viterbi-web.usc.edu/~ruishanl/). \* Equal contribution.

## The problem

A new clinical center may have only a small labeled dataset, alongside a much larger pool of annotated external cases. Differences in scanners, protocols, and patient populations mean that adding every available source case can increase training cost and cause negative transfer. The question is which cases are useful for this particular target center and training budget.

## The approach

**Target-Aware Valuation Optimization (TAVO)** curates the training set before segmentation training. It combines eight complementary signals for target similarity, gradient compatibility, source coverage, and diversity.

- A shared warm-up model provides representations and gradients for case-level source rankings.
- Rank normalization puts heterogeneous scores on a common scale.
- Validation-guided, multi-fidelity **CMA-ES search** learns target- and budget-specific weights for combining the rankings.
- The fused ranking produces a deterministic top-budget list of source cases for standard downstream training.

The selected cases can be used without changing the segmentation architecture, training loss, or inference procedure. Selection has a development cost, but adds no inference-time overhead.

## Evaluation details {#evaluation-and-results}

The study covers **eight held-out target centers or domains** across **BraTS 2021** brain tumor segmentation and **MAMA-MIA** breast tumor segmentation. EfficientViT and nnU-Net provide the medical segmentation backbones; OfficeHome serves as a cross-task classification control.

See the [camera-ready paper]({{ '/assets/pdf/TAVO_WACV_2027_Camera_Ready.pdf' | relative_url }}) for per-target results, additional budgets, and ablations.

The source budget applies to candidate and final training; the one-time warm-up and evidence extraction still access the full source pool. Selection also requires proxy-training runs, so reducing the final training set does not by itself establish a reduction in total development compute. Once the subset is fixed, the method adds no inference-time overhead.

**My work:** Method design, source-target split construction, selection and adaptation baselines, multi-budget experiments, backbone validation, and reproducible training and analysis pipelines.

**Stack**

<ul class="project-stack" aria-label="Stack">
  <li>PyTorch</li>
  <li>CUDA</li>
  <li>EfficientViT</li>
  <li>nnU-Net</li>
  <li>MONAI</li>
  <li>NumPy</li>
  <li>scikit-learn</li>
  <li>Linux/Slurm</li>
</ul>

[Camera-ready PDF]({{ '/assets/pdf/TAVO_WACV_2027_Camera_Ready.pdf' | relative_url }}) · [Code](https://github.com/francischen0724/TAVO) · [All projects]({{ '/projects/' | relative_url }})
