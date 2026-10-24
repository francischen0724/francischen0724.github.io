---
layout: about
title: about
permalink: /
subtitle: Agentic AI, Full-Stack Engineering & Data-Centric ML

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

I build AI systems that make better use of limited data and computation, turning research ideas into reliable software. My work spans **agentic AI, data-centric machine learning, computer vision, and production engineering**. One question connects much of my work:

**Which data is most useful, and when is expensive computation actually worth it?**

At USC's Lab for ML, Health and Biomedicine, advised by Prof. Ruishan Liu, I led research exploring both sides of this question. [RadOncGym]({{ '/projects/radonc-gym/' | relative_url }}) studies how agents decide when expensive computation is worth the cost, reducing full evaluations by **81%** while retaining **95%** of optimization gains in our benchmarks. [TAVO]({{ '/projects/tavo/' | relative_url }}) and [TAC]({{ '/projects/tac/' | relative_url }}) investigate which source examples to select and which target samples to label under distribution shift. With just **12% of the available source data**, TAVO outperformed the strongest fixed-selection baseline. Two first-author papers on RadOncGym and TAVO were accepted at **WACV 2027**.

I bring that same focus on reliability and efficiency into production AI at **EGUOO Wellness**, where I built a stateful LangGraph agent combining visual information extraction, evidence-grounded retrieval, and personalized recommendations. Across 60+ held-out scenarios, the system improved valid recommendation success from **71% to 95%** while reducing inference cost per successful task by **35%**.

Previously, at **2 Cube Global**, I applied data-curation ideas from TAVO to real-world speech ML pipelines, processing 80+ hours of audio into 45K aligned utterances for model adaptation and evaluation. At **Xiaomi**, I worked on distributed storage and performance optimization across a 60-node Linux environment, gaining hands-on experience with large-scale data infrastructure.

Beyond my core research, I've explored [reasoning distillation for compact vision-language models]({{ '/projects/vlm-distillation/' | relative_url }}) and co-developed [ZeroWasteFashionAI]({{ '/projects/zero-waste-fashion/' | relative_url }}), a sketch-to-garment prototype combining computer vision, multimodal understanding, and optimization.

I earned my **M.S. in Computer Science (Artificial Intelligence) from USC in May 2026**. I'm seeking **Machine Learning Engineer, Research Engineer, and Applied Scientist** opportunities in agentic AI, multimodal learning, data-centric ML, and ML systems. I'm open to relocation.

[CV (PDF)]({{ '/assets/pdf/cv.pdf' | relative_url }}) · [GitHub](https://github.com/francischen0724) · [LinkedIn](https://www.linkedin.com/in/xiwen-chen-franciscxw/) · [Email](mailto:xiwenc@usc.edu)

## Research Interests

Agentic AI & evaluation · Data-centric ML · Multimodal learning & distillation · Budget-aware optimization · Active learning · Learning under distribution shift
