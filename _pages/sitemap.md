---
layout: archive
title: "Sitemap"
permalink: /sitemap/
author_profile: true
---

{% include base_path %}

[//]: # ({% assign base_path = 'http://www.bwzhu.com' %})

[//]: # (A list of all the posts and pages found on the site. For you robots out there is an [XML version]&#40;{{ base_path }}/sitemap.xml&#41; available for digesting as well.)

A list of all the posts and pages found on the site. For you robots out there is an <a href="{{ base_path }}/sitemap.xml" target="_blank">XML version</a> available for digesting as well.

<hr>
<h2>Pages</h2>
{% for post in site.pages %}
  {% if post.sitemap %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}

<br><br>
<hr>
<h2>Posts</h2>
<!--
{% for post in site.posts %}
  {% include archive-single.html %}
{% endfor %}
-->

{% capture written_label %}'None'{% endcapture %}

{% for collection in site.collections %}
{% unless collection.output == false or collection.label == "posts" %}
  {% capture label %}{{ collection.label }}{% endcapture %}
  {% if label != written_label %}
  <h2>{{ label }}</h2>
  {% capture written_label %}{{ label }}{% endcapture %}
  {% endif %}
{% endunless %}

{% for post in collection.docs %}
  {% unless collection.output == false or collection.label == "posts" %}
  {% include archive-single.html %}
  {% endunless %}
{% endfor %}
{% endfor %}




<br>
<br>
<hr>

*This site is currently under development.
<br>Not all content is available yet, but updates are on the way!
<br >Please check back soon.*

<hr>