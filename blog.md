---
layout: blog
title: Blog
subtitle: Explore insights, perspectives, and meticulously crafted thought pieces.
---

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
