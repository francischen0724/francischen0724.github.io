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

I led this work as first author at USC under the supervision of [Prof. Ruishan Liu](https://viterbi-web.usc.edu/~ruishanl/).

**Under review at CVPR 2027.** [Read the preprint (PDF)]({{ '/assets/pdf/TAC_Preprint.pdf' | relative_url }}).

## The problem

Under a limited annotation budget, a learner must decide which target examples to label. In cross-center medical imaging, it must also decide which examples from a heterogeneous source pool should remain in training. Treating these decisions separately can leave the training set poorly matched to the target domain.

## The approach

**Target-Anchored Coverage (TAC)** couples active target acquisition with source selection. Queried target labels become reliability anchors for constructing compact, target-aligned source subsets. The aim is to use limited target supervision to improve both the target evidence available to the learner and the composition of its source training data.

TAC complements [TAVO]({{ '/projects/tavo/' | relative_url }}): TAVO uses a fixed labeled target support set to rank source cases, while TAC studies how target acquisition and source curation can work together.

TAC first selects target cases for annotation using a weighted clustering scheme guided by prediction uncertainty, inconsistency, and stability. It then uses the annotated masks to estimate source reliability from distributional similarity, gradient agreement, and prototype compatibility. Reliability-weighted coverage selects a complementary source subset for training alongside the annotated target cases. TAC preserves the downstream segmentation architecture, loss, and inference procedure.

## Results

In leave-one-center-out evaluations with 10 newly annotated target cases and 150 selected source cases, TAC reaches **77.3% macro Dice on BraTS 2021** and **68.4% foreground Dice on MAMA-MIA**. It improves on the strongest matched-budget baselines by **1.8** and **1.9 Dice points**, respectively.

## Coupled data curation

_What to Label, What to Train On: Coupled Data Curation for Cross-Domain Medical Segmentation_ is a companion manuscript submitted to the Data4VFM Workshop at WACV 2027. It examines how the value of labeling a target case depends on which source cases enter training under the same budgets.

## My contribution

I led the first-author research project and developed the data-curation and evaluation workflows, including:

- Source-target split construction and active-learning baselines.
- Budget-aware selection of target labels and source training subsets.
- Multi-budget training, metric aggregation, and ablation pipelines for studying label scarcity and distribution shift.

**Stack:** PyTorch, MONAI, CUDA, active learning, source-data selection, and Linux/Slurm experiment pipelines.

[View manuscript listing]({{ '/publications/' | relative_url }}) · [All projects]({{ '/projects/' | relative_url }})
