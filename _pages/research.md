---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

<font size="8">**Publications**</font> 

Working Papers

Work in Progress



{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
