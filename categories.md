---
layout: page2col
title: Categories
permalink: archives/categories.html
---

<!-- <header class="post-header"> -->
<div class="page-subtitle" >
	<a href="archives.html">Archives</a>
	<span style="font-size: 1.5em">Catagories</span>
	<a href="tags.html">Tags</a>
</div>
<!-- </header> -->

<ul class="tags-box">
	{% if site.posts != empty %}
		{% for cat in site.categories %}
			{% if cat[0] != "update" %}
				<a href="#{{ cat[0] }}" title="{{ cat[0] }}" rel="{{ cat[1].size }}">{{ cat[0] | join: "/"}}<span class="size"> {{ cat[1].size }}</span></a>
			{% endif %}
		{% endfor %}
</ul>

<ul class="tags-box">
		{% for cat in site.categories %}
			{% if cat[0] != "update" %}
				<li id="{{ cat[0] }}">{{ cat[0]}}</li>
				{% for post in cat[1] %}
					<time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time> &raquo;
					<a href="{{ site.baseurl }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a><br />
				{% endfor %}
			{% endif %}
		{% endfor %}
			
	{% else %}
		<span>No posts</span>
	{% endif %}
</ul>

