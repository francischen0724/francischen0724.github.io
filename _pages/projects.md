---
layout: page
title: projects
permalink: /projects/
description: agentic systems, data-centric learning, multimodal AI, and optimization under limited resources.
nav: true
nav_order: 3
---

I study how AI systems should allocate training data, labels, computation, and expensive evaluations. These projects connect method design with reproducible experiments and systems engineering.

## [RadOncGym: Agentic Optimization Under Expensive Feedback]({{ '/projects/radonc-gym/' | relative_url }})

When evaluating a decision is expensive, an agent must choose both its next action and when to pay for reliable feedback. I built an environment for this problem using radiotherapy dose-mimicking optimization as a testbed: agents tune **12 objective weights**, use fast surrogate feedback, and decide when to request a full Gurobi solve.

**Result:** Across **600 contexts**, benchmarking against black-box optimization policies reduced full evaluations by **81%** while retaining **95% of downstream objective gains** under matched compute budgets. The evaluation also compares **nine agent configurations** spanning three memory mechanisms and three role structures.

**Focus:** Agentic AI, evaluation, multi-fidelity optimization, and budget-aware decisions.<br>
**Tools:** Python, Gymnasium, Gurobi, scikit-learn.<br>
**Role:** Research lead and first author.

## [TAVO: Target-Aware Source Curation]({{ '/projects/tavo/' | relative_url }})

Which training examples are useful for a particular target domain? TAVO combines **eight complementary signals** for target relevance, gradient compatibility, source coverage, and diversity, then learns target- and budget-specific combinations through validation-guided search. The resulting training subset leaves the downstream model, loss, and inference procedure unchanged.

**Result:** Across held-out targets at a **12% source-data budget**, TAVO improves Dice by **1.9 points over fixed-selector baselines** and **2.2 points over domain-adaptation baselines**. The evaluation covers BraTS 2021 and MAMA-MIA, with OfficeHome as a cross-task classification control.

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

### [Distilling Small Vision-Language Models with Structured Reasoning]({{ '/projects/vlm-distillation/' | relative_url }})

Can structured teacher explanations improve a smaller vision-language model? This team project distills question summaries, image captions, and reasoning from **LLaVA-CoT (11B)** into **Moondream (2B)** for visual question answering.

**Result:** On the image-containing ScienceQA test subset, the project report records an accuracy increase from **46.20% to 53.54%**, a **7.34 percentage-point gain** over the base student. The project evaluates the trade-off between answer quality, model size, and inference time.

**Focus:** Multimodal learning, knowledge distillation, data preparation, and evaluation.<br>
**Tools:** Python, PyTorch, Hugging Face Transformers, ScienceQA.<br>
**My contribution:** Method design, data processing, and final evaluation.

### [ZeroWasteFashionAI: Sketch Processing and Pattern Layout]({{ '/projects/zero-waste-fashion/' | relative_url }})

Co-led an end-to-end sketch-to-garment prototype connecting sketch vectorization, multimodal garment-component recognition, structured tech-pack summaries, and 2D pattern placement. The workflow explores how AI can help designers prepare digital garment information and assess fabric use.

**Result:** The team's demonstrated **10-piece bin-packing example** reports **29.97% lower net fabric consumption** and **5.41 seconds** of processing time. Net consumption accounts for reusable offcuts; these are prototype case results. The project also includes an experimental PPO placement implementation, with CLO 3D integration and virtual fitting identified as future directions.

**Focus:** Computer vision, multimodal workflows, layout optimization, and prototyping.<br>
**Role:** Co-leader, January-May 2025.

### Speech AI & Data Pipelines - 2 Cube Global

Adapted F5-TTS and evaluated it against zero-shot Qwen3-TTS for multilingual notifications. Built Python/Librosa pipelines for **80+ hours of speech and 45K aligned utterances**, filtering 16% misaligned samples to support model adaptation and held-out evaluation.

### Distributed Storage Systems - Xiaomi

Worked on erasure-coded storage across a **60-node Linux environment**, building reliability and failure-analysis workflows with **50+ client-I/O correctness scenarios**. Performance work covered eight coding baselines and 48 paired tests, improving encoding throughput by **81.5%**, end-to-end upload throughput by **22%**, and recovery latency by **12%**. Validation separated coding-library correctness from file I/O and failure recovery, covering **2KB-1GB workloads**.

For experience details, see my [CV]({{ '/cv/' | relative_url }}). For manuscript titles and status, see [Publications]({{ '/publications/' | relative_url }}).
