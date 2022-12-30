---
layout: default
title: People
---

## People

<!-- predefined labels, in order -->
{% assign tags = "Principal Investigator, Graduate, Undergraduate, Alumni" | split: ", " %}

<!-- loop over tags -->

{% for tag in tags %}

{% assign members = site.people | where: "position", tag | reverse %}
{% assign mem_size = members | size %}
{% if mem_size > 0 %} <!-- generate group if not empty -->

### {{ tag }}
<!-- generate list of members and link to their bios -->
{% for person in members | sort: "name" %}

* [{{ person.name }}]({{ person.url }})

{% endfor %}
{% endif %}
{% endfor %}