---
layout: page
title: Articles & Insights
permalink: /blog/
---

Insights on cybersecurity, threat intelligence, AI in networks, telecom security, and more.

## Security Reports & Writeups

(Click a card to read the full report or write-up)

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(340px, 1fr)); gap: 2rem; margin: 3rem 0;">
  <!-- Card 1: crAPI Bug Bounty Report -->
  <details class="card" style="background: var(--surface); border: 1px solid var(--border); border-radius: 12px; overflow: hidden; box-shadow: 0 4px 12px rgba(0,0,0,0.15); transition: all 0.3s;">
    <summary style="padding: 1.4rem 1.8rem; font-size: 1.35rem; font-weight: 600; color: var(--red); cursor: pointer; list-style: none; background: linear-gradient(to right, var(--surface), rgba(230,57,70,0.08));">
      Bug Bounty Report – crAPI (Multiple Vulnerabilities)
    </summary>
    <div style="padding: 1.8rem; border-top: 1px solid var(--border);">
      <p><strong>Severity:</strong> Critical / High / Medium (8 confirmed issues)</p>
      <p><strong>Target:</strong> crAPI (completely ridiculous API) – public bug bounty target</p>
      <p><strong>Date:</strong> [Month Year – e.g., Feb 2026]</p>
      <p>Comprehensive bug bounty engagement on crAPI, uncovering critical authentication bypasses, authorization flaws, business logic issues, and more.</p>
      <p><strong>Key findings summary:</strong></p>
      <ul>
        <li>JWT alg=none Authentication Bypass (Critical)</li>
        <li>JWT Expiration Not Enforced (High)</li>
        <li>Missing JWT Revocation on Logout (Medium)</li>
        <li>Broken Object Level Authorization (IDOR) – Orders API (High)</li>
        <li>Mass Assignment Vulnerability (Privilege Manipulation) (Critical)</li>
        <li>Business Logic Flaw – Negative Quantity Credit Abuse (Critical)</li>
        <li>Business Logic Flaw – Unlimited Order Amount (High)</li>
        <li>Missing Rate Limiting on Login Endpoint (High)</li>
      </ul>
      <p>Also tested & documented safe items (Informational / Not Vulnerable): XSS, CSRF, CORS, File Upload Execution, SQLi, Clickjacking.</p>
      <p><a href="[link-to-your-full-crAPI-report]" style="color: var(--red); font-weight: 600; text-decoration: none;">Read Full Bug Bounty Report →</a></p>
    </div>
  </details>

  <!-- Card 2: Pentest (placeholder) -->
  <details class="card" style="background: var(--surface); border: 1px solid var(--border); border-radius: 12px; overflow: hidden; box-shadow: 0 4px 12px rgba(0,0,0,0.15); transition: all 0.3s;">
    <summary style="padding: 1.4rem 1.8rem; font-size: 1.35rem; font-weight: 600; color: var(--accent); cursor: pointer; list-style: none; background: linear-gradient(to right, var(--surface), rgba(0,212,255,0.08));">
      Penetration Test Report – [Client / Scope Name]
    </summary>
    <div style="padding: 1.8rem; border-top: 1px solid var(--border);">
      <p><strong>Scope:</strong> [External/Internal/Web/API]</p>
      <p><strong>Findings:</strong> 1× Critical, 3× High • Date: [Month Year]</p>
      <p>Comprehensive external/internal pentest with OSINT, scanning, exploitation, and post-exploitation phases. Key vulnerabilities and remediation recommendations included.</p>
      <p><a href="[link-to-report-or-writeup]" style="color: var(--accent); font-weight: 600; text-decoration: none;">Read Full Pentest Report →</a></p>
    </div>
  </details>

  <!-- Card 3: Hardening Project (placeholder) -->
  <details class="card" style="background: var(--surface); border: 1px solid var(--border); border-radius: 12px; overflow: hidden; box-shadow: 0 4px 12px rgba(0,0,0,0.15); transition: all 0.3s;">
    <summary style="padding: 1.4rem 1.8rem; font-size: 1.35rem; font-weight: 600; color: var(--green); cursor: pointer; list-style: none; background: linear-gradient(to right, var(--surface), rgba(63,185,80,0.08));">
      Infrastructure Hardening Project – [System / Environment Name]
    </summary>
    <div style="padding: 1.8rem; border-top: 1px solid var(--border);">
      <p><strong>Environment:</strong> [Linux/AD/Cloud]</p>
      <p><strong>Standards:</strong> CIS/NIST • Date: [Month Year]</p>
      <p>Hardening of servers/network using Ansible, Wazuh, OpenSCAP. Before/after state, applied configurations, and validation scans.</p>
      <p><a href="[link-to-writeup-or-report]" style="color: var(--green); font-weight: 600; text-decoration: none;">Read Full Hardening Write-up →</a></p>
    </div>
  </details>
</div>

<!-- Latest Articles – also in cards with date & reading length -->
<h2 style="margin: 6rem 0 2.5rem; color: var(--accent); font-family: 'JetBrains Mono', monospace; text-align: center;">Latest Articles</h2>

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(340px, 1fr)); gap: 2rem;">
  {% for post in site.posts %}
  <div class="card" style="padding: 1.8rem; background: var(--surface); border: 1px solid var(--border); border-radius: 12px; transition: all 0.3s; box-shadow: 0 4px 12px rgba(0,0,0,0.15);">
    <h3 style="margin: 0 0 0.8rem; font-size: 1.35rem;">
      <a href="{{ post.url }}" style="color: var(--accent); text-decoration: none;">{{ post.title }}</a>
    </h3>
    <p style="color: var(--text-muted); font-size: 0.95rem; margin: 0 0 1rem;">
      {{ post.date | date: "%b %-d, %Y" }} • {{ post.categories | join: " • " }} • ~{{ post.content | number_of_words }} words
    </p>
    <p style="margin: 0; color: var(--text);">
      {{ post.excerpt | strip_html | truncatewords: 35 }}
    </p>
  </div>
  {% endfor %}
</div>

<div style="text-align: center; margin: 4rem 0;">
  <a href="/blog" style="color: var(--accent); font-size: 1.3rem; font-weight: 600; text-decoration: none;">
    View All Articles →
  </a>
</div>
