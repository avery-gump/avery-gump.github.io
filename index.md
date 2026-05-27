---
layout: single
title: "Latest Updates"
author_profile: true
---

{% include base_path %}

<div class="home-intro" style="margin-bottom: 40px;">
  <p style="color: var(--global-text-color-light, #666); font-size: 1.1em; margin: 5px 0 0 0;">Snippets, milestones, and quick links from my research portfolio.</p>
</div>

<div class="micro-blog-feed" style="display: flex; flex-direction: column; gap: 20px;">
  
  {% assign timeline_posts = site.mainPagePosts | sort: 'date' | reverse %}
  {% for post in timeline_posts %}
    
    {% if post.category == 'Celebrate' %}
      <a href="{% if post.link %}{{ post.link | relative_url }}{% else %}#{% endif %}" class="pop-hover" style="text-decoration: none; color: inherit; display: block;" {% if post.confetti %}onclick="triggerCelebration(event, '{% if post.link %}{{ post.link | relative_url }}{% else %}#{% endif %}')"{% endif %}>
        <div class="snippet-card" style="background: var(--global-bg-color, #fafafa); border: 1px solid var(--global-border-color, #e1e4e8); border-left: 5px solid {{ post.accent_color | default: '#333' }}; padding: 20px; border-radius: 6px; position: relative;">
          <div style="display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 8px;">
            <span class="snippet-tag" style="background: {{ post.accent_color | append: '1A' | default: 'rgba(0,0,0,0.05)' }}; color: {{ post.accent_color | default: '#333' }}; padding: 3px 10px; border-radius: 12px; font-size: 0.8em; font-weight: bold;">
              🎉 {{ post.tag | default: 'Milestone' }}
            </span>
            <span class="snippet-date" style="font-size: 0.85em; color: #777;">{{ post.date | date: "%B %Y" }}</span>
          </div>
          <h3 style="margin: 5px 0 8px 0; font-size: 1.25em; font-weight: 700; color: var(--global-text-color, #222);">{{ post.title }}</h3>
          <div class="snippet-description" style="margin: 0; font-size: 0.95em; line-height: 1.5; color: var(--global-text-color, #444);">
            {{ post.content | markdownify }}
          </div>
        </div>
      </a>

    {% elsif post.category == 'Project' %}
      <a href="{% if post.link %}{{ post.link | relative_url }}{% else %}#{% endif %}" class="pop-hover" style="text-decoration: none; color: inherit; display: block;" {% if post.confetti %}onclick="triggerCelebration(event, '{% if post.link %}{{ post.link | relative_url }}{% else %}#{% endif %}')"{% endif %}>
        <div class="snippet-card" style="background: var(--global-bg-color, #fafafa); border: 1px solid var(--global-border-color, #e1e4e8); border-left: 5px solid {{ post.accent_color | default: '#0078d4' }}; padding: 20px; border-radius: 6px; position: relative;">
          <div style="display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 8px;">
            <span class="snippet-tag" style="background: {{ post.accent_color | append: '1A' | default: 'rgba(0, 120, 212, 0.1)' }}; color: {{ post.accent_color | default: '#0078d4' }}; padding: 3px 10px; border-radius: 12px; font-size: 0.8em; font-weight: bold;">
              🚀 {{ post.tag | default: 'Project Launch' }}
            </span>
            <span class="snippet-date" style="font-size: 0.85em; color: #777;">{{ post.date | date: "%B %Y" }}</span>
          </div>
          <h3 style="margin: 5px 0 8px 0; font-size: 1.25em; font-weight: 700; color: var(--global-text-color, #222);">{{ post.title }}</h3>
          <div class="snippet-description" style="margin: 0; font-size: 0.95em; line-height: 1.5; color: var(--global-text-color, #444);">
            {{ post.content | markdownify }}
          </div>
          <div style="margin-top: 12px; font-size: 0.85em; color: {{ post.accent_color | default: '#0078d4' }}; font-weight: 600;">
            Explore project &rarr;
          </div>
        </div>
      </a>

    {% elsif post.category == 'Blog' %}
      <a href="{% if post.link %}{{ post.link | relative_url }}{% else %}#{% endif %}" class="pop-hover" style="text-decoration: none; color: inherit; display: block;" {% if post.confetti %}onclick="triggerCelebration(event, '{% if post.link %}{{ post.link | relative_url }}{% else %}#{% endif %}')"{% endif %}>
        <div class="snippet-card" style="background: var(--global-bg-color, #fafafa); border: 1px solid var(--global-border-color, #e1e4e8); border-left: 5px solid {{ post.accent_color | default: '#6f42c1' }}; padding: 20px; border-radius: 6px; position: relative;">
          <div style="display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 8px;">
            <span class="snippet-tag" style="background: {{ post.accent_color | append: '1A' | default: 'rgba(111, 66, 193, 0.1)' }}; color: {{ post.accent_color | default: '#6f42c1' }}; padding: 3px 10px; border-radius: 12px; font-size: 0.8em; font-weight: bold;">
              📝 {{ post.tag | default: 'New Post' }}
            </span>
            <span class="snippet-date" style="font-size: 0.85em; color: #777;">{{ post.date | date: "%B %Y" }}</span>
          </div>
          <h3 style="margin: 5px 0 8px 0; font-size: 1.25em; font-weight: 700; color: var(--global-text-color, #222);">{{ post.title }}</h3>
          <div class="snippet-description" style="margin: 0; font-size: 0.95em; line-height: 1.5; color: var(--global-text-color, #444);">
            {{ post.content | markdownify }}
          </div>
          <div style="margin-top: 12px; font-size: 0.85em; color: {{ post.accent_color | default: '#6f42c1' }}; font-weight: 600;">
            Read article &rarr;
          </div>
        </div>
      </a>

    {% else %}
      <a href="{% if post.link %}{{ post.link | relative_url }}{% else %}#{% endif %}" class="pop-hover" style="text-decoration: none; color: inherit; display: block;" {% if post.confetti %}onclick="triggerCelebration(event, '{% if post.link %}{{ post.link | relative_url }}{% else %}#{% endif %}')"{% endif %}>
        <div class="snippet-card" style="background: var(--global-bg-color, #fafafa); border: 1px solid var(--global-border-color, #e1e4e8); border-left: 5px solid {{ post.accent_color | default: '#333' }}; padding: 20px; border-radius: 6px; position: relative;">
          <div style="display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 8px;">
            <span class="snippet-tag" style="background: {{ post.accent_color | append: '1A' | default: 'rgba(0,0,0,0.05)' }}; color: {{ post.accent_color | default: '#333' }}; padding: 3px 10px; border-radius: 12px; font-size: 0.8em; font-weight: bold;">
              {{ post.tag }}
            </span>
            <span class="snippet-date" style="font-size: 0.85em; color: #777;">{{ post.date | date: "%B %Y" }}</span>
          </div>
          <h3 style="margin: 5px 0 8px 0; font-size: 1.25em; font-weight: 700; color: var(--global-text-color, #222);">{{ post.title }}</h3>
          <div class="snippet-description" style="margin: 0; font-size: 0.95em; line-height: 1.5; color: var(--global-text-color, #444);">
            {{ post.content | markdownify }}
          </div>
        </div>
      </a>
    {% endif %}

  {% endfor %}
</div>

<canvas id="confetti-canvas" style="position: fixed; top: 0; left: 0; width: 100vw; height: 100vh; pointer-events: none; z-index: 9999; display: none;"></canvas>

<style>
  .pop-hover {
    transition: transform 0.2s cubic-bezier(0.175, 0.885, 0.32, 1.275), box-shadow 0.2s ease !important;
  }
  .pop-hover:hover {
    transform: translateY(-4px) !important;
    box-shadow: 0 10px 20px rgba(0,0,0,0.07) !important;
  }
  .snippet-description p {
    margin: 0 !important;
  }
</style>

<script>
function triggerCelebration(e, linkUrl) {
  e.preventDefault();
  const card = e.currentTarget;
  card.style.transform = 'scale(0.98)';
  setTimeout(() => card.style.transform = '', 150);

  if (linkUrl && linkUrl !== '#' && linkUrl !== '') {
    setTimeout(() => window.location.href = linkUrl, 800);
  }

  const canvas = document.getElementById('confetti-canvas');
  const ctx = canvas.getContext('2d');
  canvas.style.display = 'block';
  canvas.width = window.innerWidth;
  canvas.height = window.innerHeight;

  let particles = [];
  const colors = ['#28a745', '#0078d4', '#ffc107', '#dc3545', '#6f42c1'];

  for (let i = 0; i < 120; i++) {
    particles.push({
      x: window.innerWidth / 2 + (Math.random() * 200 - 100),
      y: window.innerHeight * 0.6,
      angle: Math.random() * Math.PI * 2,
      speed: 15 + Math.random() * 15,
      friction: 0.94,
      gravity: 1.2,
      color: colors[Math.floor(Math.random() * colors.length)],
      size: 6 + Math.random() * 6,
      rotation: Math.random() * 360,
      rotationSpeed: Math.random() * 10 - 5
    });
  }

  function runConfetti() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    let alive = false;
    
    particles.forEach(p => {
      p.x += Math.cos(p.angle) * p.speed;
      p.y += Math.sin(p.angle) * p.speed + p.gravity;
      p.speed *= p.friction;
      p.rotation += p.rotationSpeed;
      ctx.save();
      ctx.translate(p.x, p.y);
      ctx.rotate(p.rotation * Math.PI / 180);
      ctx.fillStyle = p.color;
      ctx.fillRect(-p.size / 2, -p.size / 2, p.size, p.size * 1.5);
      ctx.restore();
      if (p.y < canvas.height && p.x > 0 && p.x < canvas.width) alive = true;
    });

    if (alive) {
      requestAnimationFrame(runConfetti);
    } else {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      canvas.style.display = 'none';
    }
  }
  
  runConfetti();
}
</script>