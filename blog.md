---
layout: page
title: Blog
subtitle: Explore insights, perspectives, and meticulously crafted thought pieces.
---

---

## Browse by Tag

<div class="tags-container" style="margin-bottom: 2em;">
  {% assign sorted_tags = site.tags | sort %}
  <div style="display: flex; flex-wrap: wrap; gap: 10px; padding-top: 10px;">
    {% for tag in sorted_tags %}
      <a href="/tag/{{ tag[0] | slugify }}/" class="btn btn-outline-primary" style="border-radius: 20px; padding: 5px 15px; font-size: 0.9rem;">
        #{{ tag[0] }} <span style="opacity: 0.6;">({{ tag[1].size }})</span>
      </a>
    {% endfor %}
  </div>
</div>

---

## Latest Posts

<div class="posts-list">
  {% for post in site.posts %}
    <div class="post-preview" style="margin-bottom: 2.5em; border-bottom: 1px solid #eaeaea; padding-bottom: 2em;">
      <h2 style="margin-bottom: 0.3em;">
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h2>
      {% if post.subtitle %}
        <h4 style="color: #666; margin-top: 0;">{{ post.subtitle }}</h4>
      {% endif %}

      <p style="font-size: 0.85rem; color: #999; margin-top: 0.4em;">
        {{ post.date | date: "%B %d, %Y" }} &nbsp;&bull;&nbsp;
        {{ post.author | default: "C V Krishna Murthy" }} &nbsp;&bull;&nbsp;
        {% for tag in post.tags %}
          <a href="/tag/{{ tag | slugify }}/" style="text-decoration: none; font-size: 0.85rem; color: #337ab7;">#{{ tag }}</a>{% unless forloop.last %}, {% endunless %}
        {% endfor %}
      </p>

      <p style="margin-top: 0.8em;">{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
      <a href="{{ post.url | relative_url }}" class="btn btn-sm btn-primary" style="border-radius: 20px; font-size: 0.85rem;">Read More →</a>
    </div>
  {% endfor %}
</div>
