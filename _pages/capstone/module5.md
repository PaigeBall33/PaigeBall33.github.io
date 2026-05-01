---
layout: page
title: "Module 5: Building a Dashboard"
permalink: /capstone/module5/
nav: false
---

## Overview

Built a fully interactive three-tab dashboard in Google Looker Studio covering current technology usage, future technology trends, and developer demographics across 12 panels, each connected directly to the Stack Overflow survey data.

**Tools:** Google Looker Studio, Stack Overflow Developer Survey dataset

---

## What I Did

- Connected Looker Studio to the survey dataset and organized it into three named tabs: Current Technology Usage, Future Technology Trends, and Demographics
- Tab 1 presents four panels in a 2×2 grid covering the top 10 languages in use, top 10 databases, platform usage as a Treemap, and top 10 web frameworks as a bubble scatter
- Tab 2 mirrors Tab 1 using the WantToWorkWith columns, giving an immediate visual contrast between what developers use today versus what they plan to use next year
- Tab 3 surfaces the respondent profile through an age breakdown pie chart, a world geographic map, an education level combo chart, and age crossed with education level as a stacked bar
- Applied null-value exclusion filters to every panel so blank dimension entries do not distort chart proportions
- Arranged all panels in consistent 2×2 grid layouts per tab for visual balance and presentation-readiness

---

## Key Findings

With 41.3% of respondents aged 25–34 and another 27.3% in the 35–44 bracket, nearly 69% of the survey population falls within a single sixteen-year window. The geographic map shows heavy concentration in the US and India, meaning any global aggregate figure from this dataset should be treated with country-level context in mind. Python appears prominently across every age group in the desired languages chart — that breadth of demand across generations distinguishes it from other trending languages.

---

## Dashboard Structure: 12 Panels Across 3 Tabs

| Tab | Panel | Chart Type | Dimension |
|---|---|---|---|
| Tab 1: Current Usage | Top 10 Languages Used | Stacked Bar | LanguageHaveWorkedWith |
| Tab 1: Current Usage | Top 10 Databases Used | Stacked Column | DatabaseHaveWorkedWith |
| Tab 1: Current Usage | Top Platforms Used | Treemap | PlatformHaveWorkedWith |
| Tab 1: Current Usage | Top 10 Web Frameworks | Scatter/Bubble | WebframeHaveWorkedWith |
| Tab 2: Future Trends | Top 10 Languages Desired | Stacked Bar | LanguageWantToWorkWith |
| Tab 2: Future Trends | Top 10 Databases Desired | Stacked Column | DatabaseWantToWorkWith |
| Tab 2: Future Trends | Top 10 Desired Platforms | Treemap | PlatformWantToWorkWith |
| Tab 2: Future Trends | Top 10 Desired Frameworks | Scatter/Bubble | WebframeWantToWorkWith |
| Tab 3: Demographics | Respondents by Age | Pie Chart | Age |
| Tab 3: Demographics | Respondent Count by Country | Geo Map | Country |
| Tab 3: Demographics | Distribution by Education | Combo Chart | EdLevel |
| Tab 3: Demographics | Age × Education Level | Stacked Bar | Age + EdLevel |

---

## Dashboard Screenshots

<style>
.dash-gallery { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1rem; margin: 1.25rem 0 1.5rem; }
.dash-fig { margin: 0; }
.dash-fig img { width: 100%; border-radius: 8px; border: 1px solid #e2e8f0; display: block; cursor: zoom-in; transition: box-shadow 0.18s; }
.dash-fig img:hover { box-shadow: 0 4px 16px rgba(37,99,235,0.18); }
.dash-fig figcaption { font-size: 0.76rem; color: #64748b; text-align: center; margin-top: 0.4rem; font-weight: 600; }
@media (max-width: 640px) { .dash-gallery { grid-template-columns: 1fr; } }
</style>

<div class="dash-gallery">
  <figure class="dash-fig">
    <img src="/assets/img/projects/Capstone_Looker_Dashboard_1.png"
         alt="Looker Studio dashboard — Tab 1: Current Technology Usage"
         class="zoomable">
    <figcaption>Tab 1 — Current Technology Usage</figcaption>
  </figure>
  <figure class="dash-fig">
    <img src="/assets/img/projects/Capstone_Looker_Dashboard_2.png"
         alt="Looker Studio dashboard — Tab 2: Future Technology Trends"
         class="zoomable">
    <figcaption>Tab 2 — Future Technology Trends</figcaption>
  </figure>
  <figure class="dash-fig">
    <img src="/assets/img/projects/Capstone_Looker_Dashboard_3.png"
         alt="Looker Studio dashboard — Tab 3: Demographics"
         class="zoomable">
    <figcaption>Tab 3 — Demographics</figcaption>
  </figure>
</div>

---

## Code Highlights

**Null filter applied to every panel:**

```
Filter Name: Exclude Nulls
Condition: Exclude
Field: [Dimension field e.g. LanguageHaveWorkedWith]
Operator: Is Null
```

Applied to all 12 panels across 3 tabs to ensure blank/null entries do not distort chart proportions.

---

## Skills Demonstrated

Google Looker Studio, interactive dashboard design, stacked bar and column charts, Treemap visualizations, scatter and bubble charts, pie charts, geographic map charts, combo charts, null filter configuration, multi-tab dashboard layout, dimension and metric configuration, data storytelling, dashboard-to-presentation integration.

[← Back to Capstone Overview](/projects/ibm_capstone/){:.btn}
