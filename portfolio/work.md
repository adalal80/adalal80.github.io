---
layout: default
title: Work Projects
permalink: /portfolio/work/
---

<h2 style="margin-top: 1.5rem; margin-bottom: 0.5rem; border-bottom: none;">Work Portfolio</h2>
<p style="font-size: 1.1rem; line-height: 1.6; color: #444; margin-bottom: 2rem;">
  Production-grade enterprise engines, econometric validation models, and risk management systems.
</p>

<div class="project-grid" style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 1.5rem; margin-bottom: 3rem;">
  {% for project in site.data.projects.work_projects %}
    <div class="project-card" style="border: 1px solid #e0e0e0; padding: 1.25rem; border-radius: 6px; background: #fafafa; display: flex; flex-direction: column; justify-content: space-between;">
      <div>
        <h4 style="margin-top: 0; margin-bottom: 0.75rem; font-size: 1.2rem; color: #111; font-weight: 600;">{{ project.name }}</h4>
        <p style="font-size: 0.95rem; line-height: 1.5; margin-bottom: 1.25rem; color: #333;">{{ project.description }}</p>
      </div>
      <div style="font-size: 0.8rem; color: #666; border-top: 1px solid #eee; padding-top: 0.75rem; font-family: monospace;">
        <strong>CAPABILITIES:</strong> {{ project.tech | join: ", " }}
      </div>
    </div>
  {% endfor %}
</div>
