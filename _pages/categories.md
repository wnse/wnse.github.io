---
layout: page
title: 分类
permalink: /categories/
content-type: eg
---

<style>
.category-content a {
    text-decoration: none;
    color: #4183c4;
}

.category-content a:hover {
    text-decoration: underline;
    color: #4183c4;
}
</style>

<main>
<h2>文章：</h2>
    {% for category in site.categories %}
        <div class="pure-u-1 tags">
        <h3 id="{{ category | first }}">{{ category | first  }}</h3>
        {% for post in category.last %}
            <li id="category-content" style="padding-bottom: 0.6em;"><a href="{{post.url}}">{{ post.title }}</a></li>
        {% endfor %}
        </div>
    {% endfor %}
    <br/>
    <br/>
<h2>摘录：</h2>
    <br/>
    {% assign tags =  site.notes | map: 'categories' | join: ','  | split: ',' | uniq %}
    {% for tag in tags %}
    <div class="pure-u-1 tags">
      <h3 id="{{ category | first }}">{{ tag | capitalize }}</h3>
      {% for note in site.notes %}
        {% if note.categories contains tag %}
            <li id="category-content" style="padding-bottom: 0.6em;"><a href="{{ note.url }}">{{ note.title }}</a></li>
        {% endif %}
      {% endfor %}
    </div>
    {% endfor %}
</main>
