---
layout: page
title: "Blog"
---

# Blog & Updates

Stay up to date with the latest news, tutorials, and insights.

{% assign posts_by_year = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}

{% for year in posts_by_year %}
## {{ year.name }}

{% for post in year.items %}
### [{{ post.title }}]({{ post.url }})
**{{ post.date | date: "%B %d, %Y" }}** {% if post.author %}by {{ post.author }}{% endif %}

{{ post.excerpt | strip_html | truncate: 200 }}

[Continue reading →]({{ post.url }})

---
{% endfor %}
{% endfor %}

## Categories

{% assign categories = site.categories | sort %}
{% for category in categories %}
- **[{{ category[0] | capitalize }}](/blog/categories/{{ category[0] }})** ({{ category[1] | size }} posts)
{% endfor %}

## Subscribe

Stay updated with new posts:
- 📡 [RSS Feed](/feed.xml)
- 🐙 [Watch on GitHub](https://github.com/yourusername/your-repo)