---
layout: home
title: Welcome
---

<div class="container" markdown="1">

<!-- HERO SECTION -->
<div style="text-align: center; padding: 5rem 1rem 4rem; max-width: 1000px; margin: 0 auto;">
  <h1 style="font-family: 'JetBrains Mono', monospace; font-size: 3.6rem; margin: 0 0 0.8rem; color: var(--text);">
    Asma NEJI
  </h1>
  <p style="font-size: 1.8rem; margin: 0 0 1.2rem; color: var(--accent); font-weight: 600;">
    Junior Cybersecurity Engineer
  </p>

  <!-- Cybersecurity trick: short nmap-style self-scan -->
  <div style="margin: 2rem auto; max-width: 800px;">
    <pre style="background: #0a0e14; color: #00b894; font-family: 'JetBrains Mono', monospace; padding: 1.4rem; border-radius: 10px; border: 1px solid #21262d; font-size: 1rem; line-height: 1.5; text-align: left; overflow-x: auto;">
Nmap scan report for asma.neji (localhost)
Host is up (0.00008s latency)
PORT   STATE SERVICE
22/tcp open  ssh
80/tcp open  http
443/tcp open  https

OS details: Linux 5.x|6.x (Ubuntu/Debian)
Device type: general purpose
Running: Linux 5.X|6.X
OS CPE: cpe:/o:linux:linux_kernel

root@asma:~# echo "Threat Intelligence | Telecom Security | AI Defense | Pentesting | DevSecOps"
root@asma:~# echo "Secure the signal. Defend the spectrum."
    </pre>
  </div>

  <!-- Contact + links – one clean row -->
  <div style="display: flex; justify-content: center; align-items: center; gap: 2.5rem; flex-wrap: wrap; margin: 2rem 0; font-size: 1.15rem;">
    <span style="color: var(--text-muted);">+216 97 322 007</span>
    <a href="mailto:asmaneji20@gmail.com" style="color: var(--accent); text-decoration: none;">asmaneji20@gmail.com</a>
    <span style="color: var(--text-muted);">Tunis, Tunisia</span>
  </div>

  <div style="display: flex; justify-content: center; gap: 2rem; flex-wrap: wrap; margin-top: 2.5rem;">
    <a href="https://linkedin.com/in/asma-neji" 
       style="color: #fff; background: var(--accent); padding: 0.9rem 2.2rem; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 1.1rem; transition: all 0.3s;">
      LinkedIn
    </a>
    <a href="https://github.com/Asma812" 
       style="color: #fff; background: #171515; padding: 0.9rem 2.2rem; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 1.1rem; transition: all 0.3s;">
      GitHub
    </a>
    <a href="/assets/cv/AsmaNEJI_CV.pdf" 
       style="color: #fff; background: var(--green); padding: 0.9rem 2.2rem; border-radius: 8px; text-decoration: none; font-weight: 600; font-size: 1.1rem; transition: all 0.3s;">
      Download CV
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
