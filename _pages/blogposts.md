---
layout: archive
permalink: /blogposts/
title: "Blogposts by tags"
#author_profile: true
header: 
	image: "/images/screenshot.png"
---

{% include base_path %}
{% include group-by-array collectionsite.posts field="tags" %}

{% include for tag in group_names %}
	{% assign posts = group_items[forloop.index0] %}
	<h2 id="{{ tag | slugify }}" class="archive_subtitle">{{ tag }}</h2>
	{% for post in posts %}
		{% include archive-single.html %}
	{% endfor %}
{% endfor %}