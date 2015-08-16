---
layout: page
title: Hazzard Family Blog
---
<ul class="posts">
  {% for post in site.posts %}
    <li>
    <span>{{ post.date | date_to_string }}</span> -
    <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a>

    <div class="post-content-truncate">
        {% if post.content contains "<!-- more -->" %}
          {{ post.content | split:"<!-- more -->" | first % }}
        {% else %}
          {{ post.content | strip_html | truncatewords:100 }}
        {% endif %}
      </div>
    </li>
  {% endfor %}
</ul>
