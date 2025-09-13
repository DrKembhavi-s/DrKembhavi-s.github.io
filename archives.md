---
layout: page
title: Archives
permalink: /archives/
---

<div class="archive-container">
  <h1>📚 All Posts by Month</h1>
  <p style="text-align: center; margin-bottom: 2rem; color: #666;">Click on any month to expand/collapse posts</p>
  
  {% assign postsByYearMonth = site.posts | group_by_exp:"post", "post.date | date: '%Y-%m'" %}
  {% for yearMonth in postsByYearMonth %}
    {% assign year = yearMonth.name | slice: 0, 4 %}
    {% assign month = yearMonth.name | slice: 5, 2 %}
    {% case month %}
      {% when '01' %}{% assign monthName = 'January' %}
      {% when '02' %}{% assign monthName = 'February' %}
      {% when '03' %}{% assign monthName = 'March' %}
      {% when '04' %}{% assign monthName = 'April' %}
      {% when '05' %}{% assign monthName = 'May' %}
      {% when '06' %}{% assign monthName = 'June' %}
      {% when '07' %}{% assign monthName = 'July' %}
      {% when '08' %}{% assign monthName = 'August' %}
      {% when '09' %}{% assign monthName = 'September' %}
      {% when '10' %}{% assign monthName = 'October' %}
      {% when '11' %}{% assign monthName = 'November' %}
      {% when '12' %}{% assign monthName = 'December' %}
    {% endcase %}
    
    <div class="archive-month">
      <h2 class="archive-month-header" onclick="toggleMonth('{{ yearMonth.name }}')">
        <span class="archive-toggle">▼</span>
        {{ monthName }} {{ year }} 
        <span class="post-count">({{ yearMonth.items | size }} posts)</span>
      </h2>
      
      <div id="month-{{ yearMonth.name }}" class="archive-month-posts">
        {% for post in yearMonth.items %}
          <div class="archive-post-item">
            <span class="post-date">{{ post.date | date: "%b %d" }}</span>
            <span class="post-category">[{{ post.categories | first | capitalize }}]</span>
            <a href="{{ post.url | relative_url }}" class="post-title">{{ post.title }}</a>
          </div>
        {% endfor %}
      </div>
    </div>
  {% endfor %}
</div>

<style>
/* Archive Styles */
.archive-container {
  max-width: 800px;
  margin: 0 auto;
  padding: 2rem 1rem;
}

.archive-month {
  margin-bottom: 1.5rem;
  border: 1px solid #e1e5e9;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 4px rgba(0,0,0,0.05);
}

.archive-month-header {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  padding: 1rem 1.5rem;
  margin: 0;
  cursor: pointer;
  transition: all 0.3s ease;
  font-size: 1.25rem;
  font-weight: 600;
}

.archive-month-header:hover {
  background: linear-gradient(135deg, #5a6fd8 0%, #6a4190 100%);
  transform: translateY(-1px);
}

.archive-toggle {
  display: inline-block;
  margin-right: 0.5rem;
  font-size: 0.8em;
  transition: transform 0.3s ease;
}

.post-count {
  float: right;
  background: rgba(255,255,255,0.2);
  padding: 0.2rem 0.8rem;
  border-radius: 15px;
  font-size: 0.85em;
}

.archive-month-posts {
  padding: 1rem 1.5rem;
  background-color: white;
}

.archive-post-item {
  display: flex;
  align-items: center;
  padding: 0.75rem 0;
  border-bottom: 1px solid #f1f3f4;
  transition: background-color 0.2s ease;
}

.archive-post-item:hover {
  background-color: #f8f9fa;
  margin: 0 -1rem;
  padding-left: 1rem;
  padding-right: 1rem;
}

.archive-post-item:last-child {
  border-bottom: none;
}

.post-date {
  min-width: 60px;
  color: #6c757d;
  font-size: 0.85em;
  margin-right: 1rem;
  font-weight: 500;
}

.post-category {
  min-width: 110px;
  color: #495057;
  font-size: 0.8em;
  margin-right: 1rem;
  background-color: #e9ecef;
  padding: 0.3rem 0.7rem;
  border-radius: 15px;
  text-align: center;
  font-weight: 600;
}

.post-title {
  flex: 1;
  color: #007bff;
  text-decoration: none;
  font-weight: 500;
  line-height: 1.4;
}

.post-title:hover {
  color: #0056b3;
  text-decoration: underline;
}

/* Responsive */
@media (max-width: 768px) {
  .archive-container {
    padding: 1rem 0.5rem;
  }
  
  .archive-month-header {
    padding: 0.75rem 1rem;
    font-size: 1.1rem;
  }
  
  .archive-month-posts {
    padding: 1rem;
  }
  
  .archive-post-item {
    flex-direction: column;
    align-items: flex-start;
    padding: 1rem 0;
  }
  
  .post-date, .post-category {
    margin-bottom: 0.5rem;
    margin-right: 0;
  }
  
  .post-count {
    float: none;
    margin-left: 0.5rem;
  }
}
</style>

<script>
function toggleMonth(monthId) {
  var element = document.getElementById('month-' + monthId);
  var toggle = element.previousElementSibling.querySelector('.archive-toggle');
  
  if (element.style.display === 'none') {
    element.style.display = 'block';
    toggle.innerHTML = '▼';
  } else {
    element.style.display = 'none';
    toggle.innerHTML = '▶';
  }
}

// Initially hide all months except the most recent
document.addEventListener('DOMContentLoaded', function() {
  var months = document.querySelectorAll('.archive-month-posts');
  months.forEach(function(month, index) {
    if (index > 0) { // Keep first month (most recent) open
      month.style.display = 'none';
      month.previousElementSibling.querySelector('.archive-toggle').innerHTML = '▶';
    }
  });
});
</script>
