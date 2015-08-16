---
layout: home
---

<div class="cate-bar"><span id="cateBar"></span></div>

<ul class="artical-list">
{% for post in site.categories.blog %}
    <li>
        <h2>
            <a href="{{ post.url }}">{{ post.title }}&nbsp;&nbsp;&nbsp;&nbsp;{{ post.date|date:"%Y-%m-%d" }}</a>
        </h2>
        <div class="title-desc">{{ post.description }}</div>
    </li>
{% endfor %}
</ul>
