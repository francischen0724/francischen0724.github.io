---
layout: page
title: VLM Distillation
description: Transferring structured visual reasoning from an 11B teacher to a 2B student.
img:
importance: 4
category: research
---

**Distilling small vision-language models with structured reasoning**

This team project studies whether structured explanations from a larger vision-language model can improve a smaller model on visual question answering. Our Structured Visual Reasoning Distillation (SVRD) framework uses **LLaVA-CoT (11B)** as the teacher and **Moondream (2B)** as the student.

**My contribution:** Method design, data processing, and final evaluation.<br>
**Status:** Team project with a technical report and public code.

## The problem

A smaller vision-language model can require less model storage while struggling with questions that combine image interpretation and reasoning. The project investigates whether teacher-generated explanations provide useful training supervision beyond the final answer.

## The approach

1. Filter ScienceQA to questions with images and prepare the questions, answer options, and training supervision.
2. Use the teacher to generate a structured question summary, image caption, and rationale. Training-time rationale generation can use the ground-truth answer and supporting context.
3. Fine-tune the student's text model on the structured rationale and answer sequence while keeping its vision encoder frozen.
4. Evaluate the student using the image, question, and answer options, without supplying the reference answer. Measure overall and topic-level accuracy and inspect generated answers for failure cases.

The report describes training on **2,000 examples** using a single **A100 80GB GPU**. My work covered the method and data pipeline, followed by final evaluation; model training was part of the team's implementation.

## Evaluation and results

Table 1 of the [project report](https://github.com/yqlu1015/vllm_distillation/blob/main/svrd.pdf) reports the following results on the image-containing ScienceQA test subset:

| Model               | Parameters | Accuracy | Reported test-run inference time |
| ------------------- | ---------: | -------: | -------------------------------: |
| Base Moondream      |         2B |   46.20% |                          158 min |
| Distilled Moondream |         2B |   53.54% |                          279 min |
| LLaVA-CoT teacher   |        11B |   78.82% |                          371 min |

Distillation improves the student's accuracy by **7.34 percentage points**. The distilled model uses fewer parameters and less test-run inference time than the teacher, while remaining less accurate. It takes longer than the base student to generate its structured responses. These timings describe the reported evaluation runs, not a deployment latency guarantee.

## What the evaluation revealed

The report documents cases where the generated rationale identifies the correct answer but the final option is wrong. This makes answer extraction and rationale-answer consistency useful evaluation targets alongside overall accuracy. Performance also varies by topic; broader datasets and stronger controls would be needed to establish generalization beyond this experiment.

**Stack:** Python, PyTorch, Hugging Face Transformers, ScienceQA, LLaVA-CoT, and Moondream.

[Code](https://github.com/yqlu1015/vllm_distillation) · [Project report](https://github.com/yqlu1015/vllm_distillation/blob/main/svrd.pdf) · [All projects]({{ '/projects/' | relative_url }})
