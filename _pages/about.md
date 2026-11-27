---
layout: about
title: about
permalink: /
subtitle: >-
  <span style="display: block; font-size: 1.25rem; font-weight: 500; margin-bottom: 0.35rem;">ML Researcher &amp; Engineer</span>
  <span style="display: block;">USC M.S. in Computer Science (AI) · Los Angeles, CA · Open to Relocate</span>

profile: false
selected_papers: true
social: false

announcements:
  enabled: false
  scrollable: false
  limit: 3

latest_posts:
  enabled: false
  scrollable: true
  limit: 3
---

<div class="home-hero">
  <div class="home-hero-text">
    <p class="home-status"><span class="home-status-dot" aria-hidden="true"></span>Actively seeking AI/ML, software engineering, and applied research roles</p>

    <p class="home-intro-summary">
      I build AI systems that make better use of limited data and computation, turning research ideas into reliable software. My work spans
      <strong>agentic AI, data-centric ML, computer vision, and production engineering</strong>.
    </p>

    <div class="portfolio-actions home-intro-actions">
      <a class="portfolio-action portfolio-action-primary" href="{{ site.data.socials.cv_pdf | relative_url }}" download="Xiwen_Chen_CV.pdf">Download CV</a>
      <a class="portfolio-action" href="mailto:{{ site.data.socials.email }}">Email <i class="fa-solid fa-envelope" aria-hidden="true"></i></a>
      <a class="portfolio-action" href="https://github.com/{{ site.data.socials.github_username }}" target="_blank" rel="noopener">GitHub <i class="fa-brands fa-github" aria-hidden="true"></i></a>
      <a class="portfolio-action" href="https://www.linkedin.com/in/{{ site.data.socials.linkedin_username }}" target="_blank" rel="noopener">LinkedIn <i class="fa-brands fa-linkedin" aria-hidden="true"></i></a>
      <a class="portfolio-action" href="{{ site.data.socials.google_scholar.url }}" target="_blank" rel="noopener">Scholar <i class="ai ai-google-scholar" aria-hidden="true"></i></a>
    </div>

  </div>

  <figure class="home-intro-portrait">
    <img
      src="{{ '/assets/img/profile.jpg' | relative_url }}"
      alt="Xiwen Chen"
      class="rounded"
      width="1279"
      height="1920"
      loading="eager"
      decoding="async"
    >
  </figure>
</div>

One question connects much of my work:

<strong style="font-weight: 700;">Which data is most useful, and when is expensive computation actually worth it?</strong>

At USC, advised by [Prof. Ruishan Liu](https://viterbi-web.usc.edu/~ruishanl/), I led two research directions. [RadOncGym]({{ '/projects/radonc-gym/' | relative_url }}) explores when agents should use costly evaluations, reducing full evaluations by **81%** while retaining **95%** of optimization gains. [TAVO]({{ '/projects/tavo/' | relative_url }}) and [TAC]({{ '/projects/tac/' | relative_url }}) focus on data selection and generalization under distribution shift, with TAVO outperforming the strongest fixed-selection baseline using just **12% of source data**. My work on RadOncGym and TAVO resulted in **two first-author papers accepted at WACV 2027**.

At [**American Best Life Inc.**]({{ '/projects/eguoo-wellness/' | relative_url }}), I owned the end-to-end development and AWS deployment of an AI wellness platform with a stateful LangGraph agent. A **1,000-participant A/B test** increased completion from **43% to 78%** and reduced average completion time by **45%**. Across **320 pilot recommendations**, the agent achieved **95% constraint validity** while reducing **end-to-end P95 latency by 27% (66 s to 48 s)** and **inference cost per successful task by 35%** compared with a stateless LLM.

Previously, I applied data-curation ideas to speech ML pipelines at [**2 Cube Global**]({{ '/projects/2-cube-speech-ai/' | relative_url }}) and worked on distributed-storage performance and reliability across a **60-node Linux environment** at [**Xiaomi**]({{ '/projects/xiaomi-storage/' | relative_url }}).

<section class="home-projects" aria-labelledby="selected-projects">
  <div class="home-section-head">
    <h2 id="selected-projects">Selected Projects</h2>
    <a href="{{ '/projects/' | relative_url }}">All projects →</a>
  </div>
  <div class="project-grid">
    <article class="project-card">
      <span class="card-badge">WACV 2027</span>
      <h3><a href="{{ '/projects/radonc-gym/' | relative_url }}">RadOncGym</a></h3>
      <p class="project-card-tag">Agentic optimization</p>
      <p class="project-card-metric"><strong>81%</strong> fewer full evaluations, retaining 95% of optimization gains</p>
      <p class="project-card-links">
        <a href="{{ '/assets/pdf/RadOncGym_WACV_2027_Camera_Ready.pdf' | relative_url }}" target="_blank" rel="noopener">Paper</a>
        <a href="https://github.com/miaot-usc/RadOncGym" target="_blank" rel="noopener">Code</a>
      </p>
    </article>
    <article class="project-card">
      <span class="card-badge">WACV 2027</span>
      <h3><a href="{{ '/projects/tavo/' | relative_url }}">TAVO</a></h3>
      <p class="project-card-tag">Source-data curation</p>
      <p class="project-card-metric"><strong>12%</strong> of source data, outperforming the strongest fixed-selection baseline</p>
      <p class="project-card-links">
        <a href="{{ '/assets/pdf/TAVO_WACV_2027_Camera_Ready.pdf' | relative_url }}" target="_blank" rel="noopener">Paper</a>
        <a href="https://github.com/francischen0724/TAVO" target="_blank" rel="noopener">Code</a>
      </p>
    </article>
    <article class="project-card">
      <span class="card-badge card-badge-muted">Under review · CVPR 2027</span>
      <h3><a href="{{ '/projects/tac/' | relative_url }}">TAC</a></h3>
      <p class="project-card-tag">Label and source selection</p>
      <p class="project-card-metric"><strong>+1.8</strong> Dice points on BraTS 2021 over the strongest matched-budget baseline</p>
      <p class="project-card-links">
        <a href="{{ '/assets/pdf/TAC_Preprint.pdf' | relative_url }}">Preprint</a>
      </p>
    </article>
  </div>
</section>

## Research Interests

<ul class="home-interests">
  <li>Agentic AI &amp; evaluation</li>
  <li>Data-centric ML</li>
  <li>Multimodal learning &amp; distillation</li>
  <li>Budget-aware optimization</li>
  <li>Active learning</li>
  <li>Learning under distribution shift</li>
</ul>
