---
layout: page
title: Hazzard Family Blog
---
<ul class="index_posts posts">
  {% for post in site.posts %}
    <li>
      <a class="index_title" href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a>
      <div class="index_date">{{ post.date | date_to_string }}</div>

      <div class="post-content-truncate">
          {% if post.content contains "<!-- more -->" %}
            {{ post.content | split:"<!-- more -->" | first % }}
          {% else %}
            <p>{{ post.content | strip_html | truncatewords:100 }}</p>
          {% endif %}

          <a href="{{ BASE_PATH }}{{ post.url }}">[Read More]</a>

          <hr />
      </div>
    </li>
  {% endfor %}
</ul>
