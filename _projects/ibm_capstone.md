---
layout: page
title: IBM Data Analyst Capstone
description: A complete end-to-end data analytics pipeline applied to the Stack Overflow Developer Survey — 65,000+ respondents across six modules.
img: assets/img/projects/capstone_preview.png
importance: 1
category: data analytics
---

<style>
* { box-sizing: border-box; }
.cap-wrap { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif; color: #1e293b; }
.section-label { font-size: 0.72rem; font-weight: 700; color: #94a3b8; text-transform: uppercase; letter-spacing: 0.08em; margin-bottom: 0.8rem; }
.pipeline-bar { display: flex; align-items: center; justify-content: center; flex-wrap: wrap; gap: 0.3rem; background: #f8fafc; border: 1px solid #e2e8f0; border-radius: 12px; padding: 1.2rem 1rem; margin-bottom: 1.8rem; }
.pipe-step { display: flex; flex-direction: column; align-items: center; gap: 0.25rem; cursor: pointer; }
.pipe-icon { width: 48px; height: 48px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 1.3rem; transition: transform 0.15s; }
.pipe-step:hover .pipe-icon { transform: scale(1.1); }
.pipe-label { font-size: 0.72rem; font-weight: 700; color: #475569; }
.pipe-arrow { color: #cbd5e1; font-size: 1rem; margin-bottom: 1.4rem; }
.modules-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0.9rem; margin-bottom: 1.5rem; }
.mod-card { background: #fff; border: 1.5px solid #e2e8f0; border-radius: 12px; padding: 1.1rem; cursor: pointer; transition: all 0.18s; }
.mod-card:hover { border-color: #2563eb; box-shadow: 0 4px 14px rgba(37,99,235,0.13); transform: translateY(-2px); }
.mod-card.selected { border-color: #2563eb; background: #eff6ff; }
.mod-num { font-size: 0.7rem; font-weight: 700; color: #94a3b8; text-transform: uppercase; letter-spacing: 0.06em; margin-bottom: 0.25rem; }
.mod-icon { font-size: 1.5rem; margin-bottom: 0.3rem; }
.mod-title { font-size: 0.95rem; font-weight: 700; color: #1e293b; margin-bottom: 0.55rem; }
.tags { display: flex; flex-wrap: wrap; gap: 0.3rem; }
.tag { background: #f1f5f9; color: #475569; border-radius: 20px; padding: 0.18rem 0.55rem; font-size: 0.7rem; font-weight: 600; }
.detail-panel { background: #fff; border: 1.5px solid #2563eb; border-radius: 12px; padding: 1.4rem; margin-bottom: 1.5rem; display: none; }
.detail-header { display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.8rem; }
.detail-avatar { width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 1.2rem; flex-shrink: 0; }
.detail-title { font-size: 1.05rem; font-weight: 700; color: #1e293b; margin: 0; }
.detail-sub { font-size: 0.82rem; color: #64748b; margin: 0; }
.detail-body { font-size: 0.9rem; color: #334155; line-height: 1.65; margin-bottom: 1rem; }
.detail-cols { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; margin-bottom: 1rem; }
.detail-col h4 { font-size: 0.78rem; font-weight: 700; color: #2563eb; text-transform: uppercase; letter-spacing: 0.05em; margin: 0 0 0.4rem; }
.detail-col ul { margin: 0; padding-left: 1.1rem; }
.detail-col li { font-size: 0.85rem; color: #334155; margin-bottom: 0.25rem; line-height: 1.5; }
.artifact-hint { background: #f0fdf4; border: 1px solid #86efac; border-radius: 8px; padding: 0.65rem 0.9rem; font-size: 0.83rem; color: #15803d; margin-bottom: 1rem; }
.detail-link { display: inline-block; background: #2563eb; color: #fff; border-radius: 8px; padding: 0.45rem 1rem; font-size: 0.83rem; font-weight: 700; text-decoration: none; transition: background 0.15s; }
.detail-link:hover { background: #1d4ed8; color: #fff; text-decoration: none; }
@media (max-width: 600px) { .modules-grid { grid-template-columns: 1fr; } .detail-cols { grid-template-columns: 1fr; } }
</style>

<div class="cap-wrap">
<p>A complete data analytics workflow applied to the <strong>Stack Overflow Developer Survey</strong> — 65,437 respondents across 114 variables, six modules, from API data collection through stakeholder presentation.</p>
<div class="section-label">Project Pipeline</div>
<div class="pipeline-bar">
  <div class="pipe-step"><div class="pipe-icon" style="background:#dbeafe;">📊</div><div class="pipe-label">Collect</div></div>
  <div class="pipe-arrow">›</div>
  <div class="pipe-step"><div class="pipe-icon" style="background:#fce7f3;">🔧</div><div class="pipe-label">Wrangle</div></div>
  <div class="pipe-arrow">›</div>
  <div class="pipe-step"><div class="pipe-icon" style="background:#ede9fe;">🔍</div><div class="pipe-label">Explore</div></div>
  <div class="pipe-arrow">›</div>
  <div class="pipe-step"><div class="pipe-icon" style="background:#dcfce7;">📈</div><div class="pipe-label">Visualize</div></div>
  <div class="pipe-arrow">›</div>
  <div class="pipe-step"><div class="pipe-icon" style="background:#dbeafe;">🖥️</div><div class="pipe-label">Dashboard</div></div>
  <div class="pipe-arrow">›</div>
  <div class="pipe-step"><div class="pipe-icon" style="background:#fef9c3;">🏆</div><div class="pipe-label">Present</div></div>
</div>
<div class="section-label">Click a module to see details</div>
<div class="modules-grid" id="modGrid"></div>
<div class="detail-panel" id="detailPanel"></div>
</div>

<script>
const modules = [
  { num: "Module 1", icon: "📊", title: "Data Collection", color: "#dbeafe", textColor: "#1d4ed8", tags: ["APIs", "Web Scraping", "Python"], tools: ["Python", "Requests", "BeautifulSoup", "Pandas", "openpyxl"], desc: "Gathered data on in-demand programming skills from a job postings API and web scraping. Loaded the Stack Overflow Developer Survey — 65,457 rows across 117 columns.", skills: ["REST API integration and JSON parsing", "Web scraping with BeautifulSoup", "Data export to Excel and CSV", "Dataset profiling with Pandas", "Feature engineering with regex"], artifacts: "Jupyter notebook screenshots, job-postings.xlsx output, salary CSV", link: "/capstone/module1/" },
  { num: "Module 2", icon: "🔧", title: "Data Wrangling", color: "#fce7f3", textColor: "#9d174d", tags: ["Cleaning", "Pandas", "NumPy"], tools: ["Python", "Pandas", "NumPy", "Matplotlib", "Seaborn"], desc: "Cleaned the dataset by detecting duplicates, imputing missing values, normalizing compensation data, encoding categorical variables, and engineering new features.", skills: ["Duplicate detection with groupby analysis", "Missing value imputation (mode, median, ffill)", "Min-Max Scaling and Z-score Normalization", "One-hot encoding with pd.get_dummies()", "Custom feature engineering with binning functions"], artifacts: "Missing values heatmap, normalization comparison histograms, ExperienceLevel distribution", link: "/capstone/module2/" },
  { num: "Module 3", icon: "🔍", title: "Exploratory Data Analysis", color: "#ede9fe", textColor: "#6d28d9", tags: ["EDA", "Statistics", "Seaborn"], tools: ["Python", "Pandas", "NumPy", "Matplotlib", "Seaborn"], desc: "Performed in-depth EDA examining distributions, identifying outliers using statistical methods, and measuring correlations between compensation, experience, and job satisfaction.", skills: ["Outlier detection: 3-SD method and IQR method", "Pearson correlation matrix computation", "Exploding multi-value semicolon-delimited columns", "Cross-tabulation with pd.crosstab()", "Segmented subgroup analysis"], artifacts: "Correlation heatmap, outlier box plots, language usage heatmap by country", link: "/capstone/module3/" },
  { num: "Module 4", icon: "📈", title: "Data Visualization", color: "#dcfce7", textColor: "#15803d", tags: ["Matplotlib", "Seaborn", "SQLite"], tools: ["Python", "Matplotlib", "Pandas", "SQLite", "NumPy"], desc: "Applied every major chart type across nine labs. Data loaded from a persistent SQLite database via SQL queries. IQR outlier removal applied consistently to all compensation charts.", skills: ["Histograms, box plots, scatter plots, bubble plots", "Pie charts, stacked bars, line charts, bar charts", "SQLite database creation and SQL querying", "Regression trend lines with NumPy polyfit", "Error bars showing compensation variability"], artifacts: "All 9 lab chart outputs, database comparison charts, compensation trend lines", link: "/capstone/module4/" },
  { num: "Module 5", icon: "🖥️", title: "Building a Dashboard", color: "#e0f2fe", textColor: "#0369a1", tags: ["Looker Studio", "BI Tools", "Dashboards"], tools: ["Google Looker Studio", "Stack Overflow Survey Dataset"], desc: "Built a fully interactive three-tab dashboard in Google Looker Studio covering current technology usage, future technology trends, and developer demographics across 12 panels.", skills: ["Multi-tab interactive dashboard design", "Stacked bars, treemaps, bubble charts, geo maps", "Null filter configuration across all panels", "Dimension and metric configuration", "Dashboard-to-presentation integration"], artifacts: "Three full-tab dashboard screenshots, panel configuration documentation", preview: "/assets/img/projects/Capstone_Looker_Dashboard_1.png", link: "/capstone/module5/" },
  { num: "Module 6", icon: "🏆", title: "Final Presentation", color: "#fef9c3", textColor: "#854d0e", tags: ["PowerPoint", "Storytelling", "Report"], tools: ["PowerPoint", "PDF Export"], desc: "Every insight from five modules synthesized into a 17-section executive presentation. One idea per slide, quantitative evidence behind every claim, findings paired with implications.", skills: ["Executive summary and findings framing", "Data storytelling and slide structure", "Chart-to-slide integration", "Cross-module synthesis", "Audience-aware communication"], artifacts: "17-slide PDF deck, language trend charts, job postings bar chart, dashboard tab screenshots", link: "/capstone/module6/" }
];

let selected = null;

function render() {
  document.getElementById('modGrid').innerHTML = modules.map((m, i) => `
    <div class="mod-card ${selected === i ? 'selected' : ''}" onclick="select(${i})">
      <div class="mod-num">${m.num}</div>
      <div class="mod-icon">${m.icon}</div>
      <div class="mod-title">${m.title}</div>
      <div class="tags">${m.tags.map(t => `<span class="tag">${t}</span>`).join('')}</div>
    </div>
  `).join('');
}

function select(i) {
  selected = selected === i ? null : i;
  render();
  const panel = document.getElementById('detailPanel');
  if (selected === null) { panel.style.display = 'none'; return; }
  const m = modules[i];
  panel.style.display = 'block';
  panel.innerHTML = `
    <div class="detail-header">
      <div class="detail-avatar" style="background:${m.color};">${m.icon}</div>
      <div><div class="detail-title">${m.num}: ${m.title}</div><div class="detail-sub">${m.tools.join(' · ')}</div></div>
    </div>
    <div class="detail-body">${m.desc}</div>
    ${m.preview ? `<img src="${m.preview}" alt="${m.title} preview" style="width:100%;border-radius:8px;border:1px solid #e2e8f0;margin-bottom:1rem;display:block;">` : ''}
    <div class="detail-cols">
      <div class="detail-col"><h4>Skills demonstrated</h4><ul>${m.skills.map(s => `<li>${s}</li>`).join('')}</ul></div>
      <div class="detail-col"><h4>Tools used</h4><ul>${m.tools.map(t => `<li>${t}</li>`).join('')}</ul></div>
    </div>
    <div class="artifact-hint"><strong>Portfolio artifacts:</strong> ${m.artifacts}</div>
    <a class="detail-link" href="${m.link}">View full module →</a>
  `;
  panel.scrollIntoView({ behavior: 'smooth', block: 'nearest' });
}

render();
</script>
