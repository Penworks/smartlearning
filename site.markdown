---
layout: default
title: Site
permalink: /site/
description: This page contains all the categorized posts from the smart learning website. This is an archive of work from 2016-2021.
---


## Tutorials and Guides

<nav id="secondary-nav">
	<ul>
{% for p in site.categories.tutorials-and-guides %}
 <li><span>{{ p.date | date_to_string }}</span> &nbsp; <a href="{{ p.url | relative_url }}" itemprop="url"><span itemprop="name"> {{ p.title }}</span></a></li>
{% endfor %}
     </ul>
</nav>

## General
<nav id="secondary-nav">
	<ul>
{% for p in site.categories.general %}
 <li><span>{{ p.date | date_to_string }}</span> &nbsp; <a href="{{ p.url | relative_url }}" itemprop="url"><span itemprop="name"> {{ p.title }}</span></a></li>
{% endfor %}
     </ul>
</nav>


## All posts in chronological order
<nav id="secondary-nav">
	<ul>
{% for p in site.posts %}
 <li><span>{{ p.date | date_to_string }}</span> &nbsp; <a href="{{ p.url | relative_url }}" itemprop="url">
            <span itemprop="name"> {{ p.title }}</span></a></li>
{% endfor %}

</ul>
</nav>


<!-- <div class="blog list">
    <h1>Filed Under <small>#{{ page.tag }}</small></h1>

    {% for post in site.categories[page.tag] %}
        {% include post_preview.html %}
    {% endfor %}
</div>
 -->



<!-- {% for category in site.categories %}
    {{ category | first }}
{% endfor %}
 -->


<!-- <div class="post-categories">
  {% if post %}
    {% assign categories = post.categories %}
  {% else %}
    {% assign categories = page.categories %}
  {% endif %} Categories:
  {% for category in categories %}
 <a href="{{site.baseurl}}/categories/{{category|slugize}}">{{category}}</a>
  {% unless forloop.last %} | {% endunless %}
  {% endfor %}
</div> -->








<!-- {% for tag in site.tags %}
  <h3>{{ tag[0] }}</h3>
  <ul>
    {% for post in tag[1] %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
 -->



<!-- <nav id="primary-nav" itemscope itemtype="http://schema.org/SiteNavigationElement" aria-label="Main navigation">
  <ul id="menu-main-navigation" class="menu">
{% for path in page_paths %}
      {% assign my_page = site.pages | where: "path", path | first %}
      {% if my_page.title %}
        <li class="menu-item">
          <a href="{{ my_page.url | relative_url }}" itemprop="url">
            <span itemprop="name">{{ my_page.title | escape }}</span>
          </a>
        </li>
      {% endif %}
    {% endfor %}
     </ul>
</nav> -->


