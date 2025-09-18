---
---

<style>
/* About Page Styling */
body {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  line-height: 1.7;
  color: #2d3748;
  background-color: #ffffff;
  margin: 0;
  padding: 0;
}

.about-container {
  max-width: 1000px;
  margin: 0 auto;
  padding: 2rem;
}

.page-header {
  text-align: center;
  background: linear-gradient(135deg, #2c5530 0%, #4a7c59 100%);
  color: white;
  padding: 3rem 2rem;
  margin: -2rem -2rem 3rem -2rem;
  border-radius: 0 0 15px 15px;
}

.page-header h1 {
  font-size: 2.5rem;
  font-weight: 700;
  margin-bottom: 1rem;
  color: white !important;
}

.page-header p {
  font-size: 1.2rem;
  opacity: 0.9;
  margin-bottom: 0;
}

.authors-section {
  display: grid;
  grid-template-columns: 1fr;
  gap: 3rem;
  margin-bottom: 3rem;
}

.author-profile {
  background: white;
  border-radius: 15px;
  box-shadow: 0 4px 20px rgba(0,0,0,0.1);
  padding: 3rem;
  border-left: 6px solid #2c5530;
}

.author-profile:nth-child(2) {
  border-left-color: #c17c47;
}

.author-name {
  font-size: 2rem;
  color: #2c5530;
  margin-bottom: 0.5rem;
  font-weight: 700;
}

.author-title {
  font-size: 1.2rem;
  color: #c17c47;
  font-weight: 600;
  margin-bottom: 2rem;
  font-style: italic;
}

.section-title {
  font-size: 1.3rem;
  color: #2c5530;
  margin: 2rem 0 1rem 0;
  font-weight: 600;
  border-bottom: 2px solid #e2e8f0;
  padding-bottom: 0.5rem;
}

.qualifications-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1rem;
  margin: 1rem 0;
}

.qualification-item {
  background: #f7fafc;
  padding: 1rem;
  border-radius: 8px;
  border-left: 4px solid #4a7c59;
}

.qualification-item strong {
  color: #2c5530;
}

.roles-list, .specialization-list {
  list-style: none;
  padding-left: 0;
}

.roles-list li, .specialization-list li {
  padding: 0.5rem 0;
  padding-left: 2rem;
  position: relative;
  border-bottom: 1px solid #e2e8f0;
}

.roles-list li:last-child, .specialization-list li:last-child {
  border-bottom: none;
}

.roles-list li::before {
  content: "🏥";
  position: absolute;
  left: 0;
  font-size: 1.1rem;
}

.specialization-list li::before {
  content: "🩺";
  position: absolute;
  left: 0;
  font-size: 1.1rem;
}

.contact-section {
  background: linear-gradient(135deg, #f7fafc 0%, #edf2f7 100%);
  padding: 2rem;
  border-radius: 15px;
  margin-top: 3rem;
  text-align: center;
}

.contact-info {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1rem;
  margin-top: 1rem;
}

.contact-item {
  background: white;
  padding: 1rem;
  border-radius: 8px;
  border-left: 4px solid #2c5530;
}

.back-to-home {
  display: inline-block;
  background: #2c5530;
  color: white;
  padding: 1rem 2rem;
  border-radius: 8px;
  text-decoration: none;
  font-weight: 600;
  margin: 2rem auto;
  display: block;
  text-align: center;
  max-width: 200px;
  transition: all 0.3s ease;
}

.back-to-home:hover {
  background: #1a3d1f;
  transform: translateY(-2px);
  box-shadow: 0 4px 15px rgba(0,0,0,0.2);
}

/* Navigation styles */
nav {
  background: #f7fafc;
  padding: 1rem 0;
  text-align: center;
  margin-bottom: 2rem;
  border-bottom: 2px solid #e2e8f0;
}

nav a {
  color: #2c5530;
  text-decoration: none;
  margin: 0 1rem;
  font-weight: 500;
  padding: 0.5rem 1rem;
  border-radius: 5px;
  transition: all 0.3s ease;
}

nav a:hover {
  background: #2c5530;
  color: white;
}

@media (max-width: 768px) {
  .page-header h1 {
    font-size: 2rem;
  }
  
  .author-profile {
    padding: 2rem;
  }
  
  .author-name {
    font-size: 1.5rem;
  }
  
  .qualifications-grid {
    grid-template-columns: 1fr;
  }
}
</style>

<!-- Simple Navigation -->
<nav>
  <a href="/">Home</a>
  <a href="/categories">Categories</a>
  <a href="/publications">Publications</a>
  <a href="/about">About</a>
  <a href="/archives">Archives</a>
</nav>

<div class="about-container">
  <!-- Page Header -->
  <div class="page-header">
    <h1>About the Authors</h1>
    <p>Meet the experienced practitioners behind this blog</p>
  </div>

  <!-- Authors Section -->
  <div class="authors-section">
    
    <!-- Dr. Kembhavi Profile -->
    <div class="author-profile">
      <h2 class="author-name">Dr. Kembhavi</h2>
      <p class="author-title">Principal, Ayurveda College</p>
      
      <div class="section-title">Professional Experience</div>
      <p>With over 25 years of dedicated service in Ayurvedic academia, clinical practice, and research, Dr. Kembhavi brings unparalleled expertise to the field of traditional medicine education and practice.</p>
      
      <div class="section-title">Areas of Expertise</div>
      <ul class="specialization-list">
        <li><strong>Educational Administration:</strong> Leading institutional reforms and academic excellence initiatives</li>
        <li><strong>Curriculum Development:</strong> Designing comprehensive Ayurvedic education programs</li>
        <li><strong>Clinical Protocols:</strong> Establishing evidence-based treatment standards</li>
        <li><strong>Research Methodology:</strong> Advancing scientific validation of Ayurvedic principles</li>
      </ul>
      
      <div class="section-title">Mission & Focus</div>
      <p>Dedicated to transforming Ayurvedic education, improving clinical standards, and advancing evidence-based practice. Committed to bridging traditional wisdom with modern educational methodologies to prepare competent, confident practitioners for the future of healthcare.</p>
    </div>

    <!-- Dr. Anita Profile -->
    <div class="author-profile">
      <h2 class="author-name">Dr. Anita Kadagad Kembhavi</h2>
      <p class="author-title">MD Kayachikitsa, Consulting Physician & Panchakarma Specialist</p>
      
      <div class="section-title">Educational Qualifications</div>
      <div class="qualifications-grid">
        <div class="qualification-item">
          <strong>MD Kayachikitsa (2007)</strong><br>
          Rajiv Gandhi University of Health Sciences, Bengaluru
        </div>
        <div class="qualification-item">
          <strong>BAMS (1992)</strong><br>
          Karnataka University, Dharwad
        </div>
        <div class="qualification-item">
          <strong>MSc Yoga (2019)</strong><br>
          SVYASA University, Bengaluru
        </div>
        <div class="qualification-item">
          <strong>MA Child Psychology (2014)</strong><br>
          Kuvempu University, Shivamogga
        </div>
        <div class="qualification-item">
          <strong>DYS (1996)</strong><br>
          Department of Yoga Studies, Karnataka University
        </div>
        <div class="qualification-item">
          <strong>D.NAT-Yoga (AYU) (1998)</strong><br>
          Gujarat Ayurveda University, Jamnagar
        </div>
        <div class="qualification-item">
          <strong>Diploma in Acupuncture (2001)</strong><br>
          Certified Acupuncture Practitioner
        </div>
      </div>
      
      <div class="section-title">Current Positions</div>
      <ul class="roles-list">
        <li><strong>Director & Consultant Physician</strong> - Astanga Wellness Pvt Ltd, Hubli, Karnataka</li>
        <li><strong>Medical Superintendent & Professor</strong> - HOD, Dept of Kaya Chikitsa, Jain AGM Ayurvedic Medical College</li>
        <li><strong>Board Member</strong> - Europe Ayurveda Academy, France</li>
        <li><strong>Resource Person</strong> - State, National and International Seminars & Conferences</li>
        <li><strong>Secretary</strong> - Smt Nagammatai Mahila Mandal</li>
        <li><strong>Life Member</strong> - Red Cross Society and Hemophilia Society</li>
        <li><strong>Member</strong> - Gandhi Peace Foundation, Dharwad</li>
      </ul>
      
      <div class="section-title">Clinical Specializations</div>
      <ul class="specialization-list">
        <li><strong>Diabetes Management</strong> - Comprehensive Ayurvedic approach to metabolic disorders</li>
        <li><strong>Rheumatoid & Osteoarthritis</strong> - Joint health and mobility restoration</li>
        <li><strong>Osteoporosis</strong> - Bone health and strength enhancement</li>
        <li><strong>Obesity Management</strong> - Holistic weight management programs</li>
        <li><strong>Respiratory Diseases</strong> - Pulmonary health and breathing disorders</li>
        <li><strong>Allergies & Skin Diseases</strong> - Immune system balance and dermatological care</li>
        <li><strong>PCOS</strong> - Women's hormonal health and reproductive wellness</li>
        <li><strong>Mental Health Counseling</strong> - Psychological well-being and mind-body balance</li>
      </ul>
      
      <div class="section-title">Practice Philosophy</div>
      <p><strong>Practicing Authentic Ayurveda, Yoga, Naturopathy and Acupuncture since 1999.</strong></p>
      <p>Dr. Anita combines traditional Ayurvedic wisdom with modern understanding of health and disease. Her integrated approach encompasses the complete spectrum of wellness - from preventive care through therapeutic intervention to long-term health maintenance.</p>
      
      <p>Her practice emphasizes:</p>
      <ul class="specialization-list">
        <li><strong>Panchakarma Specialization</strong> - Authentic detoxification and rejuvenation therapies</li>
        <li><strong>Mind-Body Integration</strong> - Combining Ayurveda with Yoga and psychological counseling</li>
        <li><strong>Holistic Patient Care</strong> - Addressing root causes rather than just symptoms</li>
        <li><strong>Evidence-Based Practice</strong> - Integrating traditional methods with modern health understanding</li>
      </ul>
      
      <div class="section-title">Academic & Research Contributions</div>
      <p>Published 3 papers in International journals and regularly invited as a resource person at various conferences. Her diverse educational background spanning Ayurveda, Yoga, Psychology, and Naturopathy provides a unique multidisciplinary perspective to patient care and academic discourse.</p>
      
      <div class="section-title">Areas of Interest</div>
      <p>Beyond clinical practice, Dr. Anita is passionate about Ayurveda, Yoga, Nature, Waste Management, Eco-friendly Living, Organic Agriculture, and Women & Child Welfare - reflecting her commitment to holistic wellness that extends to environmental and social health.</p>
    </div>
  </div>

  <!-- Contact Information -->
  <div class="contact-section">
    <h3>Professional Contact Information</h3>
    <div class="contact-info">
      <div class="contact-item">
        <strong>Astanga Wellness Pvt Ltd</strong><br>
        Shop 1 F-C, Om Annexe, Above SBI Bank<br>
        Shirur Park Main Road, Near The Oaks Hotel<br>
        Prashant Colony, Vidyanagar, Hubli - 580031<br>
        Karnataka, India
      </div>
      <div class="contact-item">
        <strong>Contact Details</strong><br>
        Mobile: 9886759399<br>
        Email: drkembhavi@gmail.com
      </div>
    </div>
  </div>

  <a href="/" class="back-to-home">← Back to Home</a>
</div>
