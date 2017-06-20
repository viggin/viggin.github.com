---
layout: page2col
title: Archives
permalink: /archives/archives.html
---

<!-- <header class="post-header"> -->
<div class="page-subtitle" >
	<span style="font-size: 1.5em">Archives</span>
	<a href="categories.html">Catagories</a>
	<a href="tags.html">Tags</a>
</div>
<!-- </header> -->

<ul class="tags-box">

	{% if site.posts != empty %}

		{% for post in site.posts %}
		
			{% if post.categories[0] != "update" %}
				{% capture this_year %}{{ post.date | date: "%Y" }}{% endcapture %}
				{% unless year == this_year %}
				{% assign year = this_year %}
				{% unless post == site.posts.first %}
				{% endunless %}
				<li id="{{ year }}">{{ year }}</li>
				{% endunless %}
				<time datetime="{{ post.date | date:"%Y-%m-%d" }}">
					{{ post.date | date:"%Y-%m-%d" }}
				</time>
				&raquo; <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title | capitalize }}</a><br />
			{% endif %}
		{% endfor %}


	{% else %}

		<span>No posts</span>

	{% endif %}

</ul>
