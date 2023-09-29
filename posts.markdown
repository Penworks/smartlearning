---
layout: default
title: Posts
permalink: /posts/
description: This page contains all the archived posts from the smart learning website
---

<nav id="secondary-nav">
	<ul>
{% for p in site.posts %}
 <li> <a href="{{ p.url | relative_url }}" itemprop="url">
            <span itemprop="name"> {{ p.title }}</span></a></li>
{% endfor %}

</ul>
</nav>



<nav id="primary-nav" itemscope itemtype="http://schema.org/SiteNavigationElement" aria-label="Main navigation">
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
</nav>