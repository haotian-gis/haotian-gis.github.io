---
permalink: /
title: ""
excerpt: ""
author_profile: false
body_class: "terminal-home"
---

<main class="terminal-profile" aria-label="Hao Tian homepage">
  <section class="terminal-profile__identity">
    <img src="/images/haotian.PNG" alt="Hao Tian" class="terminal-profile__avatar">
    <h1>Hao Tian</h1>
    <p>Ph.D. Student, Department of Geography, Texas A&amp;M University</p>
    <p>Urban human dynamics · GeoAI · climate resilience · spatial sensing</p>
  </section>

  <nav class="terminal-profile__nav" aria-label="Homepage sections">
    <button type="button" data-terminal-open="about">About</button>
    <button type="button" data-terminal-open="news">News</button>
    <button type="button" data-terminal-open="research">Research</button>
    <button type="button" data-terminal-open="publications">Publications</button>
    <button type="button" data-terminal-open="service">Service</button>
    <button type="button" data-terminal-open="life">Life</button>
    <a href="/about/">Archive</a>
    <a href="https://scholar.google.com/citations?user=T5zW_C8AAAAJ&hl=zh-CN" target="_blank">Scholar↗</a>
    <a href="mailto:haotian@tamu.edu">Email</a>
  </nav>

  <section class="terminal-window" aria-live="polite">
    <div class="terminal-window__bar">
      <span></span>
      <span></span>
      <span></span>
      <strong id="terminal-title">about.md</strong>
    </div>
    <pre id="terminal-output" tabindex="0"></pre>
  </section>
</main>

<script type="application/json" id="terminal-content">
{
  "about": {
    "title": "about.md",
    "command": "open about",
    "body": [
      "Welcome to my homepage. I am Hao Tian, a Ph.D. student in the Department of Geography at Texas A&M University.",
      "",
      "I am a member of the GIScience for Resilience (GIResilience) Lab, advised by Dr. Heng Cai.",
      "",
      "My work uses mobility traces, ambient seismic noise, distributed acoustic sensing, remote sensing, and GeoAI to understand how cities move, adapt, and recover during environmental and climatic stressors.",
      "",
      "Contact:",
      "- haotian [at] tamu.edu",
      "- College Station, TX, USA"
    ]
  },
  "news": {
    "title": "news.log",
    "command": "open news",
    "body": [
      "2026.03.20  Awarded 2nd Place in the AAG RSSG Student Paper Competition.",
      "2026.03.15  Elected Student Director of the AAG Cyberinfrastructure Specialty Group.",
      "2026.02.11  Received AAG International Geographic Information Fund Student Paper Award.",
      "2025.10.17  Successfully passed my Ph.D. preliminary exam at Texas A&M University."
    ]
  },
  "research": {
    "title": "research_statement.txt",
    "command": "open research",
    "body": [
      "I study urban human dynamics and human-environment interactions through large-scale spatial sensing data.",
      "",
      "Current questions:",
      "- How can mobility, seismic, and remote-sensing data jointly capture disruptions in human activity?",
      "- How do communities adapt unequally to climate stress?",
      "- How can GeoAI translate complex urban signals into actionable resilience and planning insights?",
      "",
      "Keywords:",
      "GeoAI / urban sensing / human mobility / climate resilience / disaster response"
    ]
  },
  "publications": {
    "title": "publications.bib",
    "command": "open publications",
    "body": [
      "- Tian H., Cai H., Chen X., Ghanatghestani A. M., Arthur L. N. B.",
      "  From seismic signals to urban sensing. Computers, Environment and Urban Systems, 2026.",
      "  https://doi.org/10.1016/j.compenvurbsys.2026.102441",
      "",
      "- Tian H., Cai H., Hu L., Qiang Y., Zhou B., Yang M., Lin B.",
      "  Unveiling community adaptations to extreme heat events. Journal of Environmental Management, 2024.",
      "  https://doi.org/10.1016/j.jenvman.2024.121665",
      "",
      "- Zhou B., Zou L., Yang M., Lin B., Mandal D., Abedin J., Cai H., Ji S., Klein A., Tian H.",
      "  Rapid disaster response and damage estimation with social media and pretrained LLMs. AAAG, 2025.",
      "  https://doi.org/10.1080/24694452.2025.2560491",
      "",
      "Full list: /about/#-publications"
    ]
  },
  "service": {
    "title": "service.yaml",
    "command": "open service",
    "body": [
      "academic_service:",
      "  - Student Director, AAG Cyberinfrastructure Specialty Group, 2026-2027",
      "  - Communications Committee, UCGIS, 2026-present",
      "  - Session Chair / Organizer, AAG 2024, AAG 2025, AAG 2026, ICC 2025",
      "",
      "reviewing:",
      "  - Computers, Environment and Urban Systems",
      "  - Journal of Transport Geography",
      "  - Annals of GIS",
      "  - Scientific Reports"
    ]
  },
  "life": {
    "title": "life.txt",
    "command": "open life",
    "body": [
      "Outside of research, I enjoy hiking, swimming, and photography.",
      "",
      "Selected awards:",
      "- AAG RSSG Student Paper Competition, 2nd Place, 2026",
      "- AAG International Geographic Information Fund Student Paper Award, 2026",
      "- International Cartographic Association Scholarship, 2025",
      "- CaGIS International Conference Grant, 2025"
    ]
  }
}
</script>

<script>
(function () {
  var dataNode = document.getElementById('terminal-content');
  var output = document.getElementById('terminal-output');
  var title = document.getElementById('terminal-title');
  var buttons = document.querySelectorAll('[data-terminal-open]');
  if (!dataNode || !output || !title || !buttons.length) return;

  var content = JSON.parse(dataNode.textContent);

  function render(key) {
    var item = content[key] || content.about;
    title.textContent = item.title;
    output.textContent = '> ' + item.command + '\n\n' + item.body.join('\n');
    buttons.forEach(function (button) {
      button.classList.toggle('is-active', button.getAttribute('data-terminal-open') === key);
    });
  }

  buttons.forEach(function (button) {
    button.addEventListener('click', function () {
      render(button.getAttribute('data-terminal-open'));
    });
  });

  render('about');
})();
</script>
