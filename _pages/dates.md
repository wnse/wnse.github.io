---
layout: page
title: 日期
permalink: /dates/
content-type: eg
---

<style>
.date-content a {
    text-decoration: none;
    color: #4183c4;
}

.date-content a:hover {
    text-decoration: underline;
    color: #4183c4;
}
</style>

<div>
<h2>文章：</h2>
    {% assign postsByDay =
    site.posts | group_by_exp:"post", "post.date | date: '%d-%B-%Y'" %}
    {% for day in postsByDay %}
      <h3 id="{{ day.name }}">{{ day.name }}</h3>
          {% for post in day.items %}
            <li id="date-content" style="padding-bottom: 0.6em; list-style: none;"><a href="{{ post.url }}">{{ post.title }}</a></li>
          {% endfor %}
    {% endfor %}
        <br/>
        <br/>
<h2>摘录：</h2>
    {% assign postsByDay =
    site.notes | group_by_exp:"notes", "notes.date | date: '%d-%B-%Y'" %}
    {% for day in postsByDay %}
      <h3 id="{{ day.name }}">{{ day.name }}</h3>
          {% for post in day.items %}
            <li id="date-content" style="padding-bottom: 0.6em; list-style: none;"><a href="{{ post.url }}">{{ post.title }}</a></li>
          {% endfor %}
    {% endfor %}
        <br/>
        <br/>
</div>
