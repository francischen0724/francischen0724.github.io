---
layout: page
title: TAC
description: Connecting target-label acquisition with source-data selection under annotation constraints.
img:
importance: 3
category: research
---

**Allocating labels and training data together**

TAC studies how limited target supervision can guide both annotation decisions and training-set composition. It connects active learning with source-data curation, using cross-center medical image segmentation to evaluate learning under distribution shift.

**Role:** First author, USC; advisor: Prof. Ruishan Liu.<br>
**Status:** Manuscript under review at NeurIPS 2026. The anonymous repo is not available during peer review.

## The problem

Under a limited annotation budget, a learner must decide which target examples to label. In cross-center medical imaging, it must also decide which examples from a heterogeneous source pool should remain in training. Treating these decisions separately can leave the training set poorly matched to the target domain.

## The approach

**Target-Anchored Coverage (TAC)** couples active target acquisition with source selection. Queried target labels become reliability anchors for constructing compact, target-aligned source subsets. The aim is to use limited target supervision to improve both the target evidence available to the learner and the composition of its source training data.

TAC complements [TAVO]({{ '/projects/tavo/' | relative_url }}): TAVO uses a fixed labeled target support set to rank source cases, while TAC studies how target acquisition and source curation can work together.

The workflow first selects target cases for annotation, then uses their labels to assess source reliability through representation similarity and gradient agreement. Target-anchored coverage expands the selected subset into relevant source regions, while redundancy control limits repetitive examples. The resulting source subset and acquired target cases feed the same downstream segmentation architecture, loss, and inference procedure used by the comparison methods.

## Results

In held-out-target experiments at a **12% source-data budget**, TAC improves Dice by **1.5 points over the strongest baseline** and **4.1 points over full-source training**. These comparisons evaluate whether joint source-target curation can improve generalization while using fewer source examples.

## My contribution

I led the first-author research project and developed the data-curation and evaluation workflows, including:

- Source-target split construction and active-learning baselines.
- Budget-aware selection of target labels and source training subsets.
- Multi-budget training, metric aggregation, and ablation pipelines for studying label scarcity and distribution shift.

**Stack:** PyTorch, MONAI, CUDA, active learning, source-data selection, and Linux/Slurm experiment pipelines.

[View manuscript listing]({{ '/publications/' | relative_url }}) · [All projects]({{ '/projects/' | relative_url }})
