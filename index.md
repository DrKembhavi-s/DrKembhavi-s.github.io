---
layout: default
---

<style>
/* Inline CSS for immediate effect */
.hero-section {
  background: linear-gradient(135deg, #2c5530 0%, #4a7c59 100%);
  color: white;
  padding: 3rem 2rem;
  text-align: center;
  margin: -2rem -2rem 3rem -2rem;
  border-radius: 0 0 15px 15px;
}

.hero-content h1 {
  font-size: 2.5rem;
  font-weight: 700;
  margin-bottom: 1rem;
  color: white !important;
}

.hero-subtitle {
  font-size: 1.2rem;
  margin-bottom: 1rem;
  opacity: 0.9;
}

.hero-description {
  font-size: 1.1rem;
  margin-bottom: 2rem;
  opacity: 0.9;
}

.expertise-tags {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 1rem;
  margin-top: 1.5rem;
}

.expertise-tag {
  background: rgba(255, 255, 255, 0.2);
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 25px;
  font-weight: 500;
  border: 1px solid rgba(255, 255, 255, 0.3);
  backdrop-filter: blur(10px);
}

.info-tabs-section {
  background: #f7fafc;
  padding: 2rem;
  margin-bottom: 3rem;
  border-radius: 15px;
  border: 1px solid #e2e8f0;
}

.tab-buttons {
  display: flex;
  justify-content: center;
  margin-bottom: 2rem;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.tab-btn {
  background: white;
  border: 2px solid #2c5530;
  padding: 1rem 1.5rem;
  font-size: 1rem;
  font-weight: 600;
  color: #2c5530;
  cursor: pointer;
  border-radius: 8px;
  transition: all 0.3s ease;
}

.tab-btn:hover {
  background: #2c5530;
  color: white;
}

.tab-btn.active {
  background: #2c5530;
  color: white;
}

.tab-content {
  display: none;
  background: white;
  padding: 2rem;
  border-radius: 10px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.tab-content.active {
  display: block;
}

.areas-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1.5rem;
}

.area-card {
  padding: 1.5rem;
  border-left: 4px solid #c17c47;
  background: #f7fafc;
  border-radius: 0 8px 8px 0;
}

.area-card h3 {
  font-size: 1.2rem;
  margin-bottom: 1rem;
  color: #2c5530;
}

.mission-list {
  list-style: none;
  padding-left: 0;
}

.mission-list li {
  padding: 0.5rem 0;
  padding-left: 2rem;
  position: relative;
}

.mission-list li::before {
  content: "✓";
  position: absolute;
  left: 0;
  color: #2c5530;
  font-weight: bold;
  font-size: 1.2rem;
}

.disclaimer-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1rem;
}

.disclaimer-item {
  padding: 1rem;
  background: #f7fafc;
  border-radius: 8px;
  border-left: 4px solid #d4af37;
}

.disclaimer-item h4 {
  color: #c17c47;
  margin-bottom: 0.5rem;
}

.articles-section {
  margin-top: 3rem;
}

.articles-section h2 {
  text-align: center;
  font-size: 2rem;
  color: #2c5530;
  margin-bottom: 2rem;
}

.articles-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-bottom: 2rem;
}

.article-card {
  background: white;
  border-radius: 10px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
  padding: 2rem;
  border-left: 4px solid #4a7c59;
  transition: transform 0.3s ease;
}

.article-card:hover {
  transform: translateY(-5px);
}

.article-title {
  font-size: 1.3rem;
  margin-bottom: 1rem;
}

.article-title a {
  color: #2c5530;
  text-decoration: none;
}

.article-meta {
  color: #718096;
  font-size: 0.9rem;
  margin-bottom: 1rem;
}

.category-tag {
  padding: 0.25rem 0.5rem;
  border-radius: 4px;
  font-size: 0.8rem;
  font-weight: 600;
  text-transform: uppercase;
}

.category-tag.administrative { background: #3182ce; color: white; }
.category-tag.academic { background: #38a169; color: white; }
.category-tag.clinical { background: #d69e2e; color: white; }
.category-tag.research { background: #9f7aea; color: white; }
.category-tag.blogging { background: #ed8936; color: white; }

@media (max-width: 768px) {
  .hero-content h1 { font-size: 2rem; }
  .expertise-tags { flex-direction: column; align-items: center; }
  .tab-buttons { flex-direction: column; align-items: center; }
  .tab-btn { width: 100%; max-width: 300px; }
  .areas-grid { grid-template-columns: 1fr; }
  .articles-grid { grid-template-columns: 1fr; }
}
</style>

<!-- Hero Section -->
<div class="hero-section">
    <div class="hero-content">
        <h1>Welcome to Dr Kembhavi's Ayurveda Blog</h1>
        <p class="hero-subtitle">Insights from 25+ years of experience in Ayurvedic medicine</p>
        <p class="hero-description">I share evidence-based perspectives across four key areas of Ayurveda:</p>
        
        <div class="expertise-tags">
            <span class="expertise-tag">🏛️ Administrative</span>
            <span class="expertise-tag">📚 Academic</span>
            <span class="expertise-tag">🩺 Clinical</span>
            <span class="expertise-tag">🔬 Research</span>
        </div>
    </div>
</div>

<!-- Tabbed Information Section -->
<div class="info-tabs-section">
    <div class="tab-buttons">
        <button class="tab-btn active" onclick="openTab(event, 'about-areas')">About My Focus Areas</button>
        <button class="tab-btn" onclick="openTab(event, 'mission')">My Mission</button>
        <button class="tab-btn" onclick="openTab(event, 'disclaimer')">Important Disclaimer</button>
    </div>
    
    <!-- Tab Content: Focus Areas -->
    <div id="about-areas" class="tab-content active">
        <div class="areas-grid">
            <div class="area-card">
                <h3>🏛️ Administrative</h3>
                <p>Healthcare management and policy in Ayurvedic institutions - exploring leadership challenges, institutional governance, and systemic improvements needed in Ayurveda administration.</p>
            </div>
            <div class="area-card">
                <h3>📚 Academic</h3>
                <p>Teaching methodologies, curriculum development, and educational reforms - examining how we can better prepare the next generation of Ayurvedic practitioners.</p>
            </div>
            <div class="area-card">
                <h3>🩺 Clinical</h3>
                <p>Patient care approaches, treatment protocols, and clinical practice insights - sharing observations from years of clinical experience in real-world Ayurvedic practice.</p>
            </div>
            <div class="area-card">
                <h3>🔬 Research</h3>
                <p>Scientific validation, methodology, and evidence-based approaches - bridging ancient wisdom with modern research to advance Ayurveda's credibility.</p>
            </div>
        </div>
    </div>
    
    <!-- Tab Content: Mission -->
    <div id="mission" class="tab-content">
        <h3>My Mission</h3>
        <p>Through this blog, I aim to:</p>
        <ul class="mission-list">
            <li><strong>Inspire Excellence</strong> in Ayurvedic education and practice</li>
            <li><strong>Encourage Innovation</strong> while respecting traditional wisdom</li>
            <li><strong>Foster Collaboration</strong> between traditional and modern approaches</li>
            <li><strong>Promote Evidence-Based Practice</strong> in Ayurvedic medicine</li>
            <li><strong>Support Professional Development</strong> of current and future practitioners</li>
            <li><strong>Contribute to Policy Discussions</strong> that can improve our field</li>
        </ul>
    </div>
    
    <!-- Tab Content: Disclaimer -->
    <div id="disclaimer" class="tab-content">
        <h3>Important Disclaimer & Platform Mission</h3>
        <div class="disclaimer-grid">
            <div class="disclaimer-item">
                <h4>Personal Perspectives</h4>
                <p>All articles, opinions, and insights shared represent my personal views and experiences, developed through decades of analysis, research, clinical practice, and interactions with colleagues, students, and patients.</p>
            </div>
            <div class="disclaimer-item">
                <h4>Constructive Intent</h4>
                <p>This platform is created with sincere intention of fostering meaningful dialogue and contributing to the transformation and advancement of Ayurveda.</p>
            </div>
            <div class="disclaimer-item">
                <h4>Respectful Dialogue</h4>
                <p>While I share honest assessments and critical analyses, these are presented with utmost respect for all stakeholders in the Ayurvedic community.</p>
            </div>
            <div class="disclaimer-item">
                <h4>Open Discussion</h4>
                <p>I believe honest, open dialogue is essential for growth. I welcome respectful discourse and collaborative discussions for excellence in Ayurvedic practice.</p>
            </div>
        </div>
    </div>
</div>

<!-- Articles Section -->
<div class="articles-section">
    <h2>Latest Articles</h2>
    
    <div class="articles-grid">
        {% for post in site.posts limit: 6 %}
        <div class="article-card">
            <div class="article-meta">
                <span class="category-tag {{ post.categories[0] | downcase }}">{{ post.categories[0] }}</span>
                <span style="margin-left: 1rem; color: #718096;">{{ post.date | date: "%B %d, %Y" }}</span>
            </div>
            <h3 class="article-title">
                <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
            </h3>
            <p>
                {% if post.excerpt %}
                    {{ post.excerpt | strip_html | truncate: 150 }}
                {% else %}
                    {{ post.content | strip_html | truncate: 150 }}
                {% endif %}
            </p>
        </div>
        {% endfor %}
    </div>
    
    <div style="text-align: center; margin-top: 2rem;">
        <a href="{{ '/archives' | relative_url }}" style="background: #2c5530; color: white; padding: 1rem 2rem; border-radius: 8px; text-decoration: none; font-weight: 600;">View All Articles</a>
    </div>
</div>

<script>
function openTab(evt, tabName) {
    var i, tabcontent, tablinks;
    
    // Hide all tab content
    tabcontent = document.getElementsByClassName("tab-content");
    for (i = 0; i < tabcontent.length; i++) {
        tabcontent[i].classList.remove("active");
    }
    
    // Remove active class from all tab buttons
    tablinks = document.getElementsByClassName("tab-btn");
    for (i = 0; i < tablinks.length; i++) {
        tablinks[i].classList.remove("active");
    }
    
    // Show selected tab and mark button as active
    document.getElementById(tabName).classList.add("active");
    evt.currentTarget.classList.add("active");
}
</script>
