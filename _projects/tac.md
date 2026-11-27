---
layout: page
title: TAC
description: Target-Anchored Coverage for cross-center medical image segmentation.
img:
importance: 3
category: research
toc:
  sidebar: left
---

<ul class="project-badges" aria-label="Project status">
  <li class="project-badge-muted">Under review · CVPR 2027</li>
  <li>First author</li>
  <li>Active learning</li>
</ul>

TAC uses acquired target masks to guide source selection and supervise segmentation.

<div class="portfolio-actions">
  <a class="portfolio-action portfolio-action-primary" href="{{ '/assets/pdf/TAC_Preprint.pdf' | relative_url }}">TAC preprint (PDF)</a>
  <a class="portfolio-action" href="{{ '/assets/pdf/Data4VFM_TAC.pdf' | relative_url }}">Data4VFM PDF</a>
</div>

## Key results {#results}

Final training used **10 acquired target masks** and **150 selected source cases**.

<div class="project-metrics">
  <div class="project-metric">
    <p class="project-metric-label">BraTS 2021 · macro Dice</p>
    <p class="project-metric-value">77.3%</p>
    <p class="project-metric-delta">+1.8 points</p>
  </div>
  <div class="project-metric">
    <p class="project-metric-label">MAMA-MIA · foreground Dice</p>
    <p class="project-metric-value">68.4%</p>
    <p class="project-metric-delta">+1.9 points</p>
  </div>
</div>

Scores are averaged over four held-out targets per benchmark. Gains are over CLUE + ORIENT on BraTS 2021 and MADA on MAMA-MIA, the strongest matched-budget baselines.

At the same source budget with only two target masks, TAC falls below the strongest comparator on both benchmarks. Target validation annotations are used separately for checkpoint selection.

TAC is under review at CVPR 2027. The companion manuscript was submitted to the Data4VFM Workshop at WACV 2027.

<figure class="tac-overview">
  <a href="{{ '/assets/img/tac-overview.png' | relative_url }}" aria-label="Open the full-size TAC workflow diagram">
    <img src="{{ '/assets/img/tac-overview.png' | relative_url }}" width="1800" height="1000" alt="Target masks guide source case selection and join the selected source cases for final training." decoding="async">
  </a>
  <figcaption>Acquired target masks guide source curation and supervise final training.</figcaption>
</figure>

## The problem

Under a limited annotation budget, a learner must decide which target examples to label. In cross-center medical imaging, it must also decide which examples from a heterogeneous source pool should remain in training. Treating these decisions separately can leave the training set poorly matched to the target domain.

## The approach

TAC couples active target acquisition with source selection. Queried target labels become reliability anchors for constructing compact, target-aligned source subsets. The aim is to use limited target supervision to improve both the target evidence available to the learner and the composition of its source training data.

TAC complements [TAVO]({{ '/projects/tavo/' | relative_url }}): TAVO uses a fixed labeled target support set to rank source cases, while TAC studies how target acquisition and source curation can work together.

TAC uses predictions from a full-source warm-up checkpoint to select target cases for annotation. It clusters candidates using weights based on foreground-aware uncertainty, local prediction inconsistency, and prediction stability. It then estimates source reliability using distributional similarity to the acquired target cases, gradient agreement, and prototype compatibility. The last two signals use the acquired masks. Reliability-weighted coverage selects a source subset for final training alongside the annotated target cases. TAC preserves the downstream segmentation architecture, supervised loss, and inference procedure.

## Coupled data curation

_What to Label, What to Train On: Coupled Data Curation for Cross-Domain Medical Segmentation_ is a companion manuscript submitted to the Data4VFM Workshop at WACV 2027. It examines how target acquisition and source selection interact. On BraTS 2021 at the same 10-target and 150-source budgets, replacing random acquisition with TAC acquisition lowers mean Dice by 0.61 points with random source selection and raises it by 2.20 points with TAC source selection.

## My contribution

I led the research as first author at USC under the supervision of [Prof. Ruishan Liu](https://viterbi-web.usc.edu/~ruishanl/). I developed the data-curation and evaluation workflows, including:

- Source-target split construction and active-learning baselines.
- Budget-aware selection of target labels and source training subsets.
- Multi-budget training, metric aggregation, and ablation pipelines for studying label scarcity and distribution shift.

**Stack**

<ul class="project-stack" aria-label="Stack">
  <li>PyTorch</li>
  <li>MONAI</li>
  <li>CUDA</li>
  <li>Active learning</li>
  <li>Source-data selection</li>
  <li>Linux/Slurm experiment pipelines</li>
</ul>

[View manuscript listing]({{ '/publications/' | relative_url }}) · [All projects]({{ '/projects/' | relative_url }})
