---
layout: default
title: "Welcome"
description: "Your comprehensive guide to mastering our project"
---

# Welcome to Your Documentation Hub 🚀

Transform your development workflow with our comprehensive documentation and tutorials.

<div class="feature-grid">
    <div class="feature-card">
        <span class="feature-icon">⚡</span>
        <h3 class="feature-title">Quick Start</h3>
        <p class="feature-description">Get up and running in minutes with our streamlined installation process and clear setup instructions.</p>
        <a href="{{ '/docs/getting-started' | relative_url }}" class="read-more">Get Started</a>
    </div>
    
    <div class="feature-card">
        <span class="feature-icon">📖</span>
        <h3 class="feature-title">Comprehensive Docs</h3>
        <p class="feature-description">Detailed documentation covering every feature, API endpoint, and configuration option you'll need.</p>
        <a href="{{ '/docs/' | relative_url }}" class="read-more">Browse Docs</a>
    </div>
    
    <div class="feature-card">
        <span class="feature-icon">💡</span>
        <h3 class="feature-title">Examples & Tutorials</h3>
        <p class="feature-description">Real-world examples and step-by-step tutorials to help you master advanced concepts quickly.</p>
        <a href="{{ '/docs/examples' | relative_url }}" class="read-more">View Examples</a>
    </div>
</div>

## 🎯 Popular Pages

- **[Installation Guide]({{ '/docs/installation' | relative_url }})** - Set up everything you need in 5 minutes
- **[API Reference]({{ '/docs/api' | relative_url }})** - Complete API documentation with examples
- **[Configuration]({{ '/docs/configuration' | relative_url }})** - Customize for your specific needs
- **[Troubleshooting]({{ '/docs/troubleshooting' | relative_url }})** - Solutions to common issues

## 📝 Latest Blog Posts

{% for post in site.posts limit:3 %}
<div class="card">
    <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
    <div class="post-meta">{{ post.date | date: "%B %d, %Y" }} • {{ post.author | default: "Team" }}</div>
    <p class="post-excerpt">{{ post.excerpt | strip_html | truncate: 150 }}</p>
    <a href="{{ post.url | relative_url }}" class="read-more">Read More</a>
</div>
{% endfor %}

<a href="{{ '/blog/' | relative_url }}" class="read-more">View All Posts</a>

## 🤝 Get Involved

<div class="card">
    <h3>Join Our Community</h3>
    <p>Help us improve the documentation and share your experience with others.</p>
    <ul>
        <li><strong>Found a bug?</strong> <a href="https://github.com/{{ site.github_username | default: 'yourusername' }}/{{ site.github_repo | default: 'Zero-to-Hero' }}/issues">Report it on GitHub</a></li>
        <li><strong>Want to contribute?</strong> <a href="{{ '/contributing' | relative_url }}">Check our contribution guide</a></li>
        <li><strong>Have questions?</strong> <a href="https://github.com/{{ site.github_username | default: 'yourusername' }}/{{ site.github_repo | default: 'Zero-to-Hero' }}/discussions">Start a discussion</a></li>
    </ul>
</div>