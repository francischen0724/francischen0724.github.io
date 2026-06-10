---
layout: page
title: RadOnc-Gym
description: Cost-aware agentic planning environment for radiotherapy optimization.
img:
importance: 3
category: research
---

RadOnc-Gym is a Gym-style environment for cost-aware LLM/RL planning in radiotherapy. Agents iteratively adjust clinical objectives while trading off fast surrogate feedback against expensive Gurobi re-optimization and clinical-score verification calls.

The environment wraps radiotherapy optimization into a state-action-reward loop for studying selective verifier use under limited evaluation budgets.
