---
layout: home
title: Welcome
---

<div class="container" markdown="1">

<div style="text-align: center; padding: 7rem 1rem 5rem;">
  <h1 style="color: var(--text); font-size: 4.8rem; margin: 0; font-family: 'JetBrains Mono', monospace; letter-spacing: -3px;">
    Asma NEJI
  </h1>
  <p style="color: var(--accent); font-size: 2.4rem; margin: 1.5rem 0; font-weight: 700;">
    Junior Cybersecurity Engineer
  </p>
  <p style="color: var(--text-muted); font-size: 1.6rem; max-width: 900px; margin: 0 auto 3rem;">
    Threat Intelligence • Telecom Security • AI Defense • Penetration Testing • DevSecOps
  </p>

  <div style="margin: 2rem 0;">
    <pre class="terminal">
user@asma:~$ whoami
Asma Neji — Junior Cybersecurity Engineer
user@asma:~$ cat focus.txt
• Threat Hunting & Intelligence
• Network & Telecom Security
• Pentesting & Red Teaming
• DevSecOps & Automation
• AI/ML for Anomaly Detection
user@asma:~$ cat motto.txt
"Secure the signal, defend the spectrum."
    </pre>
  </div>

  <div style="display: flex; justify-content: center; gap: 2.5rem; flex-wrap: wrap; margin-top: 3rem;">
    <span style="color: var(--text-muted); font-size: 1.3rem;">+216 97 322 007</span>
    <a href="mailto:asmaneji20@gmail.com" style="color: var(--accent); font-size: 1.3rem; text-decoration: none;">asmaneji20@gmail.com</a>
    <span style="color: var(--text-muted); font-size: 1.3rem;">Tunis, Tunisia</span>
  </div>

  <div style="margin-top: 4rem; display: flex; justify-content: center; gap: 2.5rem; flex-wrap: wrap;">
    <a href="https://linkedin.com/in/asma-neji" style="color: #fff; background: var(--blue); padding: 1rem 2.5rem; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 1.15rem;">LinkedIn</a>
    <a href="https://github.com/Asma812" style="color: #fff; background: #171515; padding: 1rem 2.5rem; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 1.15rem;">GitHub</a>
    <a href="/assets/cv/AsmaNEJI_CV.pdf" style="color: #fff; background: var(--green); padding: 1rem 2.5rem; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 1.15rem;">Download CV</a>
  </div>
</div>

## Latest Articles
{% for post in site.posts limit:5 %}
<div class="card">
  <h3 style="margin: 0; color: var(--accent);">
    <a href="{{ post.url }}" style="text-decoration: none;">{{ post.title }}</a>
  </h3>
  <p style="color: var(--text-muted); font-size: 0.95rem; margin: 0.6rem 0;">
    {{ post.date | date: "%B %d, %Y" }} • {{ post.categories | join: " • " }}
  </p>
  <p style="margin: 1rem 0 0; color: var(--text);">
    {{ post.excerpt | strip_html | truncate: 160 }}
  </p>
</div>
{% endfor %}

<div style="text-align: center; margin: 4rem 0;">
  <a href="/blog" style="color: var(--accent); font-size: 1.4rem; font-weight: 600; text-decoration: none;">
    View All Articles →
  </a>
</div>

## Featured Projects
<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(340px, 1fr)); gap: 2rem; margin: 4rem 0;">
  <div class="card">
    <h3 style="color: var(--red);">Cyber Threat Intelligence Platform</h3>
    <p style="color: var(--text-muted);">Neo4j • ML • MITRE ATT&CK • Docker</p>
    <a href="/about/#professional-experience" style="color: var(--accent); font-weight: 600;">View Details →</a>
  </div>
  <div class="card">
    <h3 style="color: var(--green);">DevSecOps Pipeline & XDR</h3>
    <p style="color: var(--text-muted);">Jenkins • SonarQube • Wazuh • OpenCTI</p>
    <a href="/about/#professional-experience" style="color: var(--accent); font-weight: 600;">View Details →</a>
  </div>
  <div class="card">
    <h3 style="color: var(--purple);">Virtualized 5G Network Optimization</h3>
    <p style="color: var(--text-muted);">SDN • NFV • AI • Open5GS</p>
    <a href="/about/#academic-projects" style="color: var(--accent); font-weight: 600;">View Details →</a>
  </div>
</div>

<div style="text-align: center; margin: 5rem 0;">
  <a href="/about" style="color: var(--accent); font-size: 1.5rem; font-weight: 600; text-decoration: none;">
    See Full Portfolio →
  </a>
</div>

### Telecom Background
Explore my academic journey in telecom engineering:  
[Telecom Lessons →](/telecom)

[Get in touch](/contact)

</div>
