---
layout: page
permalink: /archive/
title: 所有
content-type: eg
---

<div>
{% for collection in site.collections %}
{% if collection.label != "pages" %}
  <h2>{{ collection.label_show | capitalize }}</h2>
  <ul>
    {% for item in site[collection.label] %}
      <li class="archive-links"><a href="{{ item.url }}">{{ item.title }}</a></li>
    {% endfor %}
  </ul>
{% endif %}
{% endfor %}
</div>
