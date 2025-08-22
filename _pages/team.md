---
title: "Team"
layout: gridlay
sitemap: false
permalink: /team/
---

## Team

<!-- **We are looking for new team members** [(see openings)]({{ site.url }}{{ site.baseurl }}/vacancies) **!** -->

<!-- ## PI -->

{% for member in site.data.pi %}

<div class="jumbotron">
<div class="row">
<div class="col-sm-2">
  <img src="{{ site.url }}{{ site.baseurl }}/images/{{ member.photo }}" width="100%" style="max-width:250px"/>
</div>
<div class="col-sm-9 col-xs-12">
<h4>{{ member.name }}</h4>
<i>{{ member.info }}</i><br>

<div style="display: flex; flex-wrap: wrap; gap: 5px; align-items: center; margin: 10px 0;">
{% if member.website %}
  <a href="{{ member.website }}" target="_blank" title="Website" style="text-decoration: none;">
    <i class="fa fa-home fa-2x"></i>
  </a>
{% endif %}
{% if member.email %}
  <a href="mailto:{{ member.email }}" target="_blank" title="Email" style="text-decoration: none;">
    <i class="fa fa-envelope-square fa-2x"></i>
  </a>
{% endif %}
{% if member.scholar %}
  <a href="{{ member.scholar }}" target="_blank" title="Google Scholar" style="text-decoration: none;">
    <i class="ai ai-google-scholar-square ai-2x"></i>
  </a>
{% endif %}
{% if member.cv %}
  <a href="{{ member.cv }}" target="_blank" title="CV" style="text-decoration: none;">
    <i class="ai ai-cv-square ai-2x"></i>
  </a>
{% endif %}
{% if member.github %}
  <a href="{{ member.github }}" target="_blank" title="GitHub" style="text-decoration: none;">
    <i class="fa fa-github-square fa-2x"></i>
  </a>
{% endif %}
{% if member.researchgate %}
  <a href="{{ member.researchgate }}" target="_blank" title="ResearchGate" style="text-decoration: none;">
    <i class="ai ai-researchgate-square ai-2x"></i>
  </a>
{% endif %}
{% if member.linkedin %}
  <a href="{{ member.linkedin }}" target="_blank" title="LinkedIn" style="text-decoration: none;">
    <i class="fa fa-linkedin-square fa-2x"></i>
  </a>
{% endif %}
</div>

<ul style="overflow: hidden">
<li> {{ member.education[0] }} </li>
<li> {{ member.education[1] }} </li>
</ul>
</div>
</div>
</div>

{% endfor %}

## Current Graduate Students and Postdocs

<div class='jumbotron'>
{% assign number_printed = 0 %}
{% for member in site.data.team_members %}
{% if member.active == true %}

{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}

<div class="row">
{% endif %}

<div class="col-sm-2">
<img src="{{ site.url }}{{ site.baseurl }}/images/{{ member.photo }}" width="100%" style="max-width:250px"/>
</div>
<div class="col-sm-4 col-xs-12">
  <h4>{{ member.name }}</h4>
  <i>{{ member.info }}<br></i>

<div style="display: flex; flex-wrap: wrap; gap: 5px; align-items: center; margin: 10px 0;">
{% if member.website %}<a href="{{ member.website }}" target="_blank"><i class="fa fa-home fa-2x"></i></a> {% endif %}
{% if member.email %}<a href="mailto:{{ member.email }}" target="_blank"><i class="fa fa-envelope-square fa-2x"></i></a> {% endif %}
{% if member.scholar %} <a href="{{ member.scholar }}" target="_blank"><i class="ai ai-google-scholar-square ai-2x"></i></a> {% endif %}
{% if member.cv %} <a href="{{ member.cv }}" target="_blank"><i class="ai ai-cv-square ai-2x"></i></a> {% endif %}
{% if member.github %} <a href="{{ member.github }}" target="_blank"><i class="fa fa-github-square fa-2x"></i></a> {% endif %}
{% if member.researchgate %} <a href="{{ member.researchgate }}" target="_blank"><i class="ai ai-researchgate-square ai-2x"></i></a> {% endif %}
{% if member.linkedin %} <a href="{{ member.linkedin }}" target="_blank" title="LinkedIn" style="text-decoration: none;"><i class="fa fa-linkedin-square fa-2x"></i></a>{% endif %}
</div>
</div>

{% assign number_printed = number_printed | plus: 1 %}
{% if even_odd == 1 %}

</div>
{% endif %}

{% endif %}
{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}

</div>
{% endif %}
</div>

## Alumni

<div class="jumbotron">
{% assign number_printed = 0 %}
{% for member in site.data.team_members %}
{% if member.active == false %}

{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}

<div class="row">
{% endif %}

<div class="col-sm-2">
<img src="{{ site.url }}{{ site.baseurl }}/images/{{ member.photo }}" width="100%" style="max-width:250px"/>
</div>
<div class="col-sm-4 col-xs-12">
  <h4>{{ member.name }}</h4>
  <i>{{ member.duration }} <br> Role: {{ member.info }}</i>
  <ul style="overflow: hidden">
  </ul>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}

</div>
{% endif %}
{% endif %}
{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}

</div>
{% endif %}
</div>

<!-- ## Undergraduate Students -->

<div class="jumbotron">
<h4 style="cursor: pointer; margin-bottom: 20px; display: flex; justify-content: space-between; align-items: center;" onclick="toggleUndergraduates()">
<span>Undergraduate Student Collaborators</span>
<i class="fa fa-chevron-down" id="undergrad-icon" title="Expand"></i>
</h4>
<div id="undergraduates" style="display: none;">
{% for member in site.data.undergrads %}
<div class="row" style="margin-bottom: 15px; align-items: center;">
<div class="col-sm-10 col-xs-9">
<strong>{{ member.name }}</strong> ({{ member.duration }}) - {{ member.info }}
</div>
<div class="col-sm-2 col-xs-3" style="text-align: right;">
{% if member.linkedin %}
<a href="{{ member.linkedin }}" target="_blank" title="LinkedIn" style="text-decoration: none;">
<i class="fa fa-linkedin-square fa-2x"></i>
</a>
{% endif %}
</div>
</div>
{% endfor %}
</div>
</div>

<script>
function toggleUndergraduates() {
const content = document.getElementById('undergraduates');
const icon = document.getElementById('undergrad-icon');

if (content.style.display === 'none') {
// Show content
content.style.display = 'block';
icon.classList.remove('fa-chevron-down');
icon.classList.add('fa-chevron-up');
icon.title = 'Collapse';
} else {
// Hide content
content.style.display = 'none';
icon.classList.remove('fa-chevron-up');
icon.classList.add('fa-chevron-down');
icon.title = 'Expand';
}
}
</script>


<!-- ## Administrative Support

<a href="exampleemail@gmail.com">Example staff</a> is helping us (and other groups) with administration. -->
