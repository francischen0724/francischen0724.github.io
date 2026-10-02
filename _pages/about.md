---
layout: about
title: about
permalink: /
subtitle: Agentic AI, Data-Centric ML & Reliable Evaluation

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

I build AI systems that make better use of limited data and computation. As an ML researcher and engineer, I study how intelligent systems allocate these resources through agentic optimization, data-centric learning, and rigorous evaluation. One question connects much of my work:

**Which data is most useful, and when is expensive computation actually worth it?**

At USC's Lab for ML, Health and Biomedicine, advised by Prof. Ruishan Liu, I lead [RadOncGym]({{ '/projects/radonc-gym/' | relative_url }}), an agentic optimization environment for studying decision-making under expensive feedback. Using radiotherapy planning as a testbed, I study how agents use memory, coordinate specialized roles, and decide when to spend a limited budget on full optimization across **600 patient-prediction contexts**.

I also led two first-author projects on learning under distribution shift. [TAVO]({{ '/projects/tavo/' | relative_url }}) learns which source examples are most useful for a target domain under a fixed training budget, while [TAC]({{ '/projects/tac/' | relative_url }}) jointly studies which target examples to label and which source examples to retain for training. Together, they ask how carefully chosen data can improve generalization when labels and training budgets are limited.

Beyond my core research, I worked on [structured reasoning distillation for small vision-language models]({{ '/projects/vlm-distillation/' | relative_url }}), exploring how reasoning supervision from larger VLMs can improve compact models for visual question answering. I contributed to method design, data processing, and final evaluation. I also co-led [ZeroWasteFashionAI]({{ '/projects/zero-waste-fashion/' | relative_url }}), an end-to-end sketch-to-garment prototype combining computer vision, multimodal understanding, and garment-pattern layout optimization for more material-efficient design.

My engineering experience includes multilingual TTS adaptation and speech-data pipelines at 2 Cube Global, as well as distributed-storage reliability and performance engineering at Xiaomi. Across these settings, I enjoy building reproducible systems, designing careful evaluations, and understanding why a method succeeds or fails. I earned my M.S. in Computer Science (Artificial Intelligence) from USC in May 2026.

I am seeking **Machine Learning Engineer, Research Engineer, and Applied Scientist** opportunities in agentic AI, multimodal learning, data-centric ML, and ML systems, including healthcare applications. I am open to relocation.

[CV]({{ '/cv/' | relative_url }}) · [GitHub](https://github.com/francischen0724) · [LinkedIn](https://www.linkedin.com/in/xiwen-chen-franciscxw/) · [Email](mailto:xiwenc@usc.edu)

## Research Interests

Agentic AI & evaluation · Data-centric ML · Multimodal learning & distillation · Budget-aware optimization · Active learning · Learning under distribution shift
