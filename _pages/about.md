---
title: "About"
layout: gridlay
sitemap: 
  priority: 0.5
  changefreq: monthly
permalink: /about/
---

<style>
.social-links {
  margin: 15px 0;
  display: flex;
  flex-wrap: wrap;
  gap: 1px;
  align-items: center;
}

.social-links a {
  text-decoration: none;
  transition: transform 0.2s ease;
  /* Remove color: inherit to let the original theme colors show */
}

.social-links a:hover {
  transform: scale(1.1);
}

.social-links i {
  margin: 0;
  /* Normalize icon sizes between Font Awesome and Academicons */
  font-size: 3em !important;
  width: 1em;
  height: 1em;
  line-height: 1;
  vertical-align: middle;
}

/* Specific adjustments for Academicons if needed */
.social-links .ai {
  font-size: 2.9em !important;
}
</style>

## About Dr. Fintan Healy

{% for member in site.data.pi %}

<div class="jumbotron">
<div class="row">
<div class="col-sm-4">
  <img src="{{ site.url }}{{ site.baseurl }}/images/{{ member.photo }}" width="100%" style="max-width:250px"/>
</div>
<div class="col-sm-8 col-xs-12">
  <h3>{{ member.name }}</h3>
  <h4><i>{{ member.info | newline_to_br }}</i></h4>
  
  <div class="social-links">
{% if member.email %}
<a href="mailto:{{ member.email }}" target="_blank" title="Email">
<i class="fa fa-envelope-square fa-3x"></i>
</a>
{% endif %}

{% if member.cv %}
<a href="{{ site.url }}{{ site.baseurl }}/{{ member.cv }}" target="_blank" title="CV">
<i class="ai ai-cv-square ai-3x"></i>
</a>
{% endif %}

{% if member.scholar %}
<a href="{{ member.scholar }}" target="_blank" title="Google Scholar">
<i class="ai ai-google-scholar-square ai-3x"></i>
</a>
{% endif %}

{% if member.orcid %}
<a href="{{ member.orcid }}" target="_blank" title="ORCID">
<i class="ai ai-orcid-square ai-3x"></i>
</a>
{% endif %}

{% if member.github %}
<a href="{{ member.github }}" target="_blank" title="GitHub">
<i class="fa fa-github-square fa-3x"></i>
</a>
{% endif %}

{% if member.linkedin %}
<a href="{{ member.linkedin }}" target="_blank" title="LinkedIn">
<i class="fa fa-linkedin-square fa-3x"></i>
</a>
{% endif %}

{% if member.researchgate %}
<a href="{{ member.researchgate }}" target="_blank" title="ResearchGate">
<i class="ai ai-researchgate-square ai-3x"></i>
</a>
{% endif %}
  </div>

  <ul style="overflow: hidden">
    {% for education in member.education %}
      <li>{{ education | replace: "-","&#8211;" }}</li>
    {% endfor %}
  </ul>

</div>
</div>
</div>
{% endfor %}

{% if site.data.grants and site.data.grants.size > 0 %}

<div class="jumbotron">
  <h3>Grants</h3>
  <ul>
    {% for grant in site.data.grants %}
      <li>{{ grant.name }}</li>
    {% endfor %}
  </ul>
</div>
{% endif %}

{% if site.data.awards %}

<div class="jumbotron">
  <h3>Awards</h3>
  <ul>
    {% for award in site.data.awards %}
      <li>{{ award.name | replace: "-","&#8211;" }}</li>
    {% endfor %}
  </ul>
</div>
{% endif %}

{% if site.data.people %}

<div class="jumbotron">
  <h3>Students and Mentoring</h3>
  <ul>
    {% for student in site.data.people %}
      <li>{{ student.name }}, {{ student.location }} ({{ student.degree }}, {{ student.year }})</li>
    {% endfor %}
  </ul>
</div>
{% endif %}

{% if site.data.funders and site.data.funders.size > 0 %}

<div class="jumbotron">
  <h4>Sponsors</h4>
  <div style='display:block; text-align:center; margin-left:auto; margin-right:auto;'>
  {% for funder in site.data.funders %}<a href="{{ funder.url }}" target="_blank"><img src='{{ site.url }}{{ site.baseurl }}/images/{{ funder.image }}' style='max-height: 80px; max-width: 200px; margin: 1%'/></a>{% endfor %}
  </div>
</div>
{% endif %}
