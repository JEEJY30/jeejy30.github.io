---
layout: default
title: "Analytics Dashboard"
description: "Real-time analytics and insights about my work and progress"
---

<div class="page-title">Analytics Dashboard</div>
<p class="page-subtitle">Real-time insights into my development journey and content creation</p>

<div class="live-indicator">
  <span class="live-dot"></span>
  <span>Live data • Last updated: <span id="last-updated">Just now</span></span>
</div>

## 📊 Overview Metrics

<div class="dashboard-grid">
  <div class="analytics-card">
    <div class="analytics-header">
      <span class="analytics-title">
        <span class="analytics-icon">📝</span>
        Total Writeups
      </span>
    </div>
    <div class="analytics-value" id="total-writeups">{{ site.posts | size }}</div>
    <div class="analytics-change positive" id="writeups-change">
      ↗ +3 this month
    </div>
  </div>
  
  <div class="analytics-card">
    <div class="analytics-header">
      <span class="analytics-title">
        <span class="analytics-icon">🎯</span>
        Categories Covered
      </span>
    </div>
    <div class="analytics-value" id="categories-count">
      {% assign categories = site.posts | map: 'category' | uniq | size %}
      {{ categories }}
    </div>
    <div class="analytics-change positive">
      ↗ +1 new category
    </div>
  </div>
  
  <div class="analytics-card">
    <div class="analytics-header">
      <span class="analytics-title">
        <span class="analytics-icon">📚</span>
        Total Words Written
      </span>
    </div>
    <div class="analytics-value" id="total-words">
      {% assign total_words = 0 %}
      {% for post in site.posts %}
        {% assign words = post.content | number_of_words %}
        {% assign total_words = total_words | plus: words %}
      {% endfor %}
      {{ total_words | divided_by: 1000 }}K
    </div>
    <div class="analytics-change positive">
      ↗ +2.5K this month
    </div>
  </div>
  
  <div class="analytics-card">
    <div class="analytics-header">
      <span class="analytics-title">
        <span class="analytics-icon">⏱️</span>
        Avg Reading Time
      </span>
    </div>
    <div class="analytics-value" id="avg-reading-time">
      {% assign avg_words = total_words | divided_by: site.posts.size %}
      {{ avg_words | divided_by: 200 }}
    </div>
    <div style="font-size: 0.9rem; color: var(--text-muted);">minutes per writeup</div>
  </div>
</div>

## 📈 Content Performance

<div class="dashboard-grid">
  <div class="analytics-card">
    <div class="analytics-header">
      <span class="analytics-title">
        <span class="analytics-icon">📊</span>
        Monthly Writeups
      </span>
    </div>
    <div class="chart-container">
      <canvas id="monthlyChart"></canvas>
    </div>
  </div>
  
  <div class="analytics-card">
    <div class="analytics-header">
      <span class="analytics-title">
        <span class="analytics-icon">🏷️</span>
        Category Distribution
      </span>
    </div>
    <div class="chart-container">
      <canvas id="categoryChart"></canvas>
    </div>
  </div>
</div>

## 🎯 Skills Progress

<div class="analytics-card">
  <div class="analytics-header">
    <span class="analytics-title">
      <span class="analytics-icon">🛠️</span>
      Technical Skills Development
    </span>
  </div>
  
  <div class="skill-progress">
    <div class="skill-name">
      <span>🔒 Cybersecurity</span>
      <span>90%</span>
    </div>
    <div class="progress-bar">
      <div class="progress-fill" style="width: 90%"></div>
    </div>
  </div>
  
  <div class="skill-progress">
    <div class="skill-name">
      <span>💻 Full-Stack Development</span>
      <span>85%</span>
    </div>
    <div class="progress-bar">
      <div class="progress-fill" style="width: 85%"></div>
    </div>
  </div>
  
  <div class="skill-progress">
    <div class="skill-name">
      <span>🐍 Python Development</span>
      <span>95%</span>
    </div>
    <div class="progress-bar">
      <div class="progress-fill" style="width: 95%"></div>
    </div>
  </div>
  
  <div class="skill-progress">
    <div class="skill-name">
      <span>☁️ Cloud Platforms</span>
      <span>75%</span>
    </div>
    <div class="progress-bar">
      <div class="progress-fill" style="width: 75%"></div>
    </div>
  </div>
  
  <div class="skill-progress">
    <div class="skill-name">
      <span>📝 Technical Writing</span>
      <span>88%</span>
    </div>
    <div class="progress-bar">
      <div class="progress-fill" style="width: 88%"></div>
    </div>
  </div>
</div>

## 📅 Activity Timeline

<div class="analytics-card">
  <div class="analytics-header">
    <span class="analytics-title">
      <span class="analytics-icon">🕒</span>
      Recent Activity
    </span>
  </div>
  
  <div class="activity-timeline">
    {% for post in site.posts limit:8 %}
    <div class="activity-item">
      <div class="activity-date">{{ post.date | date: "%B %d, %Y" }}</div>
      <div class="activity-title">Published: {{ post.title }}</div>
      <div class="activity-description">
        {% if post.category %}{{ post.category | capitalize }}{% else %}General{% endif %} • 
        {{ post.content | number_of_words }} words
      </div>
    </div>
    {% endfor %}
  </div>
</div>

## 🔥 Content Heatmap

<div class="analytics-card">
  <div class="analytics-header">
    <span class="analytics-title">
      <span class="analytics-icon">📅</span>
      Publishing Activity (Last 12 Months)
    </span>
  </div>
  
  <div class="heatmap-container">
    <div class="heatmap-grid" id="activity-heatmap">
      <!-- Generated by JavaScript -->
    </div>
    <div style="display: flex; align-items: center; gap: 1rem; margin-top: 1rem; font-size: 0.8rem; color: var(--text-muted);">
      <span>Less</span>
      <div style="display: flex; gap: 2px;">
        <div class="heatmap-cell level-0"></div>
        <div class="heatmap-cell level-1"></div>
        <div class="heatmap-cell level-2"></div>
        <div class="heatmap-cell level-3"></div>
        <div class="heatmap-cell level-4"></div>
      </div>
      <span>More</span>
    </div>
  </div>
</div>

## 🎖️ Achievements & Milestones

<div class="dashboard-grid">
  <div class="analytics-card">
    <div class="analytics-header">
      <span class="analytics-title">
        <span class="analytics-icon">🏆</span>
        Recent Achievements
      </span>
    </div>
    <div style="display: flex; flex-direction: column; gap: 1rem;">
      <div style="padding: 1rem; background: var(--bg-secondary); border-radius: 8px;">
        <div style="font-weight: 600; color: var(--text-primary);">🎯 50 Writeups Published</div>
        <div style="font-size: 0.9rem; color: var(--text-muted);">Reached major milestone</div>
      </div>
      <div style="padding: 1rem; background: var(--bg-secondary); border-radius: 8px;">
        <div style="font-weight: 600; color: var(--text-primary);">🔥 Consistent Publishing</div>
        <div style="font-size: 0.9rem; color: var(--text-muted);">Posted for 30 days straight</div>
      </div>
      <div style="padding: 1rem; background: var(--bg-secondary); border-radius: 8px;">
        <div style="font-weight: 600; color: var(--text-primary);">⭐ Quality Content</div>
        <div style="font-size: 0.9rem; color: var(--text-muted);">Average 1000+ words per post</div>
      </div>
    </div>
  </div>
  
  <div class="analytics-card">
    <div class="analytics-header">
      <span class="analytics-title">
        <span class="analytics-icon">🎯</span>
        Goals Progress
      </span>
    </div>
    <div style="display: flex; flex-direction: column; gap: 1.5rem;">
      <div>
        <div style="display: flex; justify-content: between; margin-bottom: 0.5rem;">
          <span style="font-weight: 500;">100 Writeups Goal</span>
          <span style="color: var(--text-muted);">{{ site.posts | size }}/100</span>
        </div>
        <div class="progress-bar">
          <div class="progress-fill" style="width: {{ site.posts | size }}%"></div>
        </div>
      </div>
      
      <div>
        <div style="display: flex; justify-content: between; margin-bottom: 0.5rem;">
          <span style="font-weight: 500;">Technical Certifications</span>
          <span style="color: var(--text-muted);">3/5</span>
        </div>
        <div class="progress-bar">
          <div class="progress-fill" style="width: 60%"></div>
        </div>
      </div>
      
      <div>
        <div style="display: flex; justify-content: between; margin-bottom: 0.5rem;">
          <span style="font-weight: 500;">Open Source Projects</span>
          <span style="color: var(--text-muted);">7/10</span>
        </div>
        <div class="progress-bar">
          <div class="progress-fill" style="width: 70%"></div>
        </div>
      </div>
    </div>
  </div>
</div>

<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script>
// Dynamic Analytics JavaScript
document.addEventListener('DOMContentLoaded', function() {
    
    // Update timestamp
    function updateTimestamp() {
        const now = new Date();
        document.getElementById('last-updated').textContent = now.toLocaleTimeString();
    }
    
    // Update every minute
    setInterval(updateTimestamp, 60000);
    
    // Generate activity heatmap
    function generateHeatmap() {
        const heatmapContainer = document.getElementById('activity-heatmap');
        const months = 12;
        const weeksPerMonth = 4;
        
        // Get Jekyll post dates (this would be dynamic in real implementation)
        const postDates = [
            {% for post in site.posts %}
            '{{ post.date | date: "%Y-%m-%d" }}',
            {% endfor %}
        ];
        
        // Create heatmap cells
        for (let month = 0; month < months; month++) {
            for (let week = 0; week < weeksPerMonth; week++) {
                const cell = document.createElement('div');
                cell.className = 'heatmap-cell';
                
                // Random activity level for demo (replace with real data)
                const activityLevel = Math.floor(Math.random() * 5);
                cell.classList.add(`level-${activityLevel}`);
                
                // Add tooltip
                const date = new Date();
                date.setMonth(date.getMonth() - month);
                date.setDate(date.getDate() - (week * 7));
                
                cell.title = `${date.toDateString()}: ${activityLevel} posts`;
                
                heatmapContainer.appendChild(cell);
            }
        }
    }
    
    // Create monthly writeups chart
    function createMonthlyChart() {
        const ctx = document.getElementById('monthlyChart').getContext('2d');
        
        // Process Jekyll posts by month
        const monthlyData = {};
        const posts = [
            {% for post in site.posts %}
            { date: '{{ post.date | date: "%Y-%m" }}', title: '{{ post.title }}' },
            {% endfor %}
        ];
        
        // Count posts per month
        posts.forEach(post => {
            monthlyData[post.date] = (monthlyData[post.date] || 0) + 1;
        });
        
        const labels = Object.keys(monthlyData).slice(-6); // Last 6 months
        const data = labels.map(month => monthlyData[month] || 0);
        
        new Chart(ctx, {
            type: 'line',
            data: {
                labels: labels.map(label => {
                    const [year, month] = label.split('-');
                    return new Date(year, month - 1).toLocaleDateString('en-US', { month: 'short', year: 'numeric' });
                }),
                datasets: [{
                    label: 'Writeups Published',
                    data: data,
                    borderColor: 'rgb(99, 102, 241)',
                    backgroundColor: 'rgba(99, 102, 241, 0.1)',
                    tension: 0.4,
                    fill: true
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    legend: {
                        display: false
                    }
                },
                scales: {
                    y: {
                        beginAtZero: true,
                        ticks: {
                            stepSize: 1
                        }
                    }
                }
            }
        });
    }
    
    // Create category distribution chart
    function createCategoryChart() {
        const ctx = document.getElementById('categoryChart').getContext('2d');
        
        // Process categories from Jekyll posts
        const categories = {};
        const posts = [
            {% for post in site.posts %}
            '{{ post.category | default: "general" }}',
            {% endfor %}
        ];
        
        posts.forEach(category => {
            categories[category] = (categories[category] || 0) + 1;
        });
        
        const labels = Object.keys(categories);
        const data = Object.values(categories);
        const colors = [
            'rgba(99, 102, 241, 0.8)',
            'rgba(139, 92, 246, 0.8)',
            'rgba(6, 182, 212, 0.8)',
            'rgba(16, 185, 129, 0.8)',
            'rgba(245, 158, 11, 0.8)'
        ];
        
        new Chart(ctx, {
            type: 'doughnut',
            data: {
                labels: labels.map(label => label.charAt(0).toUpperCase() + label.slice(1)),
                datasets: [{
                    data: data,
                    backgroundColor: colors,
                    borderWidth: 2,
                    borderColor: 'rgba(255, 255, 255, 0.8)'
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                plugins: {
                    legend: {
                        position: 'bottom'
                    }
                }
            }
        });
    }
    
    // Animate counters
    function animateCounters() {
        const counters = document.querySelectorAll('.analytics-value');
        counters.forEach(counter => {
            const target = parseInt(counter.textContent);
            const increment = target / 100;
            let current = 0;
            
            const timer = setInterval(() => {
                current += increment;
                if (current >= target) {
                    counter.textContent = target;
                    clearInterval(timer);
                } else {
                    counter.textContent = Math.floor(current);
                }
            }, 20);
        });
    }
    
    // Initialize everything
    setTimeout(() => {
        generateHeatmap();
        createMonthlyChart();
        createCategoryChart();
        animateCounters();
    }, 500);
});
</script>