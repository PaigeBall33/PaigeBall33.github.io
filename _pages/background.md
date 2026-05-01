---
layout: page
title: Background
permalink: /background/
nav: true
nav_order: 6
---

<style>
/* Hide the theme's auto-rendered page title */
.post-header { display: none; }

.story-wrap { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif; color: #1C1812; padding-bottom: 4rem; }

/* MY STORY hero */
.story-hero {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2rem;
  align-items: start;
  margin-bottom: 3rem;
}
.story-hero-left {}
.story-hero-heading {
  font-size: clamp(3rem, 8vw, 5.5rem);
  font-weight: 900;
  color: #1C1812;
  line-height: 1;
  letter-spacing: -0.02em;
  margin-bottom: 1.5rem;
  text-transform: uppercase;
}
.story-hero-heading span { color: #2D4A3E; }
.story-hero-text {
  font-size: 0.92rem;
  color: #9C8B7A;
  line-height: 1.85;
  max-width: 420px;
}
.story-hero-right {
  display: flex;
  align-items: stretch;
}
.story-photo {
  border-radius: 8px;
  overflow: hidden;
  background: #e2e8f0;
}
.story-photo-tall {
  grid-row: span 2;
}
.story-photo img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}
.story-photo-placeholder {
  width: 100%;
  aspect-ratio: 3/4;
  background: linear-gradient(135deg, #dbeafe, #e0f2fe);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.75rem;
  color: #9C8B7A;
  text-align: center;
  padding: 1rem;
}
.story-photo-placeholder-sq {
  width: 100%;
  aspect-ratio: 1;
  background: linear-gradient(135deg, #f1f5f9, #e2e8f0);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.75rem;
  color: #9C8B7A;
  text-align: center;
  padding: 1rem;
}

/* Photo strip */
.bg-photo-strip {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
  margin-bottom: 2.5rem;
}
.bg-photo-strip img {
  width: 100%;
  height: 260px;
  object-fit: cover;
  object-position: center;
  border-radius: 8px;
  display: block;
}
@media (max-width: 640px) {
  .bg-photo-strip { grid-template-columns: 1fr; }
  .bg-photo-strip img { height: 200px; }
}

/* Ticker */
.ticker-wrap {
  background: #1C1812;
  padding: 1rem 0;
  margin: 2.5rem -1rem;
  overflow: hidden;
  white-space: nowrap;
}
.ticker-track {
  display: inline-block;
  animation: ticker 20s linear infinite;
}
.ticker-track span {
  font-size: 1rem;
  font-weight: 800;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: #F5EFE6;
  padding: 0 1.5rem;
}
.ticker-track span.dot {
  color: #2D4A3E;
  font-size: 0.6rem;
  vertical-align: middle;
  padding: 0 0.5rem;
}
@keyframes ticker {
  0% { transform: translateX(0); }
  100% { transform: translateX(-50%); }
}

/* Facts grid */
.facts-heading {
  font-size: 0.72rem;
  font-weight: 700;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: #9C8B7A;
  margin-bottom: 1.2rem;
}
.facts-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1rem;
  margin-bottom: 3.5rem;
}
.fact-card {
  border-radius: 10px;
  overflow: hidden;
  border: 1px solid rgba(156,139,122,0.25);
  background: white;
}
.fact-card-image {
  height: 160px;
  background: linear-gradient(135deg, #dbeafe, #ede9fe);
  position: relative;
  overflow: hidden;
}
.fact-card-image img {
  position: absolute;
  top: 0; left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}
.fact-card-body {
  padding: 0.9rem;
}
.fact-card-title {
  font-size: 0.8rem;
  font-weight: 700;
  color: #1C1812;
  margin-bottom: 0.3rem;
}
.fact-card-desc {
  font-size: 0.75rem;
  color: #9C8B7A;
  line-height: 1.6;
}

/* Timeline */
.timeline-section { margin-bottom: 3.5rem; }
.timeline { position: relative; padding-left: 1.8rem; }
.timeline::before {
  content: '';
  position: absolute;
  left: 0; top: 8px; bottom: 8px;
  width: 2px;
  background: #e2e8f0;
}
.timeline-item {
  position: relative;
  margin-bottom: 2rem;
  padding-bottom: 2rem;
  border-bottom: 1px solid #f1f5f9;
}
.timeline-item:last-child { border-bottom: none; margin-bottom: 0; padding-bottom: 0; }
.timeline-item::before {
  content: '';
  position: absolute;
  left: -1.8rem; top: 6px;
  width: 10px; height: 10px;
  border-radius: 50%;
  background: #2D4A3E;
  border: 2px solid #fff;
  box-shadow: 0 0 0 2px #2D4A3E;
}
.timeline-date {
  font-size: 0.75rem;
  font-weight: 700;
  color: #2D4A3E;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  margin-bottom: 0.25rem;
}
.timeline-title { font-size: 1rem; font-weight: 700; color: #1C1812; margin-bottom: 0.2rem; }
.timeline-subtitle { font-size: 0.85rem; color: #9C8B7A; margin-bottom: 0.5rem; }
.timeline-desc { font-size: 0.88rem; color: #9C8B7A; line-height: 1.7; }

/* Skills */
.skills-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
  margin-bottom: 3.5rem;
}
.skill-card {
  background: white;
  border: 1px solid rgba(156,139,122,0.25);
  border-radius: 10px;
  padding: 1.2rem;
}
.skill-card-label {
  font-size: 0.7rem;
  font-weight: 700;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: #2D4A3E;
  margin-bottom: 0.6rem;
}
.skill-tags { display: flex; flex-wrap: wrap; gap: 0.35rem; }
.skill-tag {
  background: #f1f5f9;
  color: #9C8B7A;
  border-radius: 20px;
  padding: 0.2rem 0.65rem;
  font-size: 0.75rem;
  font-weight: 600;
}

/* Connect CTA */
.connect-section {
  background: #1C1812;
  border-radius: 16px;
  padding: 3rem;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
  align-items: center;
}
.connect-heading {
  font-size: clamp(2rem, 4vw, 3rem);
  font-weight: 900;
  text-transform: uppercase;
  color: #F5EFE6;
  line-height: 1.1;
  margin-bottom: 0.75rem;
}
.connect-heading span { color: #2D4A3E; }
.connect-subtext {
  font-size: 0.88rem;
  color: #9C8B7A;
  line-height: 1.7;
  margin-bottom: 1.5rem;
}
.connect-buttons { display: flex; gap: 0.75rem; flex-wrap: wrap; }
.connect-btn-primary {
  background: #2D4A3E;
  color: white;
  padding: 0.65rem 1.4rem;
  border-radius: 8px;
  font-size: 0.85rem;
  font-weight: 700;
  text-decoration: none;
  transition: background 0.15s;
}
.connect-btn-primary:hover { background: #2D4A3E; color: white; text-decoration: none; }
.connect-btn-secondary {
  background: transparent;
  color: #F5EFE6;
  padding: 0.65rem 1.4rem;
  border-radius: 8px;
  font-size: 0.85rem;
  font-weight: 700;
  text-decoration: none;
  border: 1.5px solid #9C8B7A;
  transition: border-color 0.15s;
}
.connect-btn-secondary:hover { border-color: #F5EFE6; color: #F5EFE6; text-decoration: none; }
.connect-details { display: flex; flex-direction: column; gap: 1rem; }
.connect-detail-item {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  padding: 0.9rem 1rem;
  background: rgba(245,239,230,0.06);
  border-radius: 8px;
  border: 1px solid rgba(245,239,230,0.08);
}
.connect-detail-icon { font-size: 1.1rem; }
.connect-detail-label { font-size: 0.72rem; color: #9C8B7A; text-transform: uppercase; letter-spacing: 0.08em; margin-bottom: 0.1rem; }
.connect-detail-value { font-size: 0.88rem; color: #F5EFE6; font-weight: 600; }

@media (max-width: 768px) {
  .story-hero { grid-template-columns: 1fr; }
  .story-hero-right { grid-template-columns: 1fr 1fr; }
  .facts-grid { grid-template-columns: 1fr 1fr; }
  .skills-grid { grid-template-columns: 1fr; }
  .connect-section { grid-template-columns: 1fr; padding: 2rem; }
}
@media (max-width: 480px) {
  .facts-grid { grid-template-columns: 1fr; }
}
</style>

<div class="story-wrap">

<!-- MY STORY -->
<div class="story-hero">
  <div class="story-hero-left">
    <div class="story-hero-heading">My<br><span>Story</span></div>
    <div class="story-hero-text">
      <!-- Replace this with your own story text -->
      I grew up on a mixed grain and cattle farm in rural Saskatchewan, where you learn early that every system is connected and every decision has a downstream consequence. That way of thinking never left me.
      <br><br>
      I currently work at a grass-fed beef cattle ranch while finishing my Bachelor of Business Management degree and building a career in data analytics. The transition made more sense than it sounds — ranching runs on margins, weather patterns, and operational efficiency. The data was always there. I just started paying closer attention to it.
      <br><br>
      After moving into marketing and sales, I became absorbed by the numbers behind the outcomes. I taught myself SQL and Python out of pure curiosity, then completed the IBM Data Analytics Professional Certificate across eleven courses. I work best where the analysis has real stakes and the findings actually drive decisions.
    </div>
  </div>
  <div class="story-hero-right">
    <div class="story-photo story-photo-tall">
      <img src="/assets/img/prof_pic.jpg" alt="Paige Ball">
    </div>
  </div>
</div>

<!-- TICKER -->
<div class="ticker-wrap">
  <div class="ticker-track">
    <span>Facts About Me</span><span class="dot">•</span>
    <span>Facts About Me</span><span class="dot">•</span>
    <span>Facts About Me</span><span class="dot">•</span>
    <span>Facts About Me</span><span class="dot">•</span>
    <span>Facts About Me</span><span class="dot">•</span>
    <span>Facts About Me</span><span class="dot">•</span>
    <span>Facts About Me</span><span class="dot">•</span>
    <span>Facts About Me</span><span class="dot">•</span>
  </div>
</div>

<!-- FACTS GRID -->
<div class="facts-grid">
  <div class="fact-card">
    <div class="fact-card-image" style="padding: 0;">
      <img src="/assets/img/sunrisehike2025.jpeg" alt="Sunrise hike 2025">
    </div>
    <div class="fact-card-body">
      <div class="fact-card-title">I do a yearly sunrise hike...</div>
      <div class="fact-card-desc">Getting up at 1:00am is tough, but the 5:00am sunrise at the top of a mountain is worth it.</div>
    </div>
  </div>
  <div class="fact-card">
    <div class="fact-card-image" style="padding: 0;">
      <img src="/assets/img/snowboard2026.jpeg" alt="Snowboarding 2026">
    </div>
    <div class="fact-card-body">
      <div class="fact-card-title">I grew up skiing...</div>
      <div class="fact-card-desc">but switched to snowboarding a few years ago.</div>
    </div>
  </div>
  <div class="fact-card">
    <div class="fact-card-image" style="padding: 0;">
      <img src="/assets/img/smokedmeat2025.jpg" alt="Smoked meat 2025">
    </div>
    <div class="fact-card-body">
      <div class="fact-card-title">A new hobby of mine is smoking meat...</div>
      <div class="fact-card-desc">In the summer/fall, it's as much a science as it is an art.</div>
    </div>
  </div>
  <div class="fact-card">
    <div class="fact-card-image" style="padding: 0;">
      <img src="/assets/img/bungeephoto.JPG" alt="Paige bungee jumping">
    </div>
    <div class="fact-card-body">
      <div class="fact-card-title">I went bungee jumping in 2025...</div>
      <div class="fact-card-desc">...and I'd absolutely do it again!</div>
    </div>
  </div>
</div>


<!-- EDUCATION -->
<div class="timeline-section">
  <div class="facts-heading">Education & Certifications</div>
  <div class="timeline">
    <div class="timeline-item">
      <div class="timeline-date">2026</div>
      <div class="timeline-title">IBM Data Analytics Professional Certificate</div>
      <div class="timeline-subtitle">IBM via Coursera · 11 courses</div>
      <div class="timeline-desc">End-to-end data analytics workflow covering Python, SQL, Excel, Tableau, and IBM Cognos Analytics. Capstone project applied to the Stack Overflow Developer Survey — 65,000+ respondents across 114 variables.</div>
    </div>
    <div class="timeline-item">
      <div class="timeline-date">Completing Summer 2026</div>
      <div class="timeline-title">Bachelor of Business Management</div>
      <div class="timeline-subtitle">Athabasca University · Calgary, AB</div>
      <div class="timeline-desc"><!-- Add relevant coursework or focus areas if desired --></div>
    </div>
  </div>
</div>

<!-- SKILLS -->
<div class="facts-heading">Skills</div>
<div class="skills-grid">
  <div class="skill-card">
    <div class="skill-card-label">Programming & Data</div>
    <div class="skill-tags">
      <span class="skill-tag">Python</span>
      <span class="skill-tag">SQL</span>
      <span class="skill-tag">Pandas</span>
      <span class="skill-tag">NumPy</span>
      <span class="skill-tag">Matplotlib</span>
      <span class="skill-tag">Seaborn</span>
    </div>
  </div>
  <div class="skill-card">
    <div class="skill-card-label">Visualization & BI</div>
    <div class="skill-tags">
      <span class="skill-tag">Tableau</span>
      <span class="skill-tag">Looker Studio</span>
      <span class="skill-tag">IBM Cognos</span>
      <span class="skill-tag">Excel</span>
      <span class="skill-tag">Power BI</span>
    </div>
  </div>
  <div class="skill-card">
    <div class="skill-card-label">Tools & Platforms</div>
    <div class="skill-tags">
      <span class="skill-tag">Jupyter</span>
      <span class="skill-tag">Git</span>
      <span class="skill-tag">GitHub</span>
      <span class="skill-tag">SQLite</span>
      <span class="skill-tag">Microsoft Office</span>
    </div>
  </div>
</div>

<!-- LET'S CONNECT -->
<div class="connect-section">
  <div>
    <div class="connect-heading">Let's<br><span>Connect</span></div>
    <div class="connect-subtext">
      Currently seeking data analyst and business intelligence roles in Calgary and open to remote opportunities across Canada. I'd love to hear from you.
    </div>
    <div class="connect-buttons">
      <a class="connect-btn-primary" href="mailto:p.a.ball@hotmail.com">Send Me an Email</a>
      <a class="connect-btn-secondary" href="/assets/pdf/resume.pdf">Download Resume</a>
    </div>
  </div>
  <div class="connect-details">
    <div class="connect-detail-item">
      <span class="connect-detail-icon">📍</span>
      <div>
        <div class="connect-detail-label">Location</div>
        <div class="connect-detail-value">Calgary, Alberta, Canada</div>
      </div>
    </div>
    <div class="connect-detail-item">
      <span class="connect-detail-icon">✉️</span>
      <div>
        <div class="connect-detail-label">Email</div>
        <div class="connect-detail-value">p.a.ball@hotmail.com</div>
      </div>
    </div>
    <div class="connect-detail-item">
      <span class="connect-detail-icon">💼</span>
      <div>
        <div class="connect-detail-label">Open To</div>
        <div class="connect-detail-value">Data Analyst · BI Developer · Remote</div>
      </div>
    </div>
  </div>
</div>

</div>
