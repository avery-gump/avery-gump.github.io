---
layout: archive
title: ""
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

<div id="pdf-only-header">
  <h1 style="margin: 0; font-size: 2.2em; font-weight: 700; color: #111; font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;">Avery Gump</h1>
  <p style="margin: 5px 0 0 0; font-size: 1.05em; color: #555;">
    <a href="https://avery-gump.github.io/">Personal Website</a> 
    &nbsp;&bull;&nbsp; 
    <a href="https://www.linkedin.com/in/avery-gump-794383232/">LinkedIn</a>
  </p>
</div>

Education
======
* **Ph.D. in Computer Sciences**, University of Wisconsin - Madison, Spring 2030 (anticipated) 
  * Advisor: Dr. Mohit Gupta 
  * Research Focus: Single-photon LiDAR sensing and computational imaging. 
* **B.S. in Computer Science and Mathematics (Distinction)**, Syracuse University, Spring 2024 
  * *Summa Cum Laude* (Cumulative GPA: 3.98/4.0) 

Research & Work Experience
======

### **Research Assistant** | UW Madison 
*May 2025 - Current*: Developing solutions for flash SP-LiDAR to enable autonomous driving robust to critical, long tail, failure modes. 
* Modeled SP-LiDAR glare as a linear inverse problem and correcting artifacts via a training-free inversion process in the raw transient histogram domain. 
* Helping to design a SP-LiDAR simulator, VisionSIM, that models phyiscal sensor non-idealities such as glare. 
* Currently working on quantifying LiDAR uncertainty in poor weather conditions.

### **Intern (Contractor for USRA)** | Air Force Research Laboratories (Rome, NY) 
*Jun 2023 - Aug 2023*: Developed a novel hierarchical active sampling method utilizing a self-supervised approach. 
* Looked into how self-supervised approaches can improve active learning through the inference of identifiable clusters. 

### **Undergraduate Research Assistant** | Syracuse University 
*May 2022 - Aug 2022*:  Developed a Python web scraper to harvest and automate the downloading of Alexa audio files by inspecting network traffic. 
* Created a synchronous recording and playback program for separate audio files across multiple sound devices. 

Teaching Experience
======

### **Teaching Assistant (Data Science Programming in Python II)** | UW Madison 
*Jan 2025 - May 2025*: Led lab sessions, facilitated programming practice, and provided one-on-one student mentoring under Dr. Gurmail Singh. 

### **Teaching Assistant (Discrete Mathematics)** | UW Madison 
*Sep 2024 - Dec 2024* Co-led discussion sections, graded assignments, mentored students during office hours, and managed Piazza under Dr. Beck Hasti. 

Skills
======
* **Languages:** C++, Python (Advanced); UNIX, Java, C, SQL, Haskell, R, MATLAB (Proficient) 
* **Frameworks/Tools:** Docker, TensorFlow, scikit-learn, PyTorch, HTCondor, Alchemy 

Honors & Awards
======
* Earl H. DeVoe Prize for Outstanding Undergraduate Research 
* Phi Beta Kappa Inductee (2024) 
* Alpha Sigma Lambda Honor Society Inductee (2020) 

Activities & Service
======
* **Mercile J. Lee Scholarship Program** - Mentor (Sep 2025 - Current) 
* **N+1 Initiative** - Poster Presenter on LiDAR bloom correction (Apr 2025, Apr 2026) 
* **Morgridge Entrepreneurial Bootcamp** - Participant (Jul 2025) 
* **AFRL Poster Session** - Presenter (Aug 2023) 

Publications
======

<div class="cv-publications">
  {% for citation in site.data.citations %}
    {% assign cite_data = citation[1] %}
    {% assign venue = cite_data.journal | default: cite_data.booktitle %}
    
    {% assign raw_authors = cite_data.authors %}
    {% assign author_array = raw_authors | split: " and " %}
    {% assign formatted_authors = "" %}

    {% for author in author_array %}
      {% assign name_parts = author | split: ", " %}
      {% assign last_name = name_parts[0] | strip %}
      
      {% if name_parts.size > 1 %}
        {% assign first_name_raw = name_parts[1] | strip %}
        {% assign first_initial = first_name_raw | slice: 0, 1 | append: "." %}
        {% assign apa_name = last_name | append: ", " | append: first_initial %}
      {% else %}
        {% assign apa_name = last_name %}
      {% endif %}
      
      {% if last_name == "Gump" %}
        {% assign apa_name = "<strong>" | append: apa_name | append: "</strong>" %}
      {% endif %}

      {% if forloop.first %}
        {% assign formatted_authors = apa_name %}
      {% elsif forloop.last %}
        {% if author_array.size > 2 %}
          {% assign formatted_authors = formatted_authors | append: ", & " | append: apa_name %}
        {% else %}
          {% assign formatted_authors = formatted_authors | append: " & " | append: apa_name %}
        {% endif %}
      {% else %}
        {% assign formatted_authors = formatted_authors | append: ", " | append: apa_name %}
      {% endif %}
    {% endfor %}

    <p>
      {{ formatted_authors }} ({{ cite_data.year }}). "{{ cite_data.title }}." <i>{{ venue }}</i>{% if cite_data.volume %}, {{ cite_data.volume }}{% endif %}{% if cite_data.issue %}({{ cite_data.issue }}){% endif %}{% if cite_data.pages %}, {{ cite_data.pages | replace: '--', '-' }}{% endif %}.
    </p>
  {% endfor %}
</div>

<div class="cv-download-btn" style="text-align: center; margin-top: 40px; margin-bottom: 20px;">
  <button onclick="window.print()" style="background: #0078d4; color: white; border: none; padding: 12px 24px; border-radius: 6px; font-size: 1.1em; font-weight: bold; cursor: pointer; box-shadow: 0 4px 6px rgba(0,0,0,0.1);">
    📄 Print / Save as PDF
  </button>
</div>

<style>
  /* Underline ONLY the header text layout tightly */
  h1 {
    display: table !important; 
    border-bottom: 2px solid #e1e4e8 !important;
    padding-bottom: 3px !important;
    margin-top: 22px !important;
    margin-bottom: 12px !important;
  }

  /* Prevent the main name title from getting an underline */
  #pdf-only-header h1 {
    display: block !important;
    border-bottom: none !important;
    margin-top: 0 !important;
    padding-bottom: 0 !important;
    margin-bottom: 0 !important;
  }

  /* Tighter subheadings spacing */
  h3 {
    margin-top: 14px !important;
    margin-bottom: 4px !important;
  }

  /* Compress paragraph and list elements slightly globally */
  p, li {
    line-height: 1.4 !important;
    margin-top: 2px !important;
    margin-bottom: 2px !important;
  }

  /* 
    FORCE SEPARATION FOR PUBLICATIONS:
    This specifically targets the generated paragraphs inside the loops
    and forces the browser to grant them explicit breathing room.
  */
  .cv-publications p {
    margin-top: 0 !important;
    margin-bottom: 22px !important;
    line-height: 1.45 !important;
  }

  ul {
    margin-top: 4px !important;
    margin-bottom: 4px !important;
  }

  /* Hide the custom PDF header on the live website layout */
  #pdf-only-header {
    display: none;
  }

  /* AUTOMATION: Handles margins and strips browser header/footer layout text fields */
  @page {
    size: letter;
    margin: 18mm 20mm 18mm 20mm;
  }

  @media print {
    html, body, #main, .initial-content, .page, .archive, .page__inner-wrap {
      width: 100% !important;
      max-width: 100% !important;
      display: block !important;
      margin: 0 !important;
      padding: 0 !important;
      box-shadow: none !important;
      background: white !important;
    }

    #pdf-only-header {
      display: block !important;
      text-align: center;
      margin-bottom: 20px;
    }

    a {
      color: #0056b3 !important;
      text-decoration: underline !important;
    }

    .masthead, .sidebar, .page__footer, .cv-download-btn, #theme-toggle, .sidebar__right {
      display: none !important;
    }
    
    .cv-publications p, li {
      page-break-inside: avoid;
    }
  }
</style>