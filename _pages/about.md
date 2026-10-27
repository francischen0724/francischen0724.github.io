---
layout: about
title: about
permalink: /
subtitle: >-
  <span style="display: block; font-size: 1.25rem; font-weight: 500; margin-bottom: 0.35rem;">ML Researcher &amp; Engineer</span>
  <span style="display: block;">USC M.S. in Computer Science (AI) · Los Angeles, CA · Open to Relocate</span>

profile: false
selected_papers: true
social: true

announcements:
  enabled: false
  scrollable: false
  limit: 3

latest_posts:
  enabled: false
  scrollable: true
  limit: 3
---

<figure style="float: right; width: 30%; min-width: 120px; max-width: 260px; margin: 0 0 1rem 1.5rem;">
  <img
    src="{{ '/assets/img/profile.jpg' | relative_url }}"
    alt="Xiwen Chen"
    class="img-fluid z-depth-1 rounded"
    width="1279"
    height="1920"
    style="width: 100%; height: auto;"
    loading="eager"
    decoding="async"
  >
</figure>

I build AI systems that make better use of limited data and computation, turning research ideas into reliable software. My work spans **agentic AI, data-centric ML, computer vision, and production engineering**. One question connects much of my work:

<strong style="font-weight: 700;">Which data is most useful, and when is expensive computation actually worth it?</strong>

At USC, advised by [Prof. Ruishan Liu](https://viterbi-web.usc.edu/~ruishanl/), I led two research directions. [RadOncGym]({{ '/projects/radonc-gym/' | relative_url }}) explores when agents should use costly evaluations, reducing full evaluations by **81%** while retaining **95%** of optimization gains. [TAVO]({{ '/projects/tavo/' | relative_url }}) and [TAC]({{ '/projects/tac/' | relative_url }}) focus on data selection and generalization under distribution shift, with TAVO outperforming the strongest fixed-selection baseline using just **12% of source data**. My work on RadOncGym and TAVO resulted in **two first-author papers accepted at WACV 2027**.

At [**EGUOO Wellness**]({{ '/projects/eguoo-wellness/' | relative_url }}), I owned the end-to-end development and AWS deployment of an AI wellness platform with a stateful LangGraph agent. A **1,000-participant A/B test** increased completion from **43% to 78%** and reduced average completion time by **45%**. Across **320 pilot recommendations**, the agent achieved **95% constraint validity**, **2.2 s P95 latency**, and **35% lower inference cost per successful task** than a stateless LLM.

Previously, I applied data-curation ideas to speech ML pipelines at [**2 Cube Global**]({{ '/projects/2-cube-speech-ai/' | relative_url }}) and worked on distributed-storage performance and reliability across a **60-node Linux environment** at [**Xiaomi**]({{ '/projects/xiaomi-storage/' | relative_url }}).

<strong style="color: #e53935; font-weight: 700;">Actively seeking AI/ML, software engineering, and applied research roles.</strong>

## Research Interests

Agentic AI & evaluation · Data-centric ML · Multimodal learning & distillation · Budget-aware optimization · Active learning · Learning under distribution shift
