---
layout: page
title: projects
permalink: /projects/
description: full-stack AI platforms, agentic systems, data-centric learning, and multimodal AI.
nav: true
nav_order: 3
---

I build AI platforms and study how intelligent systems should allocate training data, labels, computation, and expensive evaluations. These projects connect method design with reproducible experiments and systems engineering.

## [EGUOO Wellness: Full-Stack Agentic AI Platform]({{ '/projects/eguoo-wellness/' | relative_url }})

Owned the end-to-end development and AWS deployment of a wellness platform with conversational assessments, persistent user profiles, and personalized recommendations. A **stateful LangGraph agent** combines visual label extraction, evidence-grounded RAG, and constraint-aware recommendations, backed by versioned profile updates and reliable asynchronous processing.

**Product results:** A **1,000-participant A/B test** improved completion rate from **43% to 78%** and reduced average completion time by **45%**.

**Agent results:** Across **320 pilot recommendations**, the agent achieved **95% constraint validity**, **88% expert approval**, **2.2 s P95 latency**, and **35% lower inference cost per successful task** compared with a stateless LLM.

**Focus:** Agentic AI, full-stack development, persistent state, and evaluation.<br>
**Tools:** Next.js, FastAPI, PostgreSQL, AWS, Terraform, LangGraph.<br>
**Role:** Software Engineer, May 2026–Present.

## [RadOncGym: Agentic Optimization Under Expensive Feedback]({{ '/projects/radonc-gym/' | relative_url }})

When evaluating a decision is expensive, an agent must choose both its next action and when to pay for reliable feedback. I built an environment for this problem using radiotherapy dose-mimicking optimization as a testbed: agents tune **12 objective weights**, use fast surrogate feedback, and decide when to request a full Gurobi solve.

**Result:** Across **600 patient-prediction contexts**, the three-solve LLM agent outperforms evaluated non-agent methods under the same solve budget. It remains competitive with their 16-solve variants at **75.0–77.6% lower normalized runtime**. The paper also compares **nine memory and role configurations**.

**Focus:** Agentic AI, evaluation, multi-fidelity optimization, and budget-aware decisions.<br>
**Tools:** Python, Gymnasium, Gurobi, scikit-learn.<br>
**Role:** Research lead and co-first author. **Accepted to WACV 2027.**

[PDF]({{ '/assets/pdf/RadOncGym_WACV_2027_Camera_Ready.pdf' | relative_url }}) · [Code](https://github.com/miaot-usc/RadOncGym)

## [TAVO: Target-Aware Source Curation]({{ '/projects/tavo/' | relative_url }})

Which training examples are useful for a particular target domain? TAVO combines **eight complementary signals** for target relevance, gradient compatibility, source coverage, and diversity, then learns target- and budget-specific combinations through validation-guided search. The resulting training subset leaves the downstream model, loss, and inference procedure unchanged.

**Result:** At a **150-case source budget**, TAVO improves target-averaged Dice over the strongest fixed selector by **1.0 points on BraTS 2021 and 1.9 on MAMA-MIA**, and over the strongest budget-matched adaptation baseline by **1.0 and 2.2 points**, respectively. OfficeHome provides a cross-task classification control.

**Focus:** Data-centric ML, training-data curation, domain shift, and budget-aware optimization.<br>
**Tools:** PyTorch, CUDA, EfficientViT, nnU-Net, ResNet-50.<br>
**Role:** Co-first author. **Accepted to WACV 2027.**

[PDF]({{ '/assets/pdf/TAVO_WACV_2027_Camera_Ready.pdf' | relative_url }}) · [Code](https://github.com/francischen0724/TAVO)

## [TAC: Target-Anchored Source-Target Curation]({{ '/projects/tac/' | relative_url }})

TAC connects two resource-allocation decisions: which target examples to annotate, and which source examples to use for training. Newly queried target labels act as reliability anchors for constructing compact, target-aligned subsets under annotation constraints and distribution shift.

**Result:** In held-out-target experiments at a **12% source-data budget**, TAC improves Dice by **1.5 points over the strongest baseline** and **4.1 points over full-source training**.

**Focus:** Active learning, source-target curation, data-efficient learning, and domain adaptation.<br>
**Tools:** PyTorch, MONAI, CUDA.<br>
**Role:** First author. **Under review at ICLR 2027.**

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

### [Speech AI & Data Pipelines - 2 Cube Global]({{ '/projects/2-cube-speech-ai/' | relative_url }})

Adapted F5-TTS and evaluated it against zero-shot Qwen3-TTS for multilingual notifications. Built Python/Librosa pipelines for **80+ hours of speech and 45K aligned utterances**, filtering **16% misaligned samples** to support model adaptation and evaluation.

**Focus:** Speech data quality, domain adaptation, and quality–cost evaluation.<br>
**Tools:** Python, Librosa, F5-TTS, Qwen3-TTS.<br>
**Role:** AI Engineer Intern, May–September 2025.

[Project details]({{ '/projects/2-cube-speech-ai/' | relative_url }})

### [Distributed Storage Systems - Xiaomi]({{ '/projects/xiaomi-storage/' | relative_url }})

Worked on erasure-coded storage across a **60-node Linux environment**, building reliability and failure-analysis workflows with **50+ client-I/O correctness scenarios**. Performance work covered eight coding baselines and 48 paired tests, improving encoding throughput by **81.5%**, end-to-end upload throughput by **22%**, and recovery latency by **12%**. Validation separated coding-library correctness from file I/O and failure recovery, covering **2KB–1GB workloads**.

**Focus:** Distributed storage, erasure coding, reliability, and performance analysis.<br>
**Tools:** C/C++, Bash, Linux, fio, GDB, Valgrind.<br>
**Role:** Research Engineer Intern, May–September 2024.

[Project details]({{ '/projects/xiaomi-storage/' | relative_url }})

For experience details, see [Experience]({{ '/experience/' | relative_url }}) and my [CV]({{ '/cv/' | relative_url }}). For manuscript titles and status, see [Publications]({{ '/publications/' | relative_url }}).
