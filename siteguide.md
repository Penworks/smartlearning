---
layout: default
title: SiteGuide
permalink: /siteguide/
description: This page contains all the categorized posts from the smart learning website. This is an archive of work from 2016-2021.
---
This page provides ways to navigate the content of the archive. Use category collections to view content related to catgeoy or use the chronological list of posts to see conent in a timeline of often posts in simialr or related contexts.


## Category posts
<!--using the code from https://blog.webjeda.com/jekyll-categories/-->
<div id="archives">
{% for category in site.categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    <div id="#{{ category_name | slugize }}"></div>
    <p></p>
    <h4 class="category-head">{{ category_name }}</h4>
    <a name="{{ category_name | slugize }}"></a>
       <ul id="secondary-nav"> {% for post in site.categories[category_name] %}
    <li><a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a></li>  
    {% endfor %} </ul>
  </div>
{% endfor %}
</div>


## All posts in chronological order
<nav id="secondary-nav">
	<ul>
{% for p in site.posts %}
 <li><span>{{ p.date | date_to_string }}</span> &nbsp; <a href="{{ p.url | relative_url }}" itemprop="url">
            <span itemprop="name"> {{ p.title }}</span></a></li>
{% endfor %}

</ul>
</nav>