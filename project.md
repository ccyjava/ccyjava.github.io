---
layout: home
---

<div class="cate-bar"><span id="cateBar"></span></div>

<ul class="artical-list">
{% for post in site.categories.project %}
    <li>
        <h2>
            <a href="{{ post.url }}">{{ post.title }}</a>
        </h2>
        <div class="title-desc">{{ post.description }}</div>
    </li>
{% endfor %}
</ul>

<script type="text/javascript">
    $(function(){
        $("#blogbar").removeClass("on");
        $("#opinionbar").removeClass("on");
        $("#projectbar").addClass("on");

    });

</script>
