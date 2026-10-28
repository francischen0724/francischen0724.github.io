---
layout: page
title: American Best Life Inc.
description: End-to-end development of an AI wellness platform, evaluated through a participant A/B test and pilot agent recommendations.
img:
importance: 1
category: engineering
---

**From conversational assessments to persistent, personalized recommendations**

At American Best Life Inc., I owned development from the initial implementation through AWS deployment of a full-stack AI wellness platform. It connects conversational assessments, visual label extraction, and evidence-grounded recommendations with persistent user profiles.

**Role:** Software Engineer | Full-Stack & Agentic AI.<br>
**Dates:** May 2026–Present.<br>
**Location:** Irvine, CA (Remote).

## The system

The platform uses **Next.js, FastAPI, and PostgreSQL**, deployed on **AWS with Terraform**. A stateful **LangGraph agent** combines three capabilities:

- **Visual understanding:** VLM-based extraction of information from labels.
- **Grounded retrieval:** RAG that brings relevant evidence into the recommendation workflow.
- **Personalization:** Recommendations that account for persistent user profiles and explicit constraints.

## Engineering for reliable state

Recommendations depend on the current user profile, so reliable state handling is part of the agent design. I implemented **versioned profile updates, optimistic concurrency, and idempotent asynchronous processing** to support consistent updates and retryable workflows.

The work spans the user-facing application, backend services, agent orchestration, database, infrastructure, and evaluation.

## Product evaluation

A **1,000-participant A/B test** measured completion rate and average completion time for the platform.

| Measure                 | Result        |
| ----------------------- | ------------- |
| Completion rate         | **43% → 78%** |
| Average completion time | **45% lower** |

## Agent evaluation

I benchmarked the stateful agent against a **stateless LLM baseline on 320 pilot recommendations**, measuring recommendation validity, expert approval, latency, and inference cost.

| Measure                            | Result                          |
| ---------------------------------- | ------------------------------- |
| Constraint validity                | **95%**                         |
| Expert approval                    | **88%**                         |
| End-to-end P95 latency             | **27% lower (66 s → 48 s)**     |
| Inference cost per successful task | **35% lower than the baseline** |

These agent results describe the pilot recommendation evaluation. The participant A/B test above measures the platform's completion outcomes.

**Stack:** TypeScript, Next.js, Python, FastAPI, PostgreSQL, AWS, Terraform, LangGraph, VLMs, and RAG.

[Experience]({{ '/experience/' | relative_url }}) · [All projects]({{ '/projects/' | relative_url }})
