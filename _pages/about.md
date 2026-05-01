---
layout: about
title: About
permalink: /
subtitle: "IBM Certified Data Analyst | Python, SQL, Tableau, Excel"
nav: false

profile:
  align: right
  image: prof_pic.jpg
  image_circular: false # crops the image to make it circular
  more_info: >
    <p>Calgary, AB</p>
    <p>p.a.ball@hotmail.com</p>
  
selected_papers: false #no research papers to post yet
social: true # includes social icons at the bottom of the page

latest_posts:
  enabled: false
---

<style>
* { box-sizing: border-box; }

/* Hide the layout's auto-rendered page title/subtitle — hero section replaces them */
.post-header { display: none; }

/* ────────────────────────────────────────────────────────
   1. HERO SECTION
   The profile photo (from frontmatter, profile.align: right) floats right
   and sits beside this text, giving the photo-on-right layout automatically.
   ──────────────────────────────────────────────────────── */
.ab-hero { padding: 1.5rem 0 0; }

.ab-uvp {
  font-size: clamp(1.75rem, 4vw, 2.5rem);
  font-weight: 800;
  color: #1e293b;
  line-height: 1.2;
  margin: 0 0 1rem;
}
.ab-uvp span { color: #2563eb; }

.ab-sub {
  font-size: 1.02rem;
  color: #475569;
  line-height: 1.7;
  max-width: 500px;
  margin: 0 0 1.75rem;
}

.ab-ctas { display: flex; flex-wrap: wrap; gap: 0.75rem; margin-bottom: 2.5rem; }

.ab-btn {
  display: inline-block;
  border-radius: 8px;
  padding: 0.6rem 1.4rem;
  font-size: 0.93rem;
  font-weight: 700;
  text-decoration: none;
  transition: all 0.18s;
}
.ab-btn-primary  { background: #2563eb; color: #fff; border: 2px solid #2563eb; }
.ab-btn-primary:hover  { background: #1d4ed8; border-color: #1d4ed8; color: #fff; text-decoration: none; }
.ab-btn-secondary { background: transparent; color: #2563eb; border: 2px solid #2563eb; }
.ab-btn-secondary:hover { background: #eff6ff; color: #1d4ed8; text-decoration: none; }

/* ────────────────────────────────────────────────────────
   2. SKILLS STRIP
   ──────────────────────────────────────────────────────── */
.ab-strip {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
  margin: 3rem 0;
}
.ab-strip-card {
  background: #fff;
  border: 1.5px solid #e2e8f0;
  border-radius: 12px;
  padding: 1.1rem 1.25rem;
  text-align: center;
}
.ab-strip-card .strip-label {
  font-size: 0.68rem;
  font-weight: 700;
  color: #94a3b8;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  margin-bottom: 0.35rem;
}
.ab-strip-card .strip-value {
  font-size: 0.92rem;
  font-weight: 700;
  color: #1e293b;
  line-height: 1.3;
}

/* ────────────────────────────────────────────────────────
   3. ABOUT SECTION
   Photo left, text right.
   ──────────────────────────────────────────────────────── */
.ab-about {
  display: grid;
  grid-template-columns: 200px 1fr;
  gap: 2.5rem;
  align-items: start;
  margin: 3.5rem 0;
}
.ab-about-photo img {
  width: 100%;
  border-radius: 12px;
  object-fit: cover;
  display: block;
}
.ab-small-label {
  font-size: 0.7rem;
  font-weight: 700;
  color: #2563eb;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  margin-bottom: 0.5rem;
}
.ab-about-text h2 {
  font-size: 1.45rem;
  font-weight: 800;
  color: #1e293b;
  margin: 0 0 0.9rem;
  line-height: 1.25;
}
.ab-about-text p {
  font-size: 0.93rem;
  color: #334155;
  line-height: 1.7;
  margin: 0 0 0.85rem;
}
.ab-tool-tags { display: flex; flex-wrap: wrap; gap: 0.4rem; margin-top: 1rem; }
.ab-tool-tag {
  background: #eff6ff;
  color: #1d4ed8;
  border-radius: 20px;
  padding: 0.22rem 0.75rem;
  font-size: 0.76rem;
  font-weight: 700;
}

/* ────────────────────────────────────────────────────────
   4. KEY SKILLS SECTION
   ──────────────────────────────────────────────────────── */
.ab-skills { margin: 3.5rem 0; }

.ab-h2 {
  font-size: 1.45rem;
  font-weight: 800;
  color: #1e293b;
  margin: 0 0 1.4rem;
}

.ab-skills-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
}
.ab-skill-card {
  background: #fff;
  border: 1.5px solid #e2e8f0;
  border-radius: 12px;
  padding: 1.4rem 1.25rem;
  transition: all 0.18s;
}
.ab-skill-card:hover {
  border-color: #2563eb;
  box-shadow: 0 4px 14px rgba(37,99,235,0.12);
  transform: translateY(-2px);
}
.ab-skill-icon { font-size: 1.8rem; margin-bottom: 0.6rem; }
.ab-skill-title { font-size: 1rem; font-weight: 700; color: #1e293b; margin: 0 0 0.45rem; }
.ab-skill-desc  { font-size: 0.86rem; color: #475569; line-height: 1.55; margin: 0; }

/* ────────────────────────────────────────────────────────
   5. PROJECTS SECTION
   ──────────────────────────────────────────────────────── */
.ab-projects { margin: 3.5rem 0; }
.ab-project-card {
  background: #fff;
  border: 1.5px solid #e2e8f0;
  border-radius: 12px;
  padding: 1.75rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 2rem;
  transition: all 0.18s;
}
.ab-project-card:hover {
  border-color: #2563eb;
  box-shadow: 0 4px 18px rgba(37,99,235,0.12);
}
.proj-label {
  font-size: 0.7rem;
  font-weight: 700;
  color: #2563eb;
  text-transform: uppercase;
  letter-spacing: 0.07em;
  margin-bottom: 0.4rem;
}
.proj-title { font-size: 1.12rem; font-weight: 800; color: #1e293b; margin: 0 0 0.5rem; }
.proj-desc  { font-size: 0.9rem; color: #475569; line-height: 1.6; margin: 0; }

/* ────────────────────────────────────────────────────────
   6. TESTIMONIALS SECTION
   ──────────────────────────────────────────────────────── */
.ab-testimonials { margin: 3.5rem 0; }
.ab-testimonials-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
}
.ab-testimonial-card {
  background: #fff;
  border: 1.5px solid #e2e8f0;
  border-radius: 12px;
  padding: 1.4rem;
}
.ab-avatar {
  width: 52px; height: 52px;
  border-radius: 50%;
  background: #e2e8f0;
  margin-bottom: 0.75rem;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.35rem;
}
.ab-t-name { font-size: 0.95rem; font-weight: 700; color: #1e293b; margin: 0 0 0.15rem; }
.ab-t-role { font-size: 0.76rem; color: #64748b; margin: 0 0 0.75rem; }
.ab-t-quote { font-size: 0.86rem; color: #334155; line-height: 1.6; font-style: italic; margin: 0; }

/* ────────────────────────────────────────────────────────
   7. FINAL CTA SECTION
   ──────────────────────────────────────────────────────── */
.ab-final-cta {
  background: #1e293b;
  border-radius: 16px;
  padding: 3rem 2rem;
  text-align: center;
  margin: 3.5rem 0 2.5rem;
}
.ab-final-cta h2 { font-size: 1.65rem; font-weight: 800; color: #f8fafc; margin: 0 0 0.7rem; }
.ab-final-cta p  { font-size: 1rem; color: #94a3b8; line-height: 1.6; margin: 0 0 1.75rem; }
.ab-final-cta .ab-ctas { justify-content: center; margin: 0; }
.ab-final-cta .ab-btn-secondary {
  color: #f8fafc;
  border-color: rgba(248,250,252,0.5);
}
.ab-final-cta .ab-btn-secondary:hover {
  background: rgba(248,250,252,0.1);
  color: #f8fafc;
  border-color: #f8fafc;
}

/* ────────────────────────────────────────────────────────
   RESPONSIVE
   ──────────────────────────────────────────────────────── */
@media (max-width: 640px) {
  .ab-strip             { grid-template-columns: 1fr; }
  .ab-about             { grid-template-columns: 1fr; }
  .ab-about-photo       { text-align: center; }
  .ab-about-photo img   { max-width: 160px; margin: 0 auto; }
  .ab-skills-grid       { grid-template-columns: 1fr; }
  .ab-project-card      { flex-direction: column; align-items: flex-start; gap: 1.25rem; }
  .ab-testimonials-grid { grid-template-columns: 1fr; }
  .ab-final-cta         { padding: 2rem 1.25rem; }
}

@media (min-width: 641px) and (max-width: 900px) {
  .ab-strip             { grid-template-columns: 1fr 1fr; }
  .ab-skills-grid       { grid-template-columns: 1fr 1fr; }
  .ab-testimonials-grid { grid-template-columns: 1fr; }
}
</style>

<!-- ══════════════════════════════════════════════════════
     1. HERO SECTION
     The profile photo (layout: about, profile.align: right) floats to the
     right of this block, giving the photo-on-right layout automatically.
     ══════════════════════════════════════════════════════ -->
<div class="ab-hero">
  <h1 class="ab-uvp">I turn <span>messy data</span><br>into clear decisions.</h1>
  <!-- Add/edit the subheading value proposition below -->
  <p class="ab-sub">
    IBM-certified data analyst with hands-on experience across the full analytics
    pipeline — from API collection and SQL querying to executive dashboards and
    stakeholder presentations. Open to analyst and BI roles in Calgary and remote
    across Canada.
  </p>
  <div class="ab-ctas">
    <a href="/portfolio/" class="ab-btn ab-btn-primary">View My Work</a>
    <a href="/assets/pdf/resume.pdf" download class="ab-btn ab-btn-secondary">Download Resume</a>
  </div>
</div>

<!-- Clears the profile photo float so subsequent sections run full width -->
<div style="clear: both; padding-top: 0.5rem;"></div>

<!-- ══════════════════════════════════════════════════════
     2. SKILLS STRIP
     Three credential/stat cards in a row.
     ══════════════════════════════════════════════════════ -->
<div class="ab-strip">
  <div class="ab-strip-card">
    <div class="strip-label">Certification</div>
    <div class="strip-value">IBM Certified Data Analyst</div>
  </div>
  <div class="ab-strip-card">
    <div class="strip-label">Education</div>
    <div class="strip-value">Bachelor of Management · Completing 2026</div>
  </div>
  <div class="ab-strip-card">
    <div class="strip-label">Location</div>
    <div class="strip-value">Calgary, AB · Open to Remote</div>
  </div>
</div>

<!-- ══════════════════════════════════════════════════════
     3. ABOUT SECTION
     Photo left, text right.
     ══════════════════════════════════════════════════════ -->
<div class="ab-about">
  <div class="ab-about-photo">
    <img src="/assets/img/prof_pic.jpg" alt="Paige Ball">
  </div>
  <div class="ab-about-text">
    <div class="ab-small-label">About Me</div>
    <h2>Data analyst. Ranch hand.<br>Lifelong problem solver.</h2>
    <!-- Add your first bio paragraph here -->
    <p>
      I grew up on a mixed grain and cattle farm in rural Saskatchewan — a place where
      every system is connected and every decision has a downstream consequence. That
      way of thinking shaped how I approach data: follow the chain, find the leverage
      point, communicate the finding clearly.
    </p>
    <!-- Add a second paragraph here, or delete if not needed -->
    <p>
      I currently work at a grass-fed beef ranch while finishing my Bachelor of Management
      and building a career in data analytics. I completed eleven IBM Professional Certificate
      courses, applying Python, SQL, Excel, and Tableau to real business problems along the way.
    </p>
    <div class="ab-tool-tags">
      <span class="ab-tool-tag">Python</span>
      <span class="ab-tool-tag">SQL</span>
      <span class="ab-tool-tag">Tableau</span>
      <span class="ab-tool-tag">Excel</span>
    </div>
  </div>
</div>

<!-- ══════════════════════════════════════════════════════
     4. KEY SKILLS SECTION
     Three cards: Data Analysis, Visualization, Communication.
     ══════════════════════════════════════════════════════ -->
<div class="ab-skills">
  <h2 class="ab-h2">What I Bring to the Table</h2>
  <div class="ab-skills-grid">
    <div class="ab-skill-card">
      <div class="ab-skill-icon">📊</div>
      <div class="ab-skill-title">Data Analysis</div>
      <!-- Add description here -->
      <p class="ab-skill-desc">From raw survey data to actionable insights using Python, SQL, and
      statistical methods including outlier detection and correlation analysis.</p>
    </div>
    <div class="ab-skill-card">
      <div class="ab-skill-icon">📈</div>
      <div class="ab-skill-title">Visualization</div>
      <!-- Add description here -->
      <p class="ab-skill-desc">Charts and dashboards that make complex findings obvious at a
      glance — built with Matplotlib, Seaborn, Tableau, and Google Looker Studio.</p>
    </div>
    <div class="ab-skill-card">
      <div class="ab-skill-icon">💬</div>
      <div class="ab-skill-title">Communication</div>
      <!-- Add description here -->
      <p class="ab-skill-desc">Translating technical findings into plain language that moves
      decision-makers — from annotated notebook to executive slide deck.</p>
    </div>
  </div>
</div>

<!-- ══════════════════════════════════════════════════════
     5. PROJECTS SECTION
     Single featured project card.
     Add more .ab-project-card blocks here as needed.
     ══════════════════════════════════════════════════════ -->
<div class="ab-projects">
  <h2 class="ab-h2">Featured Work</h2>
  <div class="ab-project-card">
    <div>
      <div class="proj-label">IBM Data Analytics Certificate</div>
      <div class="proj-title">Stack Overflow Developer Survey Analysis</div>
      <!-- Add project description here -->
      <p class="proj-desc">End-to-end analytics pipeline across six modules — data collection,
      wrangling, EDA, visualization, interactive dashboard, and executive presentation —
      applied to 65,000+ survey respondents.</p>
    </div>
    <div style="flex-shrink: 0;">
      <a href="/projects/ibm_capstone/" class="ab-btn ab-btn-primary">View Project</a>
    </div>
  </div>
</div>

<!-- ══════════════════════════════════════════════════════
     6. TESTIMONIALS SECTION
     Three placeholder cards — replace with real quotes.
     Each card: circular avatar, name, job title, 2-line quote.
     ══════════════════════════════════════════════════════ -->
<div class="ab-testimonials">
  <h2 class="ab-h2">What Others Say</h2>
  <div class="ab-testimonials-grid">

    <div class="ab-testimonial-card">
      <div class="ab-avatar">👤</div>
      <!-- Replace with real name -->
      <div class="ab-t-name">Name Placeholder</div>
      <!-- Replace with job title / relationship -->
      <div class="ab-t-role">Job Title · Company</div>
      <!-- Replace with real quote (two lines work well) -->
      <p class="ab-t-quote">"Placeholder testimonial — replace with a real recommendation
      from a colleague, manager, or client."</p>
    </div>

    <div class="ab-testimonial-card">
      <div class="ab-avatar">👤</div>
      <div class="ab-t-name">Name Placeholder</div>
      <div class="ab-t-role">Job Title · Company</div>
      <p class="ab-t-quote">"Placeholder testimonial — replace with a real recommendation
      from a colleague, manager, or client."</p>
    </div>

    <div class="ab-testimonial-card">
      <div class="ab-avatar">👤</div>
      <div class="ab-t-name">Name Placeholder</div>
      <div class="ab-t-role">Job Title · Company</div>
      <p class="ab-t-quote">"Placeholder testimonial — replace with a real recommendation
      from a colleague, manager, or client."</p>
    </div>

  </div>
</div>

<!-- ══════════════════════════════════════════════════════
     7. FINAL CTA SECTION
     Dark navy background, centered heading + subheading + two buttons.
     ══════════════════════════════════════════════════════ -->
<div class="ab-final-cta">
  <!-- Edit heading here -->
  <h2>Let's Work Together</h2>
  <!-- Edit subheading here -->
  <p>Open to analyst and BI roles in Calgary and remote opportunities across Canada.<br>
  Let's talk about how data can drive better decisions for your team.</p>
  <div class="ab-ctas">
    <a href="mailto:p.a.ball@hotmail.com" class="ab-btn ab-btn-primary">Get In Touch</a>
    <a href="/portfolio/" class="ab-btn ab-btn-secondary">View My Portfolio</a>
  </div>
</div>
