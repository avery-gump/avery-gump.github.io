---
layout: archive
title: ""
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

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
*May 2025 - Current* * Developing solutions for flash SP-LiDAR to enable autonomous driving robust to critical, long tail, failure modes. 
* Modeled SP-LiDAR glare as a linear inverse problem and correcting artifacts via a training-free inversion process in the raw transient histogram domain. 
* Helping to design a SP-LiDAR simulator, VISIONSIM, that models phyiscal sensor non-idealities. 
* Currently working on quantifying LiDAR uncertainty in poor weather conditions.

### **Intern (Contractor for USRA)** | Air Force Research Laboratories (Rome, NY) 
*Jun 2023 - Aug 2023* * Developed a novel hierarchical active sampling method utilizing a self-supervised approach. 
* Looked into how self-supervised approaches can improve active learning through the inference of identifiable clusters. 

### **Undergraduate Research Assistant** | Syracuse University 
*May 2022 - Aug 2022* * Developed a Python web scraper to harvest and automate the downloading of Alexa audio files by inspecting network traffic. 
* Created a synchronous recording and playback program for separate audio files across multiple sound devices. 

Teaching Experience
======

### **Teaching Assistant (Data Science Programming in Python II)** | UW Madison 
*Jan 2025 - May 2025* * Led lab sessions, facilitated programming practice, and provided one-on-one student mentoring under Dr. Gurmail Singh. 

### **Teaching Assistant (Discrete Mathematics)** | UW Madison 
*Sep 2024 - Dec 2024* * Co-led discussion sections, graded assignments, mentored students during office hours, and managed Piazza under Dr. Beck Hasti. 

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
  {% assign sorted_pubs = site.publications | sort: 'date' | reverse %}
  {% for pub in sorted_pubs %}
    {% if pub.citation_key and site.data.citations[pub.citation_key] %}
      {% assign cite_data = site.data.citations[pub.citation_key] %}
      {% assign venue = cite_data.journal | default: cite_data.booktitle %}
      
      <p style="margin-bottom: 15px; line-height: 1.5;">
        {{ cite_data.authors | replace: 'Gump, Avery', '<strong>Gump, Avery</strong>' }}. ({{ cite_data.year }}). <a href="{{ pub.url | relative_url }}">"{{ pub.title | default: cite_data.title }}."</a> <i>{{ venue }}</i>{% if cite_data.volume %}, {{ cite_data.volume }}{% endif %}{% if cite_data.issue %}({{ cite_data.issue }}){% endif %}{% if cite_data.pages %}, {{ cite_data.pages | replace: '--', '-' }}{% endif %}.
      </p>
    {% endif %}
  {% endfor %}
</div>