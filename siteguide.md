---
layout: default
title: SiteGuide
permalink: /siteguide/
description: This page contains the archive of all the posts from the smart learning website, categorized and tagged. This archive is from 2016-2021. A few posts dat from a slightly later period.
---
This page provides ways to navigate the content of the archive. 
Use category collections or tag collections to view content related to category or tag. 
Use the chronological list of posts to see content in a timeline of posts often similar or related. Key collections are the Literary London and Malta Democracy smart learning journey activities, the technology tagged posts and the Tutorials and Guides category.

***NB: This site contains information about Aurasma/HP Reveal that is archived and no longer current - that app is defunct and not available as of 2021. The site is preserved in authenticity to offer ideas, approaches and the main content that was developed for smart learning journey actities to demonstrate practical ways that these kinds of learning expereinces can be designed and implemented.***

---

## Posts by Category
<!--
using the code from https://blog.webjeda.com/jekyll-categories/
for reversed order using https://templates.supply/sort-jekyll-collection-by-reverse-order-and-limit-results/ 
-->

{% for category in site.categories %}
<p>{{category.name | }}</p>
{% endfor %}



<div id="archives">
{% for category in site.categories reversed %}
  <div class="category-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    <!-- <div id="#{{ category_name | slugize }}"></div> -->
    <h4 class="category-head">{{ category_name | capitalize | replace: '-', ' ' }}</h4>
    <div class="cat-subgroup"> <a name="{{ category_name | slugize }}"></a>
       <ul id="secondary-nav"> {% for post in site.categories[category_name] %}
    <li><a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a></li>  
    {% endfor %} </ul>
    </div>
  </div>
{% endfor %}
</div>

---

## Tag Cloud

{% assign tags = site.tags | sort %}       
<div class="tagger">
  <ul class="tagcloud">{% for tag in tags %}
    <li><a href="{{ site.baseurl }}/tag/{{ tag | first | slugify }}"
          style="font-size: {{ tag | last | size  |  times: 4 | plus: 80 }}%">
              {{ tag[0] | replace:'-', ' ' }} ({{ tag | last | size }})
      </a></li>
{% endfor %}
</ul>
</div> 

<!--using modified code from https://superdevresources.com/tag-cloud-jekyll/-->


---


## Posts by Tag
<!--using the code from https://blog.webjeda.com/jekyll-categories/-->
<div id="archives">
{% for tag in site.tags reversed %}
  <div class="tag-group">
    {% capture tag_name %}{{ tag | first }}{% endcapture %}
   <!--  <div id="#{{ tag_name | slugize }}"></div> -->
    <p></p>
    <h4 class="tag-head">{{ tag_name }}</h4>
   <div class="tag-subgroup"> <a name="{{ tag_name | slugize }}"></a>
       <ul id="secondary-nav"> {% for post in site.tags[tag_name] %}
    <li><a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a></li>  
    {% endfor %} </ul>
  </div></div>
{% endfor %}
</div>


---


## All posts in chronological order
<nav id="secondary-nav">
  <ul>
{% for p in site.posts %}
 <li><span>{{ p.date | date_to_string }}</span> &nbsp; <a href="{{ p.url | relative_url }}" itemprop="url">
            <span itemprop="name"> {{ p.title }}</span></a></li>
{% endfor %}

</ul>
</nav>

---

