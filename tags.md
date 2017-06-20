---
layout: page
title: Tags
permalink: archives/tags.html
---

<!-- <header class="post-header"> -->
  <div class="page-subtitle" >
   <a href="archives.html">Archives</a>
   <a href="categories.html">Catagories</a>
   <span style="font-size: 1.5em">Tags</span>
 </div>
<!-- </header> -->

<ul class="tags-box">
	{% if site.posts != empty %}
	{% for tag in site.tags %}
	<a href="#{{ tag[0] }}" title="{{ tag[0] }}" rel="{{ tag[1].size }}">{{ tag[0] }}<span class="size"> {{ tag[1].size }}</span></a>
	{% endfor %}
</ul>

<ul class="tags-box">
	{% for tag in site.tags %}
	<li  id="{{ tag[0] }}">{{ tag[0] }}</li>
	{% for post in tag[1] %}
	<time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time> &raquo;
	<a href="{{ site.baseurl }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a><br />
	{% endfor %}
	{% endfor %}
	{% else %}
	<span>No posts</span>
	{% endif %}
</ul>
