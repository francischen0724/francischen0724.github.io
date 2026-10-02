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

**Role:** Research lead and first author, Lab for ML, Health and Biomedicine, USC.<br>
**Status:** Manuscript under review at WACV 2027. The anonymous repo is not available during peer review. See [Publications]({{ '/publications/' | relative_url }}) for the full manuscript title.

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

The benchmark covers **600 contexts**, comparing **three frontier LLMs and one locally deployed open-source LLM** with black-box optimization policies. Evaluation spans objective quality, expensive-call usage, agent trajectories, and failure modes.

The benchmark results summarized in my [CV]({{ '/cv/' | relative_url }}) are:

| Measure                                  | Result |
| ---------------------------------------- | -----: |
| Reduction in full evaluations            |    81% |
| Downstream objective gains retained      |    95% |
| Memory and role configurations evaluated |      9 |

These results use matched compute budgets. The evaluation studies how memory design, planner/evaluator/critic roles, and access to expensive feedback affect decision quality. The surrogate supplies approximate screening feedback; final candidate selection uses successful full solves. The reported outcomes concern benchmark optimization, rather than clinical deployment.

## My contribution

I lead the environment and evaluation framework: modular action/state interfaces, budget-aware experiment orchestration, multi-fidelity feedback, reproducible trajectory logging, and end-to-end model evaluation. I also implement and compare memory and role configurations to examine where agent decisions succeed or fail.

**Stack:** Python, Gymnasium, Gurobi, scikit-learn, LLM agents, surrogate modeling, and reproducible evaluation pipelines.

[View manuscript listing]({{ '/publications/' | relative_url }}) · [All projects]({{ '/projects/' | relative_url }})
