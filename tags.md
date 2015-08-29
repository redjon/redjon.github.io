---
layout: page
title: Tags
---

<div>

<!-- See http://stackoverflow.com/questions/1408824/an-easy-way-to-support-tags-in-a-jekyll-blog -->

{% capture tags %}
  {% for tag in site.tags %}
    {{ tag[0] }}
  {% endfor %}
{% endcapture %}
{% assign sortedtags = tags | split:' ' | sort %}

{% for tag in sortedtags %}
  <h4 id="{{ tag }}">{{ tag }}</h4>
  <ul>
  {% for post in site.tags[tag] %}
      <li>
        <span>{{ post.date | date: "%Y-%m-%d" }}</span>
		&raquo;
        <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </li>
  {% endfor %}
  </ul>
{% endfor %}

</div>
