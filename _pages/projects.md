---
layout: page
title: projects
permalink: /projects/
description: agentic systems, data-centric learning, and optimization under limited resources.
nav: true
nav_order: 3
---

I study how AI systems should allocate training data, labels, computation, and expensive evaluations. These projects connect method design with reproducible experiments and systems engineering.

## [RadOncGym: Agentic Optimization Under Expensive Feedback]({{ '/projects/radonc-gym/' | relative_url }})

When evaluating a decision is expensive, an agent must choose both its next action and when to pay for reliable feedback. I built an environment for this problem using radiotherapy dose-mimicking optimization as a testbed: agents tune **12 objective weights**, use fast surrogate feedback, and decide when to request a full Gurobi solve.

**Result:** Across **600 patient-prediction contexts**, a 16-turn, three-solve agent configuration reduces mean clinical-criterion violation by **0.613 Gy** relative to all-one weights. It remains competitive with 16-solve numerical baselines while using **75.0-77.6% less runtime**. The benchmark also compares nine configurations of agent memory and roles.

**Focus:** Agentic AI, evaluation, multi-fidelity optimization, and budget-aware decisions.<br>
**Tools:** Python, Gymnasium, Gurobi, scikit-learn.<br>
**Role:** Research lead and first author.

## [TAVO: Target-Aware Source Curation]({{ '/projects/tavo/' | relative_url }})

Which training examples are useful for a particular target domain? TAVO combines **eight complementary signals** for target relevance, gradient compatibility, source coverage, and diversity, then learns target- and budget-specific combinations through validation-guided search. The resulting training subset leaves the downstream model, loss, and inference procedure unchanged.

**Result:** At a **150-case source budget**, TAVO improves target-averaged Dice by **1.9 points over the strongest fixed selector** and **2.2 points over the strongest budget-matched adaptation baseline** on MAMA-MIA. Evaluation covers eight held-out targets across BraTS 2021 and MAMA-MIA, with OfficeHome as a cross-task control.

**Focus:** Data-centric ML, training-data curation, domain shift, and budget-aware optimization.<br>
**Tools:** PyTorch, CUDA, EfficientViT, nnU-Net, ResNet-50.<br>
**Role:** First author.

## [TAC: Target-Anchored Source-Target Curation]({{ '/projects/tac/' | relative_url }})

TAC connects two resource-allocation decisions: which target examples to annotate, and which source examples to use for training. Newly queried target labels act as reliability anchors for constructing compact, target-aligned subsets under annotation constraints and distribution shift.

**Result:** In held-out-target experiments at a **12% source-data budget**, TAC improves Dice by **1.5 points over the strongest baseline** and **4.1 points over full-source training**.

**Focus:** Active learning, source-target curation, data-efficient learning, and domain adaptation.<br>
**Tools:** PyTorch, MONAI, CUDA.<br>
**Role:** First author.

## Selected Engineering Work

### Speech AI & Data Pipelines - 2 Cube Global

Adapted F5-TTS and evaluated it against zero-shot Qwen3-TTS for multilingual notifications. Built Python/Librosa pipelines for **80+ hours of speech and 45K aligned utterances**, filtering 16% misaligned samples to support model adaptation and held-out evaluation.

### Distributed Storage Systems - Xiaomi

Worked on erasure-coded storage across a **60-node Linux environment**, building reliability and failure-analysis workflows with **50+ client-I/O correctness scenarios**. Performance work covered eight coding baselines and 48 paired tests, improving upload throughput by **22%** and recovery latency by **12%**.

For experience details, see my [CV]({{ '/cv/' | relative_url }}). For manuscript titles and status, see [Publications]({{ '/publications/' | relative_url }}).
