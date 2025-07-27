---
layout: default
title: "Home"
description: "Welcome to my personal portfolio showcasing professional experiences, writeups, and projects"
---

<div class="page-title">Welcome to My Digital Space</div>
<p class="page-subtitle">Software Developer, Security Researcher, and Technical Writer sharing knowledge through detailed writeups and professional insights.</p>

## 📊 Quick Stats

<div class="stats-grid">
    <div class="stat-card">
        <div class="stat-number">10+</div>
        <div class="stat-label">Writeups Published</div>
    </div>
    <div class="stat-card">
        <div class="stat-number">2+</div>
        <div class="stat-label">Years Experience</div>
    </div>
    <div class="stat-card">
        <div class="stat-number">25+</div>
        <div class="stat-label">Projects Completed</div>
    </div>
</div>

## 🌟 What I Do

<div class="experience-grid">
    <div class="experience-card">
        <div class="experience-header">
            <div>
                <h3 class="experience-title">🔒 IAM Ninja, Data Security Analyst And Enthusiast DevOps Engineer</h3>
                <p class="experience-company"></p>
            </div>
        </div>
        <p class="experience-description">
            
        </p>
        <div class="experience-skills">
            <span class="skill-tag">OWASP Top 10</span>
            <span class="skill-tag"></span>
            <span class="skill-tag">Metasploit</span>
            <span class="skill-tag">Python</span>
        </div>
    </div>
    
    <div class="experience-card">
        <div class="experience-header">
            <div>
                <h3 class="experience-title">💻 Full-Stack Development</h3>
                <p class="experience-company">Modern Web Applications</p>
            </div>
        </div>
        <p class="experience-description">
            Building scalable web applications with modern frameworks and best practices. 
            From concept to deployment, I create solutions that are both secure and user-friendly.
        </p>
        <div class="experience-skills">
            <span class="skill-tag">React</span>
            <span class="skill-tag">Node.js</span>
            <span class="skill-tag">Python</span>
            <span class="skill-tag">PostgreSQL</span>
        </div>
    </div>
    
    <div class="experience-card">
        <div class="experience-header">
            <div>
                <h3 class="experience-title">📝 Technical Writing</h3>
                <p class="experience-company">Knowledge Sharing & Education</p>
            </div>
        </div>
        <p class="experience-description">
            Creating comprehensive writeups, tutorials, and documentation to help others learn. 
            My content ranges from beginner-friendly guides to advanced technical deep-dives.
        </p>
        <div class="experience-skills">
            <span class="skill-tag">Technical Writing</span>
            <span class="skill-tag">Documentation</span>
            <span class="skill-tag">Tutorials</span>
            <span class="skill-tag">Markdown</span>
        </div>
    </div>
</div>

## 📝 Latest Writeups

<div class="writeup-grid">
    {% for post in site.posts limit:6 %}
    <div class="writeup-card">
        <div class="writeup-image">
            {% if post.category == 'cybersecurity' %}🔒
            {% elsif post.category == 'web-dev' %}🌐
            {% elsif post.category == 'tools' %}🛠️
            {% else %}📄{% endif %}
        </div>
        <div class="writeup-content">
            <h3 class="writeup-title">{{ post.title }}</h3>
            <div class="writeup-meta">
                {{ post.date | date: "%B %d, %Y" }} • 
                {% if post.category %}{{ post.category | capitalize }}{% else %}General{% endif %} • 
                {{ post.reading_time | default: "5 min" }} read
            </div>
            <p class="writeup-excerpt">{{ post.excerpt | strip_html | truncate: 120 }}</p>
            <a href="{{ post.url | relative_url }}" class="read-more">Read Full Writeup</a>
        </div>
    </div>
    {% endfor %}
</div>

<div style="text-align: center; margin: 3rem 0;">
    <a href="{{ '/writeups/' | relative_url }}" class="read-more" style="font-size: 1.1rem;">View All Writeups →</a>
</div>

## 💼 Professional Experience Highlights

<div class="experience-grid">
    <div class="experience-card">
        <div class="experience-header">
            <div>
                <h3 class="experience-title">Senior Security Analyst</h3>
                <p class="experience-company">TechCorp Solutions</p>
            </div>
            <span class="experience-date">2022 - Present</span>
        </div>
        <p class="experience-description">
            Leading security assessments for enterprise clients, conducting penetration tests, 
            and developing custom security tools. Reduced client vulnerabilities by 40% through 
            comprehensive testing methodologies.
        </p>
        <div class="experience-skills">
            <span class="skill-tag">Penetration Testing</span>
            <span class="skill-tag">Risk Assessment</span>
            <span class="skill-tag">Team Leadership</span>
        </div>
    </div>
    
    <div class="experience-card">
        <div class="experience-header">
            <div>
                <h3 class="experience-title">Full-Stack Developer</h3>
                <p class="experience-company">StartupXYZ</p>
            </div>
            <span class="experience-date">2020 - 2022</span>
        </div>
        <p class="experience-description">
            Built and maintained web applications serving 10,000+ users. Implemented security 
            best practices and optimized performance, resulting in 50% faster load times.
        </p>
        <div class="experience-skills">
            <span class="skill-tag">React</span>
            <span class="skill-tag">Python Django</span>
            <span class="skill-tag">AWS</span>
        </div>
    </div>
</div>

<div style="text-align: center; margin: 3rem 0;">
    <a href="{{ '/experience/' | relative_url }}" class="read-more" style="font-size: 1.1rem;">View Full Experience →</a>
</div>

## 🚀 Featured Projects

<div class="writeup-grid">
    <div class="writeup-card">
        <div class="writeup-image">🛡️</div>
        <div class="writeup-content">
            <h3 class="writeup-title">SecureAuth Tool</h3>
            <div class="writeup-meta">Python • Security • Open Source</div>
            <p class="writeup-excerpt">
                A comprehensive authentication security testing tool that automates common 
                authentication bypass techniques and generates detailed reports.
            </p>
            <a href="https://github.com/yourusername/secureauth" class="read-more">View on GitHub</a>
        </div>
    </div>
    
    <div class="writeup-card">
        <div class="writeup-image">📊</div>
        <div class="writeup-content">
            <h3 class="writeup-title">VulnTracker Dashboard</h3>
            <div class="writeup-meta">React • Node.js • MongoDB</div>
            <p class="writeup-excerpt">
                Real-time vulnerability tracking dashboard for security teams. Features automated 
                scanning integration and customizable reporting.
            </p>
            <a href="https://github.com/yourusername/vulntracker" class="read-more">View Project</a>
        </div>
    </div>
    
    <div class="writeup-card">
        <div class="writeup-image">🔍</div>
        <div class="writeup-content">
            <h3 class="writeup-title">CTF Writeup Collection</h3>
            <div class="writeup-meta">Documentation • Educational</div>
            <p class="writeup-excerpt">
                Comprehensive collection of CTF writeups covering web exploitation, 
                cryptography, reverse engineering, and forensics challenges.
            </p>
            <a href="{{ '/writeups/ctf/' | relative_url }}" class="read-more">Browse Writeups</a>
        </div>
    </div>
</div>

## 🎯 Current Focus

I'm currently working on:

- **IAM Ninja, RBAC And ABAC Mastery** -  Help Organization Enhencing Overall Security Posture
- **Data Security, Crafting Security From Really Matters** -  Help Organization Enhencing Data Security Posture
- **Build Scalable And Reliable Systems** - Designing Modern Architectures
- **CI/CD Pipelines That Never Brakes** - Building Resilient, Collaborative CI/CD Pipelines
- **RDB, NRDB And Event Driven Architecture** - Creating 
- **Open Source Contributions** - Contributing to security tools and frameworks

## 📬 Let's Connect

Whether you're interested in collaboration, have questions about my writeups, or just want to chat about cybersecurity and development, I'd love to hear from you!

<div style="text-align: center; margin: 3rem 0;">
    <a href="{{ '/contact/' | relative_url }}" class="read-more" style="font-size: 1.2rem;">Get In Touch →</a>
</div>