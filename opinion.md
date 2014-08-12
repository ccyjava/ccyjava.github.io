---
layout: home
---

<div class="cate-bar"><span id="cateBar"></span></div>

<ul class="artical-list">
{% for post in site.categories.opinion %}
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
        $("#opinionbar").addClass("on");
        $("#projectbar").removeClass("on");

    });

</script>
