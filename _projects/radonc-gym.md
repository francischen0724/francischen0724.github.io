---
layout: page
title: RadOncGym
description: Agents that tune radiotherapy planning objectives under a limited optimization budget.
img:
importance: 1
category: research
---

**An Agent-Based Framework for Radiotherapy Dose-Mimicking Optimization**

**Role:** Research lead and first author, Lab for ML, Health and Biomedicine, USC.<br>
**Status:** Manuscript under review, WACV 2027.

## The problem

An AI-predicted radiation dose is an intermediate representation: a planning optimizer must turn it into a physically constrained plan while balancing target coverage and organ-at-risk sparing. The weights assigned to these objectives affect the resulting plan, and evaluating each new set of weights requires an expensive optimization run.

RadOncGym makes this trade-off explicit. An agent searches for better objective weights while deciding which candidates justify a full planning solve.

## How it works

Built on OpenKBP-Opt and a Gurobi planning backend, the Gymnasium-based environment exposes **12 continuous objective weights**, covering target volumes, organs at risk, ring falloff, and posterior-neck sparing.

1. The agent receives a structured summary of patient anatomy, the predicted dose, previous feedback, and its remaining budget.
2. It proposes new weights and decides whether to request a full solve or stop.
3. A frozen surrogate ensemble rapidly estimates mean clinical-criterion violation and uncertainty. A full solve additionally returns exact violations, plan-specific dose-volume histogram (DVH) statistics, and a DVH plot.
4. The environment selects the best successfully solved candidate for final evaluation. Expert-reference information and benchmark DVH/dose scores are used only after plan selection.

The evaluation framework compares **nine memory-role configurations**: three memory mechanisms crossed with direct-planner, evaluator-planner, and candidate-critic structures. Standardized interfaces, experiment orchestration, and trajectory logs support comparisons with numerical optimization methods.

## Evaluation and results

The manuscript evaluates **60 OpenKBP patients paired with 10 dose predictions each**, giving **600 patient-prediction contexts** per configuration. The primary setting allows **16 turns and three full planning solves**.

Under this setting, the GPT-5.6 Sol configuration with criterion-response contrast memory and a candidate critic achieves the following mean improvements over the context-matched plan with all weights set to one:

| Endpoint                          |          Improvement |
| --------------------------------- | -------------------: |
| Mean clinical-criterion violation |   0.613 Gy reduction |
| DVH score                         | 0.599 Gy improvement |
| Dose score                        | 0.220 Gy improvement |

It outperforms the evaluated non-agent methods under the matched three-solve, 16-turn protocol, and remains competitive with their 16-solve variants while using **75.0-77.6% less runtime**. These are benchmark planning results; the comparison depends on the solve and turn budgets. The experiments also isolate the effects of solve timing, feedback content, and agent memory and roles.

**Stack:** Python, Gymnasium, Gurobi, scikit-learn, LLM agents, surrogate modeling, and reproducible evaluation pipelines.

[View manuscript listing]({{ '/publications/' | relative_url }}) · [All projects]({{ '/projects/' | relative_url }})
