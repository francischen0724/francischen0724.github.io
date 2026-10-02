---
layout: page
title: projects
permalink: /projects/
description: agentic optimization, training-data curation, and medical imaging.
nav: true
nav_order: 3
---

My research asks how AI systems can use limited data and computation more effectively, from selecting training examples to allocating expensive optimization calls.

## [RadOncGym: Agentic Radiotherapy Optimization]({{ '/projects/radonc-gym/' | relative_url }})

An agent environment for tuning 12 radiotherapy planning-objective weights. Agents combine fast surrogate feedback with selectively requested full Gurobi solves. Evaluated across 600 patient-prediction contexts, the framework supports controlled comparisons of agent memory, role structures, and numerical optimizers.

**Focus:** LLM agents, multi-fidelity optimization, evaluation, and radiotherapy planning.<br>
**Role:** Research lead and first author.

## [TAVO: Target-Aware Source Curation]({{ '/projects/tavo/' | relative_url }})

A training-data curation framework that combines target similarity, gradient compatibility, coverage, and diversity to select useful external cases for a target clinical center. Tested across eight held-out targets in brain and breast tumor segmentation, with no change to the downstream model or inference procedure.

**Focus:** Data valuation, domain shift, budget-aware selection, and medical image segmentation.<br>
**Role:** First author.

## [TAC: Target-Anchored Coverage]({{ '/projects/tac/' | relative_url }})

A source-target curation method that couples active target-label acquisition with source-data selection. Newly queried target labels guide the construction of compact training subsets under annotation constraints and cross-center distribution shift.

**Focus:** Active learning, source-target curation, and annotation-efficient learning.<br>
**Role:** First author.

For my work on speech-data pipelines and distributed systems, see my [CV]({{ '/cv/' | relative_url }}).
