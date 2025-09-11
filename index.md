---
layout: default
title: Christian Galvez - Cyber Portfolio
---

<nav class="navbar">
  <ul>
    <li><a href="./index.md">🏠 Home</a></li>
    <li><a href="./projects.md">💻 Projects</a></li>
    <li><a href="./writeups.md">📝 Writeups</a></li>
    <li><a href="./labs.md">🔨 Labs</a></li>
  </ul>
</nav>

---

# 👋 Hello, I'm Christian Galvez

Certified and aspiring cybersecurity professional with a foundation in technical support, security documentation, and vulnerability analysis. This portfolio showcases my hands-on skills and knowledge in cybersecurity operations, cloud platforms, and secure system design.

- **Location**: Egg Harbor, NJ
- **Certifications**: Security+, Network+, A+, ITIL v4, AZ-900, ISC2 CC
- **Degree**: B.S. in Cybersecurity (in progress, WGU)
- [Download Resume](assets/Resume.pdf)

---

## 🌟 Featured Projects  

<div class="project-grid">

  <div class="project-card">
    <a href="writeups/honeypot-project.md" class="thumbnail-link">
      <div class="thumbnail-container">
        <img src="assets/honeypot-thumbnail.png" alt="Cowrie Honeypot Screenshot" class="thumbnail">
        <img src="assets/terminal.png" alt="Terminal Icon" class="icon-overlay">
      </div>
    </a>
    <h3>🔒 Cowrie SSH Honeypot</h3>
    <p>Tracked real-world unauthorized login attempts and learned to troubleshoot Python environments, system paths, and log analysis.</p>
  </div>

  <div class="project-card">
    <a href="writeups/vpn-project.md" class="thumbnail-link">
      <div class="thumbnail-container">
        <img src="assets/Wireguard-thumbnail.png" alt="WireGuard VPN Screenshot" class="thumbnail">
        <img src="assets/shield.png" alt="Lock Icon" class="icon-overlay">
      </div>
    </a>
    <h3>🔐 WireGuard VPN with Firewall Hardening</h3>
    <p>Configured a secure VPN on a cloud server, with added firewall rules for resilience against brute force and scanning attempts.</p>
  </div>

</div>
.project-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 24px;
  margin-top: 20px;
}

.project-card {
  text-align: center;
}

.thumbnail-container {
  position: relative;
  display: inline-block;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.thumbnail-container:hover {
  transform: translateY(-4px);
  box-shadow: 0 6px 12px rgba(0,0,0,0.2);
}

.thumbnail {
  width: 100%;
  border-radius: 12px;
}

.icon-overlay {
  position: absolute;
  top: 15px;
  right: 15px;
  width: 40px;
  height: auto;
  background: white;
  border-radius: 50%;
  padding: 6px;
  box-shadow: 0 2px 6px rgba(0,0,0,0.25);
}

---

Explore my work:
- [Projects](projects.md)
- [Labs](labs.md)
- [Writeups](writeups.md)
