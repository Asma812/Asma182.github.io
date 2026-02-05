---
layout: page
title: Articles & Insights
permalink: /blog/
---

Insights on cybersecurity, threat intelligence, AI in networks, telecom security, and more.

## Security Reports & Writeups

(Click each card to view summary and link)

<details class="card" style="margin: 1.5rem 0; border: 1px solid var(--border); border-radius: 10px; overflow: hidden; background: var(--surface); box-shadow: 0 4px 12px rgba(0,0,0,0.15); transition: all 0.3s;">
  <summary style="padding: 1.2rem 1.8rem; font-size: 1.3rem; font-weight: 600; color: var(--red); cursor: pointer; list-style: none; background: linear-gradient(to right, var(--surface), rgba(230,57,70,0.08));">
    Bug Bounty Report – [Target / Vulnerability Name]
  </summary>
  <div style="padding: 1.6rem; border-top: 1px solid var(--border);">
    <p><strong>Date:</strong> [Month Year]</p>
    <p><strong>Platform:</strong> [HackerOne / Bugcrowd / Intigriti / Private]</p>
    <p><strong>Severity:</strong> [Critical / High / Medium / Low]</p>
    <p><strong>Type:</strong> [e.g., XSS, IDOR, SSRF, API abuse, RCE...]</p>
    <p>Short description of the finding, impact, and how it was exploited. Bounty amount: [$$$ or thanks].</p>
    <p><a href="[link-to-full-report-or-writeup]" style="color: var(--red); font-weight: 600;">Read Full Report →</a></p>
  </div>
</details>

<details class="card" style="margin: 1.5rem 0; border: 1px solid var(--border); border-radius: 10px; overflow: hidden; background: var(--surface); box-shadow: 0 4px 12px rgba(0,0,0,0.15); transition: all 0.3s;">
  <summary style="padding: 1.2rem 1.8rem; font-size: 1.3rem; font-weight: 600; color: var(--accent); cursor: pointer; list-style: none; background: linear-gradient(to right, var(--surface), rgba(0,212,255,0.08));">
    Penetration Test Report – [Client / Scope Name]
  </summary>
  <div style="padding: 1.6rem; border-top: 1px solid var(--border);">
    <p><strong>Date:</strong> [Month Year]</p>
    <p><strong>Scope:</strong> [External / Internal / Web App / API / Cloud...]</p>
    <p><strong>Duration:</strong> [X days / weeks]</p>
    <p><strong>Key findings:</strong> [e.g., 1× Critical, 3× High, 5× Medium]</p>
    <p>Overview of methodology (OSINT, scanning, exploitation, post-exploitation), tools used, and main vulnerabilities discovered.</p>
    <p><a href="[link-to-report-pdf-or-writeup]" style="color: var(--accent); font-weight: 600;">Read Full Pentest Report →</a></p>
  </div>
</details>

<details class="card" style="margin: 1.5rem 0; border: 1px solid var(--border); border-radius: 10px; overflow: hidden; background: var(--surface); box-shadow: 0 4px 12px rgba(0,0,0,0.15); transition: all 0.3s;">
  <summary style="padding: 1.2rem 1.8rem; font-size: 1.3rem; font-weight: 600; color: var(--green); cursor: pointer; list-style: none; background: linear-gradient(to right, var(--surface), rgba(63,185,80,0.08));">
    Infrastructure Hardening Project – [System / Environment Name]
  </summary>
  <div style="padding: 1.6rem; border-top: 1px solid var(--border);">
    <p><strong>Date:</strong> [Month Year]</p>
    <p><strong>Environment:</strong> [Linux servers / Windows AD / Cloud / Hybrid...]</p>
    <p><strong>Standards applied:</strong> [CIS Benchmarks, NIST 800-53, custom...]</p>
    <p>Before/after hardening state, tools used (Ansible, Wazuh, OpenSCAP...), key configurations applied, and validation results (scans, pentest simulation).</p>
    <p><a href="[link-to-writeup-or-report]" style="color: var(--green); font-weight: 600;">Read Full Hardening Write-up →</a></p>
  </div>
</details>

<!-- Latest Articles / Blog Posts -->
<h2 style="margin: 5rem 0 2rem; color: var(--accent); font-family: 'JetBrains Mono', monospace;">Latest Articles</h2>

{% for post in site.posts %}
<article class="card" style="margin: 1.8rem 0; padding: 1.8rem; border: 1px solid var(--border); border-radius: 10px; background: var(--surface);">
  <h2 style="margin: 0 0 0.8rem; font-size: 1.5rem;">
    <a href="{{ post.url }}" style="color: var(--accent); text-decoration: none;">{{ post.title }}</a>
  </h2>
  <p style="color: var(--text-muted); font-size: 0.95rem; margin: 0 0 1rem;">
    {{ post.date | date: "%b %-d, %Y" }} • {{ post.categories | join: " • " }}
  </p>
  <p style="margin: 0; color: var(--text);">
    {{ post.excerpt | strip_html | truncatewords: 40 }}
  </p>
</article>
{% endfor %}

</div>
