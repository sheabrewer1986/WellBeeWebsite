---
layout: page
title: Blog
include_in_header: true
permalink: /blog/
---

# WellBee Blog

Practical family health tips, helpful guides, parenting advice and updates from WellBee.

<div class="blogList">

{% for post in site.posts %}

    <article class="blogCard">

        <div class="blogCardContent">

            <h2>
                <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
            </h2>

            <p class="blogCardMeta">
                {{ post.date | date: "%d %B %Y" }}
                {% if post.categories.size > 0 %}
                    · {{ post.categories | join: ", " }}
                {% endif %}
            </p>

            <p class="blogCardDescription">
                {{ post.description | default: post.excerpt | strip_html | truncate: 200 }}
            </p>

            <a class="blogReadMore" href="{{ post.url | relative_url }}">
                Read article →
            </a>

        </div>

    </article>

{% endfor %}

</div>
