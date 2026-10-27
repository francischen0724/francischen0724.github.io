---
layout: page
title: experience
permalink: /experience/
description: engineering, research, education, and technical background.
nav: true
nav_order: 4
---

My work combines AI research, evaluation, and the engineering needed to put intelligent systems into practice. [Download my CV]({{ '/assets/pdf/cv.pdf' | relative_url }}) for a one-page overview.

## American Best Life Inc.

**Software Engineer | Full-Stack & Agentic AI**<br>
May 2026–Present · Irvine, CA (Remote)

- Owned the development and AWS deployment of a full-stack AI wellness platform using **Next.js, FastAPI, PostgreSQL, and Terraform**. A **1,000-participant A/B test** improved completion rate from **43% to 78%** and reduced average completion time by **45%**.
- Architected a **stateful LangGraph agent** combining VLM-based label extraction, evidence-grounded RAG, and constraint-aware recommendations. Implemented versioned profile updates, optimistic concurrency, and idempotent asynchronous processing.
- Benchmarked the agent against a stateless LLM on **320 pilot recommendations**, achieving **95% constraint validity**, **88% expert approval**, **2.2 s P95 latency**, and **35% lower inference cost per successful task**.

[Project details]({{ '/projects/eguoo-wellness/' | relative_url }})

## Keck School of Medicine, USC | Radiation Oncology

**Research Lead | Agentic AI, Optimization & Evaluation**<br>
May 2025–October 2026 · Los Angeles, CA<br>
Advisor: [Prof. Ruishan Liu](https://viterbi-web.usc.edu/~ruishanl/)

- Led development of **RadOncGym**, a Gymnasium-based framework for radiotherapy dose-mimicking optimization, integrating a Gurobi-backed simulator with **12 objective-weight variables**, multi-fidelity feedback, and budget-aware execution.
- Built standardized agent and optimizer interfaces, automated experiment orchestration, reproducible trajectory logging, and end-to-end evaluation across **600 patient-prediction contexts**.
- Co-first author of the **WACV 2027 accepted** paper. The camera-ready evaluation compares LLM agents with numerical optimizers and examines nine memory and role configurations.

[RadOncGym: paper, code, and results]({{ '/projects/radonc-gym/' | relative_url }})

## 2 Cube Global

**AI Engineer Intern | ML Data Pipelines & Evaluation**<br>
May 2025–September 2025 · Los Angeles, CA

- Built Python/Librosa curation and validation pipelines for **80+ hours of audio and transcripts**, producing **45K aligned utterances** and filtering **16% misaligned samples**.
- Adapted **F5-TTS** for multilingual supply-chain speech and benchmarked against zero-shot **Qwen3-TTS**, evaluating quality and cost to inform technology selection.

[Project details]({{ '/projects/2-cube-speech-ai/' | relative_url }})

## Lab for ML, Health and Biomedicine, USC

**Research Assistant | Data-Centric ML & Training Data Curation**<br>
September 2024–May 2025 · Los Angeles, CA<br>
Advisor: [Prof. Ruishan Liu](https://viterbi-web.usc.edu/~ruishanl/)

- Led **TAVO and TAC**, developing training-data curation methods that combine target-conditioned selection, multi-fidelity search, and active acquisition under distribution shift.
- Built reproducible **multi-GPU PyTorch/CUDA pipelines with Slurm**, automated multi-budget experiments, and evaluated TAVO across BraTS 2021, MAMA-MIA, and OfficeHome.
- **TAVO: accepted to WACV 2027 (co-first author). TAC: under review at ICLR 2027 (first author).**

[TAVO]({{ '/projects/tavo/' | relative_url }}) · [TAC]({{ '/projects/tac/' | relative_url }})

## Xiaomi Technology Co., Ltd.

**Research Engineer Intern | Distributed Systems & Cloud Infrastructure**<br>
May 2024–September 2024 · Beijing & Shenzhen, China

- Integrated network and erasure-coding components into the NCDSS distributed-storage system and validated **K=4, M=2 erasure-coded storage across a 60-node Linux environment**.
- Built **50+ client-I/O correctness scenarios** covering encoding, decoding, repair, update, file I/O, and recovery under simulated failures across **2KB–1GB workloads**.
- Benchmarked **eight baselines across 48 paired tests**, improving encoding throughput by **81.5%**, upload throughput by **22%**, and recovery latency by **12%**.

[Project details]({{ '/projects/xiaomi-storage/' | relative_url }})

## Education

**University of Southern California** · Los Angeles, CA<br>
M.S. in Computer Science, Artificial Intelligence Track · January 2024–May 2026<br>
GPA: **3.71 / 4.00**

**South China Normal University** · Guangzhou, China<br>
B.E. in Software Engineering · September 2019–July 2023<br>
GPA: **3.87 / 4.00**

## Technical Skills

**Languages:** Python, C/C++, Java, SQL, Bash, TypeScript.<br>
**Systems & Backend:** Linux, Docker, Kubernetes, AWS, Terraform, CI/CD, Next.js, FastAPI, PostgreSQL, Kafka, Spark, distributed systems.<br>
**AI/ML Systems:** PyTorch, CUDA, Slurm, Hugging Face Transformers, scikit-learn, Gymnasium, SGLang, LangGraph, RAG, Gurobi.
