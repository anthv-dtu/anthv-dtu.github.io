---
layout: page
permalink: /publications/
title: Publications
description:
nav: true
nav_order: 3
---

<div class="academic-profiles">
  <a href="https://scholar.google.com/citations?user=UXzXSKwAAAAJ&hl=en" target="_blank" rel="noopener" title="Google Scholar" aria-label="Google Scholar">
    <i class="ai ai-google-scholar"></i>
  </a>
  <a href="https://orcid.org/0009-0007-8597-6705" target="_blank" rel="noopener" title="ORCID" aria-label="ORCID">
    <i class="ai ai-orcid"></i>
  </a>
  <!-- ResearchGate (optional):
  <a href="https://www.researchgate.net/profile/YOUR-PROFILE" target="_blank" rel="noopener" title="ResearchGate" aria-label="ResearchGate"><i class="ai ai-researchgate"></i></a>
  -->
  <a href="https://arxiv.org/search/?searchtype=author&query=Vi%C3%A9%2C+Antoine+Thibault" target="_blank" rel="noopener" title="arXiv" aria-label="arXiv">
    <i class="ai ai-arxiv"></i>
  </a>
  <a href="https://www.linkedin.com/in/antoine-vié-aa8aa01b8" target="_blank" rel="noopener" title="LinkedIn" aria-label="LinkedIn">
    <i class="fa-brands fa-linkedin"></i>
  </a>
  <a class="publications-pdf-button" href="{{ '/assets/pdf/Antoine_Vie_CV.pdf' | relative_url }}" target="_blank" rel="noopener">
    <i class="fa-solid fa-file-pdf"></i>
    CV (PDF)
  </a>
</div>

{% capture total_count %}{% bibliography_count -f papers %}{% endcapture %}
{% capture journal_count %}{% bibliography_count -f papers --query @article %}{% endcapture %}
{% capture conference_count %}{% bibliography_count -f papers --query @inproceedings @conference %}{% endcapture %}
{% capture preprint_count %}{% bibliography_count -f papers --query @misc @unpublished %}{% endcapture %}
{% capture thesis_count %}{% bibliography_count -f papers --query @phdthesis @mastersthesis @thesis %}{% endcapture %}

<div class="publications">

<p class="publication-counts">
  <strong>{{ total_count | strip }}</strong> total publications ·
  <strong>{{ journal_count | strip }}</strong> journal articles ·
  <strong>{{ conference_count | strip }}</strong> conference papers ·
  <strong>{{ preprint_count | strip }}</strong> preprints
</p>

{% assign n = journal_count | strip | plus: 0 %}
{% if n > 0 %}

<h2>Journal Articles</h2>
{% bibliography -f papers -q @article %}
{% endif %}

{% assign n = conference_count | strip | plus: 0 %}
{% if n > 0 %}

<h2>Conference Papers</h2>
{% bibliography -f papers -q @inproceedings @conference %}
{% endif %}

{% assign n = preprint_count | strip | plus: 0 %}
{% if n > 0 %}

<h2>Preprints</h2>
{% bibliography -f papers -q @misc @unpublished %}
{% endif %}

{% assign n = thesis_count | strip | plus: 0 %}
{% if n > 0 %}

<h2>Theses</h2>
{% bibliography -f papers -q @phdthesis @mastersthesis @thesis %}
{% endif %}

</div>
