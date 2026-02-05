---
layout: home
title: Welcome
---

<div class="container" markdown="1">

<!-- HERO SECTION -->
<div style="text-align: center; padding: 4rem 1rem 3rem; max-width: 1000px; margin: 0 auto;">
  <h1 style="font-family: 'JetBrains Mono', monospace; font-size: 3.2rem; margin: 0 0 0.6rem; color: var(--text); letter-spacing: -1px;">
    Asma NEJI
  </h1>

  <!-- Cybersecurity trick: dig + traceroute style + 3-line intro -->
  <div style="margin: 1.8rem auto; max-width: 780px;">
    <pre style="background: #0a0e14; color: #00b894; font-family: 'JetBrains Mono', monospace; padding: 1.3rem; border-radius: 10px; border: 1px solid #21262d; font-size: 0.98rem; line-height: 1.55; text-align: left; overflow-x: auto;">
dig asma.neji +short
  185.199.108.153   ; github.io edge

traceroute asma.neji
  1  192.168.1.1     0.8 ms
  2  isp-gateway      4.2 ms
  3  te Tunis node    12 ms
  4  global backbone  28 ms
  5  github edge      42 ms

Junior Cybersecurity Engineer
Threat Intelligence • Telecom Security • AI Defense • Pentesting • DevSecOps
Secure the signal. Defend the spectrum.
    </pre>
  </div>

  <!-- Contact + buttons – one tight row -->
  <div style="display: flex; justify-content: center; align-items: center; gap: 2.8rem; flex-wrap: wrap; margin-top: 1.5rem; font-size: 1.15rem;">
    <span style="color: var(--text-muted);">+216 97 322 007</span>
    <a href="mailto:asmaneji20@gmail.com" style="color: var(--accent); text-decoration: none;">asmaneji20@gmail.com</a>
    <span style="color: var(--text-muted);">Tunis, Tunisia</span>
  </div>

  <div style="display: flex; justify-content: center; gap: 1.8rem; flex-wrap: wrap; margin-top: 2.2rem;">
    <a href="https://linkedin.com/in/asma-neji" 
       style="display: flex; align-items: center; gap: 0.6rem; color: #fff; background: var(--accent); padding: 0.8rem 1.8rem; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 1.05rem; transition: all 0.3s;">
      <span>↗</span> LinkedIn
    </a>
    <a href="https://github.com/Asma812" 
       style="display: flex; align-items: center; gap: 0.6rem; color: #fff; background: #171515; padding: 0.8rem 1.8rem; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 1.05rem; transition: all 0.3s;">
      <span>🐙</span> GitHub
    </a>
    <a href="/assets/cv/AsmaNEJI_CV.pdf" 
       style="display: flex; align-items: center; gap: 0.6rem; color: #fff; background: var(--green); padding: 0.8rem 1.8rem; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 1.05rem; transition: all 0.3s;">
      <span>📄</span> Download CV
    </a>
  </div>
</div>

<!-- Latest Articles -->
<h2 style="text-align: center; color: var(--accent); font-family: 'JetBrains Mono', monospace; margin: 5rem 0 3rem;">Latest Articles</h2>

{% for post in site.posts limit:5 %}
<div class="card" style="margin: 2rem 0;">
  <h3 style="margin: 0; color: var(--accent);">
    <a href="{{ post.url }}" style="text-decoration: none;">{{ post.title }}</a>
  </h3>
  <p style="color: var(--text-muted); font-size: 1rem; margin: 0.8rem 0;">
    {{ post.date | date: "%B %d, %Y" }} • {{ post.categories | join: " • " }}
  </p>
  <p style="margin: 1.2rem 0 0; color: var(--text);">
    {{ post.excerpt | strip_html | truncate: 180 }}
  </p>
</div>
{% endfor %}

<div style="text-align: center; margin: 4rem 0;">
  <a href="/blog" style="color: var(--accent); font-size: 1.4rem; font-weight: 600; text-decoration: none;">
    View All Articles →
  </a>
</div>

<!-- Featured Projects -->
<h2 style="text-align: center; color: var(--accent); font-family: 'JetBrains Mono', monospace; margin: 6rem 0 3rem;">Featured Projects</h2>

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(340px, 1fr)); gap: 2.5rem; margin: 0 0 5rem;">
  <div class="card">
    <h3 style="color: var(--red); margin-top: 0;">Cyber Threat Intelligence Platform</h3>
    <p style="color: var(--text-muted);">Neo4j knowledge graph • ML anomaly detection • MITRE ATT&CK • Dash/Flask • Docker</p>
    <a href="/about/#professional-experience" style="color: var(--red); font-weight: 600;">View Details →</a>
  </div>
  <div class="card">
    <h3 style="color: var(--green); margin-top: 0;">DevSecOps Pipeline & XDR</h3>
    <p style="color: var(--text-muted);">Jenkins • SonarQube • OWASP ZAP • Wazuh • TheHive • OpenCTI</p>
    <a href="/about/#professional-experience" style="color: var(--green); font-weight: 600;">View Details →</a>
  </div>
  <div class="card">
    <h3 style="color: var(--purple); margin-top: 0;">Virtualized 5G Network Optimization</h3>
    <p style="color: var(--text-muted);">SDN • NFV • AI • Blockchain • OpenDaylight • Open5GS • TensorFlow</p>
    <a href="/about/#academic-projects" style="color: var(--purple); font-weight: 600;">View Details →</a>
  </div>
</div>

<div style="text-align: center; margin: 5rem 0;">
  <a href="/about" style="color: var(--accent); font-size: 1.5rem; font-weight: 600; text-decoration: none;">
    See Full Portfolio →
  </a>
</div>

<!-- Telecom & Contact -->
<div style="text-align: center; margin: 6rem 0;">
  <p style="font-size: 1.3rem; color: var(--text-muted);">
    Explore my academic journey in telecom engineering:<br>
    <a href="/telecom" style="color: var(--accent); font-weight: 600;">Telecom Lessons →</a>
  </p>
  <p style="font-size: 1.4rem; margin-top: 3rem;">
    <a href="/contact" style="color: var(--accent); font-weight: 600;">Get in touch</a>
  </p>
</div>

</div>
