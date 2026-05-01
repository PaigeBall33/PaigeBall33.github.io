---
layout: page
title: Blog
permalink: /blog/
nav: true
nav_order: 4
pagination:
  enabled: true
---

<style>
.blog-hero {
  background: linear-gradient(135deg, #0f172a 0%, #1e293b 60%, #0f2a47 100%);
  color: white;
  text-align: center;
  padding: 4rem 2rem;
  margin: -1rem -1rem 2.5rem -1rem;
  border-radius: 12px;
  position: relative;
  overflow: hidden;
}
.blog-hero::before {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(ellipse at center, rgba(37,99,235,0.15) 0%, transparent 70%);
}
.blog-hero h1 {
  font-size: clamp(2.5rem, 6vw, 4rem);
  font-weight: 800;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  margin: 0 0 0.75rem;
  color: white;
  border: none;
  position: relative;
}
.blog-hero p {
  font-size: 0.82rem;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: #94a3b8;
  margin: 0;
  position: relative;
}
.blog-categories {
  display: flex;
  align-items: center;
  gap: 1.5rem;
  margin-bottom: 2.5rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid #e2e8f0;
  flex-wrap: wrap;
}
.blog-categories-label {
  font-style: italic;
  color: #64748b;
  font-size: 0.95rem;
  white-space: nowrap;
}
.blog-cat-link {
  font-size: 0.78rem;
  font-weight: 700;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: #475569;
  text-decoration: none;
  transition: color 0.15s;
}
.blog-cat-link:hover { color: #2563eb; text-decoration: none; }
.featured-post {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0;
  background: white;
  border: 1px solid #e2e8f0;
  border-radius: 12px;
  overflow: hidden;
  margin-bottom: 2.5rem;
  min-height: 380px;
}
.featured-post-image {
  background: linear-gradient(135deg, #1e293b, #0f2a47);
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  min-height: 320px;
}
.featured-badge {
  position: absolute;
  top: 1.2rem;
  left: 1.2rem;
  width: 64px;
  height: 64px;
  background: #1e293b;
  color: white;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.6rem;
  font-weight: 800;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  text-align: center;
  line-height: 1.2;
}
.featured-post-image-placeholder {
  width: 100%;
  height: 100%;
  min-height: 320px;
  background: linear-gradient(135deg, #1e293b 0%, #0f2a47 50%, #1e3a5f 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 4rem;
  opacity: 0.3;
}
.featured-post-content {
  padding: 2.5rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.featured-post-category {
  font-size: 0.72rem;
  font-weight: 700;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: #2563eb;
  margin-bottom: 0.75rem;
}
.featured-post-title {
  font-size: clamp(1.3rem, 2.5vw, 1.8rem);
  font-weight: 800;
  color: #0f172a;
  line-height: 1.25;
  margin-bottom: 1rem;
  text-transform: uppercase;
  letter-spacing: 0.02em;
}
.featured-post-excerpt {
  font-size: 0.9rem;
  color: #475569;
  line-height: 1.7;
  margin-bottom: 1.5rem;
  flex-grow: 1;
}
.featured-post-meta {
  font-size: 0.75rem;
  color: #94a3b8;
  margin-bottom: 1rem;
}
.btn-read {
  display: inline-block;
  border: 1.5px solid #1e293b;
  color: #1e293b;
  padding: 0.5rem 1.2rem;
  font-size: 0.78rem;
  font-weight: 700;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  text-decoration: none;
  border-radius: 4px;
  transition: all 0.18s;
  align-self: flex-start;
}
.btn-read:hover { background: #1e293b; color: white; text-decoration: none; }
.posts-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.5rem;
  margin-bottom: 2.5rem;
}
.post-card {
  background: white;
  border: 1px solid #e2e8f0;
  border-radius: 12px;
  overflow: hidden;
  transition: all 0.18s;
  text-decoration: none;
  color: inherit;
  display: block;
}
.post-card:hover {
  border-color: #2563eb;
  box-shadow: 0 4px 16px rgba(37,99,235,0.12);
  transform: translateY(-3px);
  text-decoration: none;
  color: inherit;
}
.post-card-image {
  height: 180px;
  background: linear-gradient(135deg, #1e293b, #0f2a47);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2.5rem;
  position: relative;
  overflow: hidden;
}
.post-card-category-vertical {
  position: absolute;
  left: 0.75rem;
  top: 50%;
  transform: translateY(-50%) rotate(-90deg);
  font-size: 0.6rem;
  font-weight: 800;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: rgba(255,255,255,0.6);
  white-space: nowrap;
}
.post-card-body { padding: 1.2rem; }
.post-card-title {
  font-size: 0.95rem;
  font-weight: 700;
  color: #0f172a;
  line-height: 1.4;
  margin-bottom: 0.5rem;
}
.post-card-excerpt {
  font-size: 0.82rem;
  color: #64748b;
  line-height: 1.6;
  margin-bottom: 0.8rem;
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
}
.post-card-read-more {
  font-size: 0.78rem;
  font-weight: 700;
  color: #2563eb;
  text-decoration: none;
  display: flex;
  align-items: center;
  gap: 0.3rem;
}
.post-card-read-more:hover { color: #1d4ed8; text-decoration: none; }
.no-posts {
  text-align: center;
  padding: 4rem 2rem;
  color: #94a3b8;
  background: white;
  border: 1px dashed #e2e8f0;
  border-radius: 12px;
  margin-bottom: 2.5rem;
}
.no-posts h3 { color: #64748b; margin-bottom: 0.5rem; }
@media (max-width: 768px) {
  .featured-post { grid-template-columns: 1fr; }
  .posts-grid { grid-template-columns: 1fr; }
  .blog-hero { padding: 2.5rem 1rem; }
}
</style>

<div class="blog-hero">
  <h1>The Blog</h1>
  <p>Data analytics · Career journeys · Building in public</p>
</div>

<div class="blog-categories">
  <span class="blog-categories-label">Browse the blog :</span>
  <a class="blog-cat-link" href="#">Data Analytics</a>
  <a class="blog-cat-link" href="#">Career</a>
  <a class="blog-cat-link" href="#">Learning</a>
  <a class="blog-cat-link" href="#">Projects</a>
</div>

{% assign sorted_posts = site.posts | sort: 'date' | reverse %}
{% assign featured = sorted_posts | first %}
{% if featured %}
<div class="featured-post">
  <div class="featured-post-image">
    <div class="featured-badge">Read<br>the<br>latest</div>
    <div class="featured-post-image-placeholder">📊</div>
  </div>
  <div class="featured-post-content">
    <div class="featured-post-category">{{ featured.categories | first | upcase | default: "FEATURED" }}</div>
    <div class="featured-post-title">{{ featured.title | upcase }}</div>
    <div class="featured-post-meta">{{ featured.date | date: "%B %d, %Y" }}</div>
    <div class="featured-post-excerpt">{{ featured.excerpt | strip_html | truncate: 220 }}</div>
    <a class="btn-read" href="{{ featured.url }}">Read Post</a>
  </div>
</div>
{% else %}
<div class="no-posts">
  <h3>Posts coming soon</h3>
  <p>Check back shortly — new posts are on the way.</p>
</div>
{% endif %}

{% assign remaining_posts = sorted_posts | offset: 1 %}
{% if remaining_posts.size > 0 %}
<div class="posts-grid">
{% for post in remaining_posts limit: 6 %}
<a class="post-card" href="{{ post.url }}">
  <div class="post-card-image">
    <span class="post-card-category-vertical">{{ post.categories | first | upcase | default: "BLOG" }}</span>
    <span style="font-size:2.5rem;">📈</span>
  </div>
  <div class="post-card-body">
    <div class="post-card-title">{{ post.title }}</div>
    <div class="post-card-excerpt">{{ post.excerpt | strip_html | truncate: 140 }}</div>
    <span class="post-card-read-more">Read More →</span>
  </div>
</a>
{% endfor %}
</div>
{% endif %}
