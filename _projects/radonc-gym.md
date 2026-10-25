---
layout: page
title: RadOncGym
description: Studying how agents allocate expensive evaluations under a fixed computation budget.
img:
importance: 1
category: research
---

**Agentic optimization under expensive feedback**

When feedback is expensive, an agent must decide both what to try and when a more reliable evaluation is worth the cost. RadOncGym studies this decision using radiotherapy dose-mimicking optimization as a testbed, with controlled comparisons of agent behavior, memory, and evaluation budgets.

**Role:** Research lead and co-first author, Lab for ML, Health and Biomedicine, USC.<br>
**Status:** Accepted to **WACV 2027**.<br>
**Authors:** Tong Miao<sup>_</sup>, Shupeng Cheng<sup>_</sup>, Xiwen Chen<sup>\*</sup>, and [Ruishan Liu](https://viterbi-web.usc.edu/~ruishanl/). \* Equal contribution.

<div class="links">
  <a href="{{ '/assets/pdf/RadOncGym_WACV_2027_Camera_Ready.pdf' | relative_url }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener" aria-label="Read RadOncGym camera-ready PDF">PDF</a>
  <a href="https://github.com/miaot-usc/RadOncGym" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener" aria-label="RadOncGym code on GitHub">Code</a>
</div>

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

The camera-ready benchmark covers **60 OpenKBP head-and-neck patients**, each paired with **10 dose predictions**, for **600 patient-prediction contexts** per configuration. It compares LLM agents with numerical weight-tuning methods under explicit solve and turn budgets.

Under a **16-turn horizon and a three-solve budget**, the GPT-5.6 Sol agent with criterion-response contrast memory and a candidate-critic role improves over the context-matched plan with all 12 weights fixed at 1:

| Measure                           |         Improvement |
| --------------------------------- | ------------------: |
| Mean clinical-criterion violation | 0.6131 Gy reduction |
| DVH score                         | 0.5986 Gy reduction |
| Dose score                        | 0.2204 Gy reduction |

The agent outperforms all evaluated non-agent weight-tuning methods under the same three-solve budget. It remains competitive with their **16-solve variants while using 75.0–77.6% less normalized runtime**. The all-ones reference solve is excluded from the optimization solve budget.

The study also compares **nine memory and role configurations**. No configuration is best on every endpoint, and the paired comparisons do not establish a robust advantage for the critic role. The surrogate supplies screening feedback; final candidate selection uses successful full solves. See the [camera-ready paper]({{ '/assets/pdf/RadOncGym_WACV_2027_Camera_Ready.pdf' | relative_url }}) for the full protocol and results.

## My contribution

I led the environment and evaluation framework: modular action/state interfaces, budget-aware experiment orchestration, multi-fidelity feedback, reproducible trajectory logging, and end-to-end model evaluation. I also implemented and compared memory and role configurations to examine where agent decisions succeed or fail.

**Stack:** Python, Gymnasium, Gurobi, scikit-learn, LLM agents, surrogate modeling, and reproducible evaluation pipelines.

[Camera-ready PDF]({{ '/assets/pdf/RadOncGym_WACV_2027_Camera_Ready.pdf' | relative_url }}) · [Code](https://github.com/miaot-usc/RadOncGym) · [All projects]({{ '/projects/' | relative_url }})
