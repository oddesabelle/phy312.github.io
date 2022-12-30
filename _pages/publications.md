---
title: "CX Team- Publications"
layout: gridlay
excerpt: "CX Team: Publications."
sitemap: false
permalink: /publications/
---


<!-- # Publications -->

## Journal Publications

<!-- (For a full list see [below](#full-list) or go to [Google Scholar](https://scholar.google.com.ph/citations?user=UvxZT-IAAAAJ&hl=en#).) -->

{% assign number_printed = 0 %}
{% for publi in site.data.journal_publist %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if publi.highlight == 1 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">
 <div class="card bg-secondary w-100 h-100">
 <div class="card-body">
  <pubtit>{{ publi.title }}</pubtit>
  {% if publi.image %}
  <img src="{{ site.url }}{{ site.baseurl }}/images/pubpic/{{ publi.image }}" class="img-responsive" width="33%" style="float: left" />
  {% endif %}
  <p>{{ publi.description }}</p>
  <p><em>{{ publi.authors }}</em></p>
  <p><strong><a href="{{ publi.link.url }}">{{ publi.link.display }}</a></strong></p>
  <p class="text-danger"><strong> {{ publi.news1 }}</strong></p>
  <p> {{ publi.news2 }}</p>
 </div>
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

<p> &nbsp; </p>


## Conference Proceedings

{% for publi in site.data.publist %}
  {% if publi.highlight == 0 %}
  {{ publi.title }} <br />
  <em>{{ publi.authors }} </em><br />
  {% if publi.link.url %}<a href="{{ publi.link.url }}">{{ publi.link.display }}</a>{% else %}{{ publi.link.display}}{% endif %}
  {% endif %}
{% endfor %}
