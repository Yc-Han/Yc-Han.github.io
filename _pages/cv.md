---

layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume

---

{% include base_path %}

[Download my full CV (PDF, 1 MB)]({{ site.baseurl }}/files/cv.pdf)

# Research Interests

* Interpretable Deep Learning
* Adversarial Robustness
* Causal Inference
* Genomics

# Education

* **B.Sc. Statistics and Data Science** (150 ECTS), Ludwig Maximilian University of Munich, Oct 2022 – Sep 2025 (expected)

  * Minor in Biology (30 ECTS)
  * Thesis (in progress): *Interpretable Sequence‑based Deep Learning Models for Biomarker Discovery in Genomics*

# Research & Work Experience

* **Research Assistant, Computational Biology for Infection Research – Helmholtz Centre for Infection Research (HZI), Brunswick**
  Oct 2024 – Present

  * Member of the GenomeNet project (PI Prof. Dr. Alice McHardy; Team lead Dr. Philipp Münch)
  * Extend *DeepG* (R package) with model‑agnostic interpretability modules
  * Design adversarial stability tests for sequence‑based classifiers

* **Research Assistant & Statistical Consultant – Statistical Consulting Unit (StaBLab), LMU Munich**
  Apr 2024 – Present

  * Delivered methodological support to 11 graduate projects (6 MSc, 5 PhD) in biology, medicine and psychology
  * Participate in internal research and ongoing consulting projects

# Teaching Experience

* **Teaching Assistant – Department of Statistics, LMU Munich**
  Oct 2023 – Oct 2024

  * *Descriptive Statistics and Exploratory Data Analysis* (WiSe 23/24): led tutorials for \~120 freshmen; authored 10 Particify quiz sessions
  * *Probability Theory and Statistics for Computer Science* (SoSe 24): grading & technical support
  * *Descriptive Statistics & Probability Theory* (SoSe 24): designated tutor for the department‑sponsored exam‑preparation course; authored first half of tutorial materials and exercise sets (45 pages)

# Selected Projects

* **MicrobeLLM & microbe.cards** – Co‑author, HZI (Aug 2024 – Oct 2024)
  Built random‑forest ensemble for LLM‑derived phenotype prediction; co‑author of the manuscript.

* **Wildlife Abundance in German National Parks** – Deputy lead, LMU (Feb 2025 – May 2025)
  Applied N‑mixture models to camera‑trap data from 10 parks; reviewed model robustness; produced abundance maps presented to the Bavarian National Park management team.

# Skills

* **Programming:** R (advanced), Python (intermediate), SAS (intermediate)
* **Tools:** Git, SLURM, Linux, LaTeX, Inkscape
* **Languages:** Chinese (native), German (fluent), English (fluent), Norwegian (beginner)

# Publications

<ul>{% for post in site.publications reversed %}
  {% include archive-single-cv.html %}
{% endfor %}</ul>

# Talks

<ul>{% for post in site.talks reversed %}
  {% include archive-single-talk-cv.html %}
{% endfor %}</ul>

# Teaching

<ul>{% for post in site.teaching reversed %}
  {% include archive-single-cv.html %}
{% endfor %}</ul>

# Service & Leadership

* **Appointment Commissions for two W2 Endowed Professorships (Machine Learning in the Life Sciences; Statistical & ML in Official Statistics)** – Primary student representative (Mar 2025 – Present)
  Review candidates' dossiers, question candidates during hearings, vote in short‑list selection.
* **Statistics Student Council, LMU Munich** – Leader, Teaching Working Group; organiser of "Round Table for Teaching" events; website administrator (Apr 2023 – Present)
