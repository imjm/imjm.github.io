---
title: tags
layout: default
---

<header>
<a title="Go to homepage" class="home" href="/"><i class="fa fa-home"></i></a>
<h1>{{ page.title }}</h1> 
</header>

<div id='tag_cloud'>
{% for tag in site.tags %}
<a href="#{{ tag[0] }}" title="{{ tag[0] }}" rel="{{ tag[1].size }}">{{ tag[0] }}</a>
{% endfor %}
</div>

<ul class="items">
{% for tag in site.tags %}
  <li class="item-seperator" id="{{ tag[0] }}">{{ tag[0] }}</li>
  {% for post in tag[1] %}
    <li class="item">
    <time datetime="{{ post.date | date_to_xmlschema }}">on {{ post.date | date_to_long_string }}</time>
    <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
    </li>
  {% endfor %}
{% endfor %}
</ul>