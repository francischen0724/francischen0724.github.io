---
layout: page
title: EGUOO Wellness
description: A full-stack AI platform with stateful agents, evidence-grounded retrieval, and personalized recommendation workflows.
img:
importance: 1
category: engineering
---

**From conversational assessments to persistent, personalized recommendations**

At EGUOO Wellness, I build a full-stack AI platform that connects conversational assessments, visual label extraction, and evidence-grounded recommendations with persistent user profiles.

**Role:** Software Engineer | Full-Stack & Agentic AI.<br>
**Dates:** September 2026–Present.<br>
**Location:** Irvine, CA (Remote).

## The system

The platform uses **Next.js, FastAPI, and PostgreSQL**, deployed on **AWS with Terraform**. A stateful **LangGraph agent** combines three capabilities:

- **Visual understanding:** VLM-based extraction of information from labels.
- **Grounded retrieval:** RAG that brings relevant evidence into the recommendation workflow.
- **Personalization:** Recommendations that account for persistent user profiles and explicit constraints.

## Engineering for reliable state

Recommendations depend on the current user profile, so reliable state handling is part of the agent design. I implemented **versioned profile updates, optimistic concurrency, and idempotent asynchronous processing** to support consistent updates and retryable workflows.

The work spans the user-facing application, backend services, agent orchestration, database, infrastructure, and evaluation.

## Evaluation

I benchmarked the system against a **stateless LLM baseline across 60+ held-out scenarios**.

| Measure                                 | Result                          |
| --------------------------------------- | ------------------------------- |
| Constraint-valid recommendation success | **71% → 95%**                   |
| Expert approval                         | **88%**                         |
| Inference cost per successful task      | **35% lower than the baseline** |

The evaluation measures whether recommendations satisfy the stated constraints, whether experts approve them, and how much inference costs per successful task.

**Stack:** TypeScript, Next.js, Python, FastAPI, PostgreSQL, AWS, Terraform, LangGraph, VLMs, and RAG.

[Experience]({{ '/experience/' | relative_url }}) · [All projects]({{ '/projects/' | relative_url }})
