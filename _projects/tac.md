---
layout: page
title: TAC
description: Joint target-label acquisition and source-data curation for cross-center medical image segmentation.
img:
importance: 3
category: research
---

**Target-Anchored Coverage for Source-Target Curation in Cross-Center Medical Image Segmentation**

**Role:** First author, USC; advisor: Prof. Ruishan Liu.<br>
**Status:** Manuscript under review, NeurIPS 2026.

## The problem

Under a limited annotation budget, a learner must decide which target examples to label. In cross-center medical imaging, it must also decide which examples from a heterogeneous source pool should remain in training. Treating these decisions separately can leave the training set poorly matched to the target domain.

## The approach

**Target-Anchored Coverage (TAC)** couples active target acquisition with source selection. Queried target labels become reliability anchors for constructing compact, target-aligned source subsets. The aim is to use limited target supervision to improve both the target evidence available to the learner and the composition of its source training data.

TAC complements [TAVO]({{ '/projects/tavo/' | relative_url }}): TAVO uses a fixed labeled target support set to rank source cases, while TAC studies how target acquisition and source curation can work together.

## My contribution

I led the first-author research project and developed the data-curation and evaluation workflows, including:

- Source-target split construction and active-learning baselines.
- Budget-aware selection of target labels and source training subsets.
- Multi-budget training, metric aggregation, and ablation pipelines for studying label scarcity and distribution shift.

**Stack:** PyTorch, MONAI, CUDA, active learning, source-data selection, and Linux/Slurm experiment pipelines.

[View manuscript listing]({{ '/publications/' | relative_url }}) · [All projects]({{ '/projects/' | relative_url }})
