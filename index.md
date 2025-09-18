---
layout: default
---

<!-- Hero Section - Brief Welcome -->
<section class="hero-section">
    <div class="hero-content">
        <h1>Welcome to Dr Kembhavi's Ayurveda Blog</h1>
        <p class="hero-subtitle">Insights from 25+ years of experience in Ayurvedic medicine</p>
        <p class="hero-description">I share evidence-based perspectives across four key areas of Ayurveda:</p>
        
        <div class="expertise-tags">
            <span class="expertise-tag admin">🏛️ Administrative</span>
            <span class="expertise-tag academic">📚 Academic</span>
            <span class="expertise-tag clinical">🩺 Clinical</span>
            <span class="expertise-tag research">🔬 Research</span>
        </div>
    </div>
</section>

<!-- Tabbed Information Section -->
<section class="info-tabs-section">
    <div class="tabs-container">
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
            <div class="mission-content">
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
        </div>
        
        <!-- Tab Content: Disclaimer -->
        <div id="disclaimer" class="tab-content">
            <div class="disclaimer-content">
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
    </div>
</section>

<!-- Featured Articles Section -->
<section class="featured-articles">
    <h2>Latest Articles</h2>
    
    <!-- Featured Article (Most Recent) -->
    {% assign featured_post = site.posts.first %}
    <div class="featured-article">
        <div class="featured-content">
            <div class="featured-meta">
                <span class="category-tag {{ featured_post.categories[0] | downcase }}">{{ featured_post.categories[0] }}</span>
                <span class="post-date">{{ featured_post.date | date: "%B %d, %Y" }}</span>
            </div>
            <h3 class="featured-title">
                <a href="{{ featured_post.url | relative_url }}">{{ featured_post.title }}</a>
            </h3>
            <p class="featured-excerpt">
                {% if featured_post.excerpt %}
                    {{ featured_post.excerpt | strip_html | truncate: 200 }}
                {% else %}
                    {{ featured_post.content | strip_html | truncate: 200 }}
                {% endif %}
            </p>
            <a href="{{ featured_post.url | relative_url }}" class="read-more-btn">Read Full Article →</a>
        </div>
    </div>
</section>

<!-- Recent Articles Grid -->
<section class="recent-articles">
    <h2>Recent Articles</h2>
    <div class="articles-grid">
        {% for post in site.posts limit: 6 offset: 1 %}
        <article class="article-card">
            <div class="article-header">
                <span class="category-tag {{ post.categories[0] | downcase }}">{{ post.categories[0] }}</span>
                <span class="article-date">{{ post.date | date: "%b %d" }}</span>
            </div>
            <h3 class="article-title">
                <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
            </h3>
            <p class="article-excerpt">
                {% if post.excerpt %}
                    {{ post.excerpt | strip_html | truncate: 120 }}
                {% else %}
                    {{ post.content | strip_html | truncate: 120 }}
                {% endif %}
            </p>
        </article>
        {% endfor %}
    </div>
    
    <div class="view-all-container">
        <a href="{{ '/archives' | relative_url }}" class="btn btn-secondary">View All Articles</a>
    </div>
</section>

<!-- JavaScript for Tabs -->
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
