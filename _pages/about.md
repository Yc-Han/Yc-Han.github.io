---
permalink: /
title: "Welcome"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

<style>
  .dual-intro {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 3rem;
    margin-bottom: 3rem;
  }
  
  @media (max-width: 768px) {
    .dual-intro {
      grid-template-columns: 1fr;
    }
  }
  
  .intro-section {
    padding: 2rem;
    border-radius: 12px;
    background: white;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  }
  
  .intro-section h2 {
    color: var(--zen-accent, #6B8E23);
    margin-bottom: 1rem;
    font-size: 1.5rem;
  }
  
  .intro-section a.explore-btn {
    display: inline-block;
    margin-top: 1rem;
    padding: 0.6rem 1.2rem;
    background: var(--zen-accent, #6B8E23);
    color: white;
    border-radius: 20px;
    text-decoration: none;
    transition: all 0.3s ease;
  }
  
  .intro-section a.explore-btn:hover {
    background: var(--zen-highlight, #DAA520);
  }
</style>

<div class="dual-intro">
  <div class="intro-section">
    <h2>Academic Work</h2>
    <p>I am an undergraduate in <strong>Statistics & Data Science</strong> at <strong>LMU Munich</strong> and a research assistant with the <a href="https://www.stablab.stat.uni-muenchen.de/">Statistical Consulting Unit (StaBLab)</a> and the <a href="https://www.helmholtz-hzi.de/">Helmholtz Centre for Infection Research (HZI)</a>.</p>
    
    <p><strong>Research interests:</strong></p>
    <ul style="margin-left: 1rem;">
      <li>Interpretable deep learning</li>
      <li>Machine learning in genomics</li>
      <li>Reproducible statistical practice</li>
    </ul>
    
    <a href="/academic/" class="explore-btn">Explore Academic Work →</a>
  </div>
  
  <div class="intro-section">
    <h2>Culture & Arts</h2>
    <p>Beyond data and algorithms, I explore the rich traditions of cultural arts, particularly Japanese aesthetics and philosophy. This includes interactive experiences and essays on tea ceremony, Zen philosophy, and the beauty of imperfection.</p>
    
    <p><strong>Cultural interests:</strong></p>
    <ul style="margin-left: 1rem;">
      <li>Japanese tea ceremony</li>
      <li>Zen aesthetics and philosophy</li>
      <li>Traditional arts and crafts</li>
    </ul>
    
    <a href="/culture/" class="explore-btn">Explore Cultural Works →</a>
  </div>
</div>

## Current Activities

* **Consulting (StaBLab).** I provide statistical guidance on ≈ 20 student and faculty projects each semester—study design, modelling, and reproducible workflows.
* **Research (HZI).** I contribute to the **[GenomeNet](https://github.com/GenomeNet)** project, developing interpretable deep-learning models for prokaryotic phenotype-genome mapping.
* **Cultural Exploration.** Creating interactive digital experiences that bridge traditional arts with modern technology.

For further details see my **[CV]({{ site.baseurl }}/cv/)**, technical write-ups on the **[blog]({{ site.baseurl }}/year-archive/)**, or explore my **[cultural essays]({{ site.baseurl }}/essays/)**.