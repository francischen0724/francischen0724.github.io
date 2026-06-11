---
layout: page
title: projects
permalink: /projects/
description: research projects and applied machine learning systems.
nav: true
nav_order: 3
---

<div class="projects">
  <div class="card mt-3 p-3">
    <h4><a href="{{ '/projects/tavo/' | relative_url }}">TAVO: Target-Aware Adaptive Data Valuation</a></h4>
    <p>
      A data-centric AI framework for budgeted cross-domain medical image segmentation. TAVO addresses unstable single-criterion source selection by combining feature- and gradient-based valuation signals through surrogate-guided optimization.
    </p>
    <p class="mb-0"><strong>Keywords:</strong> data valuation, source curation, domain adaptation, medical image segmentation, PyTorch, MONAI.</p>
  </div>

  <div class="card mt-3 p-3">
    <h4><a href="{{ '/projects/tac/' | relative_url }}">TAC: Target-Anchored Coverage</a></h4>
    <p>
      An annotation-efficient source-target curation method for cross-domain learning. TAC uses actively queried target labels as reliability anchors for compact, target-aligned source subset construction.
    </p>
    <p class="mb-0"><strong>Keywords:</strong> active learning, target labels, source selection, label scarcity, distribution shift.</p>
  </div>

  <div class="card mt-3 p-3">
    <h4><a href="{{ '/projects/radonc-gym/' | relative_url }}">RadOnc-Gym: Cost-Aware Agentic Planning for Radiotherapy</a></h4>
    <p>
      A Gym-style LLM/RL planning environment for radiotherapy optimization. Agents iteratively adjust clinical objectives while trading off surrogate scoring against expensive Gurobi re-optimization and DVH/clinical-score verification calls.
    </p>
    <p class="mb-0"><strong>Keywords:</strong> agentic AI, reinforcement learning, radiotherapy planning, Gurobi, surrogate verification.</p>
  </div>
</div>
