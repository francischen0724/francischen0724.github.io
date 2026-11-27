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

TAC uses predictions from a full-source warm-up checkpoint to select target cases for annotation. It clusters candidates using weights based on foreground-aware uncertainty, local prediction inconsistency, and prediction stability. It then estimates source reliability using distributional similarity to the acquired target cases, gradient agreement, and prototype compatibility. The last two signals use the acquired masks. Reliability-weighted coverage selects a source subset for final training alongside the annotated target cases. TAC preserves the downstream segmentation architecture, supervised loss, and inference procedure.

## Results

With 10 acquired target masks and 150 selected source cases for final training, TAC reaches **77.3% macro Dice on BraTS 2021** and **68.4% foreground Dice on MAMA-MIA**, averaged over four held-out targets per benchmark. It improves on CLUE + ORIENT by **1.8 Dice points** on BraTS 2021 and on MADA by **1.9 Dice points** on MAMA-MIA. At the same source budget with only two target masks, TAC falls below the strongest comparator on both benchmarks. Target validation annotations are used separately for checkpoint selection.

## Coupled data curation

_What to Label, What to Train On: Coupled Data Curation for Cross-Domain Medical Segmentation_ is a companion manuscript submitted to the Data4VFM Workshop at WACV 2027. It examines how target acquisition and source selection interact. On BraTS 2021 at the same 10-target and 150-source budgets, replacing random acquisition with TAC acquisition lowers mean Dice by 0.61 points with random source selection and raises it by 2.20 points with TAC source selection.

[Read the workshop manuscript (PDF)]({{ '/assets/pdf/Data4VFM_TAC.pdf' | relative_url }}).

## My contribution

I led the first-author research project and developed the data-curation and evaluation workflows, including:

- Source-target split construction and active-learning baselines.
- Budget-aware selection of target labels and source training subsets.
- Multi-budget training, metric aggregation, and ablation pipelines for studying label scarcity and distribution shift.

**Stack:** PyTorch, MONAI, CUDA, active learning, source-data selection, and Linux/Slurm experiment pipelines.

[View manuscript listing]({{ '/publications/' | relative_url }}) · [All projects]({{ '/projects/' | relative_url }})
