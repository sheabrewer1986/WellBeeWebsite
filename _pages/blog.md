---
layout: page
title: Blog
include_in_header: true
permalink: /blog/
---

# WellBee Blog

Welcome to the WellBee Blog, where you’ll find practical family health tips, helpful guides, everyday advice and the latest updates from WellBee.

Whether you’re looking for ways to manage illness, keep track of your family’s health or make everyday life a little easier when someone is unwell, you’ll find useful information and resources here.

Our aim is to help families feel more organised and better prepared when illness strikes.

<div class="blogList">

{% for post in site.posts %}

    <article class="blogCard {% if post.categories.size > 0 %}category-{{ post.categories.first | slugify }}{% endif %}">

        <div class="blogCardContent">

            <h2>
                <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
            </h2>
            
            <div class="blogCardMeta">
                <span>{{ post.date | date: "%d %B %Y" }}</span>

                {% for category in post.categories %}
                    <span class="blogCategory category-{{ category | slugify }}">
                        {{ category }}
                    </span>
                {% endfor %}
            </div>

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
