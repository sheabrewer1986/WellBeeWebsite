---
layout: page
title: Blog
include_in_header: true
permalink: /blog/
---

# WellBee Blog

Practical family health tips, helpful guides, parenting advice and updates from WellBee.

{% for post in site.posts %}

<div class="blogPost">

    <h2>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </h2>

    <p>{{ post.date | date: "%d %B %Y" }}</p>

    <p>{{ post.description | default: post.excerpt | strip_html | truncate: 200 }}</p>

    <a href="{{ post.url | relative_url }}">Read article</a>

</div>

{% endfor %}
