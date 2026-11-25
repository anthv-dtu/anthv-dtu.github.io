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
  <a href="https://www.scopus.com/authid/detail.uri?authorId=60243869000" target="_blank" rel="noopener" title="Scopus" aria-label="Scopus">
    <i class="ai ai-scopus"></i>
  </a>
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

{% comment %}
Same counting rule as the CREA group site: IFAC-PapersOnLine articles count as conference papers.
{% endcomment %}
{% capture total_count %}{% bibliography_count -f papers %}{% endcapture %}
{% capture journal_count %}{% bibliography_count -f papers --query @article[journal != IFAC-PapersOnLine] %}{% endcapture %}
{% capture conference_count %}{% bibliography_count -f papers --query @inproceedings @conference @article[journal = IFAC-PapersOnLine] %}{% endcapture %}
{% capture preprint_count %}{% bibliography_count -f papers --query @misc @unpublished %}{% endcapture %}
{% capture thesis_count %}{% bibliography_count -f papers --query @phdthesis @mastersthesis @thesis %}{% endcapture %}
{% assign journal_n = journal_count | strip | plus: 0 %}
{% assign conference_n = conference_count | strip | plus: 0 %}
{% assign preprint_n = preprint_count | strip | plus: 0 %}
{% assign thesis_n = thesis_count | strip | plus: 0 %}

<div class="publications">

<p class="publication-counts">
  <strong>{{ total_count | strip }}</strong> total publications · <strong>{{ journal_n }}</strong> journal articles ·
  <strong>{{ conference_n }}</strong> conference papers
  {%- if preprint_n > 0 %} · <strong>{{ preprint_n }}</strong> preprints{% endif %}
  {%- if thesis_n > 0 %} · <strong>{{ thesis_n }}</strong> theses{% endif %}
</p>

{% if journal_n > 0 %}

<h2>Journal Articles</h2>
{% bibliography -f papers -q @article[journal != IFAC-PapersOnLine] %}
{% endif %}

{% if conference_n > 0 %}

<h2>Conference Papers</h2>
{% bibliography -f papers -q @inproceedings @conference @article[journal = IFAC-PapersOnLine] %}
{% endif %}

{% if preprint_n > 0 %}

<h2>Preprints</h2>
{% bibliography -f papers -q @misc @unpublished %}
{% endif %}

{% if thesis_n > 0 %}

<h2>Theses</h2>
{% bibliography -f papers -q @phdthesis @mastersthesis @thesis %}
{% endif %}

</div>
