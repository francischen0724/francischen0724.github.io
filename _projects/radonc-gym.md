---
layout: page
title: RadOnc-Gym
description: Cost-aware agentic planning environment for radiotherapy optimization.
img:
importance: 3
category: research
---

RadOnc-Gym is a Gym-style environment for cost-aware LLM/RL planning in radiotherapy. Agents iteratively adjust clinical objectives while trading off fast surrogate feedback against expensive Gurobi re-optimization and clinical-score verification calls.

The environment extends an OpenKBP-Opt/Gurobi pipeline into a configurable optimization simulator with tunable objective weights, optimization modes, plan-dose generation, DVH feedback, and clinical scoring. The broader goal is to study selective verifier use under limited evaluation budgets.

**Role:** Research assistant, Lab for ML, Health and Biomedicine at USC.

**Stack:** Python, Gurobi, Gym-style RL environments, LLM/RL planning loops, surrogate scoring, and clinical-score verification.
