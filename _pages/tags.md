---
layout: page
title: 标签
permalink: /tags/
content-type: eg
---

<div>
<h2>文章：</h2>
    {% for tag in site.tags %}
    <div class="pure-u-1 tags">
        <h3 id="{{ tag | first }}">{{ tag | first | capitalize }}</h3>
        <ul>
        {% for post in tag.last %}
            <li><a href="{{post.url}}">{{ post.title }}</a></li>
        {% endfor %}
        </ul>
    </div>
    {% endfor %}
    <br/>
    <br/>
<h2>摘录：</h2>
    <br/>
    {% assign tags =  site.notes | map: 'tags' | join: ','  | split: ',' | uniq %}
    {% for tag in tags %}
    <div class="pure-u-1 tags">
      <h3 id="{{ tag | first }}">{{ tag | capitalize }}</h3>
      <ul>
      {% for note in site.notes %}
        {% if note.tags contains tag %}
        <li><a href="{{ note.url }}">{{ note.title }}</a></li>
        {% endif %}
      {% endfor %}
      </ul>
    </div>
    {% endfor %}
</div>
