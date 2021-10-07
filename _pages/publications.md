---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

## Journal
---
<ul>
{% assign journals = site.publications | where: "category", "journal" %}
{% for post in journals reversed %}
    {% include archive-single-cv.html %}
{% endfor %}
</ul>

## Preprint
---
<ul>
{% assign journals = site.publications | where: "category", "preprint" %}
{% for post in journals reversed %}
    {% include archive-single-cv.html %}
{% endfor %}
</ul>

## Conference
---
<ul>
{% assign conferences = site.publications | where: "category", "conference" %}
{% for post in conferences reversed %}
    {% include archive-single-cv.html %}
{% endfor %}
</ul>

## Demo
---
<ul>
{% assign conferences = site.publications | where: "category", "demo" %}
{% for post in conferences reversed %}
    {% include archive-single-cv.html %}
{% endfor %}
</ul>

## Patents
---
<ul>
{% assign patents = site.publications | where: "category", "patent" %}
{% for post in patents reversed %}
    {% include archive-single-cv.html %}
{% endfor %}
</ul>


## Thesis
---
<ul>
{% assign thesises = site.publications | where: "category", "thesis" %}
{% for post in thesises reversed %}
    {% include archive-single-cv.html %}
{% endfor %}
</ul>

