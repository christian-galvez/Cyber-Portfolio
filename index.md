---
{% include header.html %}
layout: default
title: Christian Galvez - Cyber Portfolio

---

# 👋 Hello, I'm Christian Galvez

Certified and aspiring cybersecurity professional with a foundation in technical support, security documentation, and vulnerability analysis. This portfolio showcases my hands-on skills and knowledge in cybersecurity operations, cloud platforms, and secure system design.

- **Location**: Egg Harbor, NJ
- **Certifications**: Security+, Network+, A+, ITIL v4, AZ-900, ISC2 CC
- **Degree**: B.S. in Cybersecurity (in progress, WGU)
- [Download Resume](assets/Resume.pdf)

---

## 🌟 Featured Projects  

<body>
  <div class="project-grid">
    <div class="project-card">
      <a href="writeups/honeypot-project.html">
        <div class="thumbnail-wrapper">
          <img src="assets/honeypot-thumbnail.png" alt="Honeypot Project" class="thumbnail">
          <img src="assets/shield.png" alt="Project Icon" class="icon">
        </div>
        <p>Honeypot Project</p>
      </a>
    </div>

   <div class="project-card">
      <a href="writeups/vpn-project.html">
        <div class="thumbnail-wrapper">
          <img src="assets/Wireguard-thumbnail.png" alt="Other Project" class="thumbnail">
          <img src="assets/terminal.png" alt="Project Icon" class="icon">
        </div>
        <p>Wireguard VPN Project</p>
      </a>
    </div>
  </div>
</body>
<head>
  <meta charset="UTF-8">
  <title>My Portfolio</title>
  <style>

  .project-grid {
  display: flex;
  gap: 20px;
  justify-content: center;
  align-items: stretch; /* ensures all cards have same height */
  margin-top: 20px;
}

.project-card {
  position: relative;
  width: 250px;
  text-align: center;
  display: flex;
  flex-direction: column; /* stack thumbnail + caption */
  justify-content: space-between; /* keeps spacing even */
}

.thumbnail-wrapper {
  position: relative;
  width: 100%;
  flex-grow: 1; /* allows thumbnails to fill same height */
}

.thumbnail {
  width: 100%;
  display: block;
  border-radius: 8px;
  height: 200px; /* force all thumbnails same height */
  object-fit: cover; /* maintains aspect ratio without stretching */
}

.icon {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 60px;
  height: 60px;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.thumbnail-wrapper:hover .icon {
  opacity: 1;
  cursor: pointer;
}

.project-card p {
  margin-top: 10px;
  font-weight: bold;
}

  </style>
</head>


---

Explore my work:
- [Projects](projects.md)
- [Labs](labs.md)
- [Writeups](writeups.md)
