---
layout: page
title: Resume
permalink: /resume/
---

<style>
/* Minimal, print-friendly styles scoped to the resume container */
.resume-container {
  max-width: 820px;
  margin: 0 auto;
  padding: 24px;
  line-height: 1.5;
  font-size: 16px;
}
.resume-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 16px;
  flex-wrap: wrap;
  border-bottom: 1px solid #ddd;
  padding-bottom: 12px;
  margin-bottom: 16px;
}
.resume-header h1 {
  margin: 0;
  font-size: 28px;
}
.meta a { text-decoration: none; }
.meta a:hover { text-decoration: underline; }
.section { margin: 18px 0; }
.section h2 {
  font-size: 18px;
  margin: 0 0 6px 0;
  text-transform: uppercase;
  letter-spacing: .02em;
}
.list-compact { margin: 0; padding-left: 20px; }
.badges span {
  display: inline-block;
  padding: 2px 8px;
  border: 1px solid #ccc;
  border-radius: 999px;
  margin: 2px 6px 2px 0;
  font-size: 12px;
}
.util {
  display: flex; justify-content: space-between; align-items: center; gap: 8px;
  margin: 8px 0 16px 0;
}
.print-btn {
  font-size: 14px; border: 1px solid #ccc; padding: 6px 10px; border-radius: 6px;
  background: transparent; cursor: pointer;
}

@media print {
  .util, .print-btn { display: none !important; }
  a[href]:after { content: ""; }
  body { margin: 0; }
  .resume-container { padding: 0; }
}
</style>

<div class="resume-container">
  <div class="util">
    <span>Print or Save as PDF →</span>
    <button class="print-btn" onclick="window.print()">Print</button>
  </div>

  <header class="resume-header">
    <div>
      <h1>Daryl Spink (RON1N01)</h1>
      <div class="meta">
        San Diego, CA · <a href="mailto:youremail@example.com">youremail@example.com</a> ·
        <a href="https://ron1n01.github.io">ron1n01.github.io</a> ·
        <a href="https://github.com/RON1N01">github.com/RON1N01</a> ·
        <a href="https://www.linkedin.com/in/YOUR-LINKEDIN/">LinkedIn</a>
      </div>
    </div>
    <div class="badges">
      <span>Security+ (in progress)</span>
      <span>Red/Blue Team Fundamentals</span>
    </div>
  </header>

  <section class="section">
    <h2>Summary</h2>
    <p>
      Early-career cybersecurity professional focusing on Security+ domains, identity & access management, and practical lab notes. 
      Comfortable on Linux (Kali), CLI tooling, and Git. Building toward red → blue → purple team competencies.
    </p>
  </section>

  <section class="section">
    <h2>Skills</h2>
    <ul class="list-compact">
      <li><strong>Security:</strong> IAM, basic network defense, vuln assessment, SIEM/logging concepts</li>
      <li><strong>Tools:</strong> tcpdump, nmap, Wireshark, iproute2, Git/GitHub, Bash</li>
      <li><strong>OS:</strong> Kali Linux, macOS</li>
      <li><strong>Programming:</strong> Bash; basics of Python; GML</li>
      <li><strong>Other:</strong> High WPM typing, documentation, minimal Jekyll/GitHub Pages</li>
    </ul>
  </section>

  <section class="section">
    <h2>Certifications & Training</h2>
    <ul class="list-compact">
      <li><strong>CompTIA Security+</strong> — in progress (2025)</li>
      <li>Harvard CS50 (edX), fundamentals of computer science (2021)</li>
      <li>TryHackMe — attacking/defending certificate</li>
    </ul>
  </section>

  <section class="section">
    <h2>Experience</h2>
    <p><em>Role / Company</em> — City, ST — YYYY–Present</p>
    <ul class="list-compact">
      <li>Wrote Bash scripts (e.g., batch file renamer) to improve team efficiency.</li>
      <li>Packet capture and analysis practice using <code>tcpdump</code> and Wireshark.</li>
      <li>Documented lab steps and findings; published concise write-ups.</li>
    </ul>
  </section>

  <section class="section">
    <h2>Projects</h2>
    <ul class="list-compact">
      <li><strong>Cybersecurity Blog</strong> — Minimal note-taking site using Jekyll (no-style-please) hosted on GitHub Pages.</li>
      <li><strong>CTF/Lab Notes</strong> — Summaries of network, IAM, and vuln scanning exercises.</li>
      <li><strong>CLI Utilities</strong> — Bash utilities for terminal productivity.</li>
    </ul>
  </section>

  <section class="section">
    <h2>Education</h2>
    <ul class="list-compact">
      <li>Self-directed cybersecurity track; formal coursework via online platforms.</li>
    </ul>
  </section>

  <section class="section">
    <h2>Interests</h2>
    <p>Security engineering, minimal tooling, documentation, and practical defensive tactics.</p>
  </section>
</div>
