---
title: "Publications"
layout: gridlay
sitemap: false
permalink: /publications/
---

<style>
.jumbotron{
    padding:3%;
    padding-bottom:10px;
    padding-top:10px;
    margin-top:10px;
    margin-bottom:30px;
}

/* Hide list numbering for bibliography */
.bibliography {
    list-style: none;
    padding-left: 0;
}

.bibliography li {
    margin-bottom: 1em;
}

/* Add space after reference number */
.bibliography li .reference-number::after {
    content: " ";
}

/* Ensure space after brackets in citations */
.text-justify {
    word-spacing: 0.1em;
}
</style>

{% capture thesis_count %}{% bibliography_count --query @phdthesis %}{% endcapture %}
{% if thesis_count != "0" %}
<div class="jumbotron">
### Thesis
{% bibliography --query @phdthesis --list_class bibliography %}
</div>
{% endif %}

{% capture preprint_count %}{% bibliography_count --query @unpublished %}{% endcapture %}
{% if preprint_count != "0" %}
<div class="jumbotron">
### Preprints
{% bibliography --query @unpublished --list_class bibliography %}
</div>
{% endif %}

{% capture journal_count %}{% bibliography_count --query @article %}{% endcapture %}
{% if journal_count != "0" %}
<div class="jumbotron">
### Journal articles
{% bibliography --query @article --list_class bibliography %}
</div>
{% endif %}

{% capture conference_count %}{% bibliography_count --query @conference %}{% endcapture %}
{% if conference_count != "0" %}
<div class="jumbotron">
### Conference papers
{% bibliography --query @conference --list_class bibliography %}
</div>
{% endif %}
