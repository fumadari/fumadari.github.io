---
layout: default
title: [Your Name]
---

<div style="display: flex; align-items: center; margin-bottom: 20px;">
  <img src="assets/images/profile.jpg" alt="Profile Image" style="border-radius: 50%; width: 150px; margin-right: 20px;">
  <div>
    <h1>[Your Name] 👨‍💻</h1>
    <p>Ph.D. Applicant | Solutions Architect @ AWS</p>
    <p><a href="mailto:your.email@example.com"><i class="fas fa-envelope"></i> your.email@example.com</a></p>
    <p><a href="https://linkedin.com/in/your-profile"><i class="fab fa-linkedin"></i> LinkedIn</a> | 
       <a href="https://github.com/your-username"><i class="fab fa-github"></i> GitHub</a></p>
    <p><a href="assets/resume.pdf" download><i class="fas fa-file-pdf"></i> Download CV</a></p>
  </div>
</div>

## About

Hello! I am a Ph.D. Applicant focusing on the intersection of **AI**, **Machine Learning**, and **Mathematics**. Currently, I work as a **Solutions Architect** at [Amazon Web Services (AWS)](https://aws.amazon.com), applying my experience in large-scale distributed systems to cutting-edge AI research.

I earned my **B.S. in Computer Science** from [University Name](https://www.university-website.edu), and I've previously worked on projects with [Company X](https://company-x.com) and contributed to research on [Neural Networks](https://en.wikipedia.org/wiki/Neural_network).

My primary research interests include:
- **LLM Evaluation**: Exploring frameworks to evaluate language models' performance and shortcomings.
- **Weak-to-Strong Generalization**: Training models to generalize effectively across various tasks.

---

## News & Updates
- **October 2024**: Submitted a paper on Neural Network Optimization to [ICML 2025](https://icml.cc/).
- **August 2024**: Started a new project on scalable data architectures at AWS. [Read more](https://github.com/your-username/project-repo).
- **May 2024**: Completed an internship at [Company X](https://company-x.com) focused on distributed AI systems.
- **March 2024**: Gave a talk on AI in distributed systems at [Conference Y](https://conferencey.org).

---

## Vitae

<div class="timeline">
  <div class="timeline-item">
    <span class="date">Aug 2024 - Present</span>
    <h3>Ph.D. in Computer Science</h3>
    <p><strong>Language Technologies Institute, CMU</strong> (Advisors: Graham Neubig and Sean Welleck)</p>
    <p>Working on LLM Evaluation and Weak-to-Strong Generalization.</p>
  </div>

  <div class="timeline-item">
    <span class="date">Mar 2023 - Aug 2024</span>
    <h3>M.S. in Artificial Intelligence</h3>
    <p><strong>KAIST AI</strong> (Advisor: Minjoon Seo)</p>
    <p>Worked on evaluator LM & VLMs, and Chain-of-Thought fine-tuning.</p>
  </div>

  <!-- Add more timeline items as needed -->
</div>

---

## Selected Projects

<div class="project-grid">
  <div class="project-card">
    <h3><a href="https://github.com/your-username/project1">Scalable Clustering for 1M+ Vectors</a></h3>
    <p>Developed a clustering algorithm to improve recall and efficiency in distributed systems.</p>
    <p><a href="https://arxiv.org/abs/your-paper" target="_blank"><i class="fas fa-file-pdf"></i> Read Paper</a> | <a href="https://github.com/your-username/project1"><i class="fab fa-github"></i> View Code</a></p>
  </div>

  <div class="project-card">
    <h3><a href="https://github.com/your-username/project2">Graph Neural Networks for Drug Discovery</a></h3>
    <p>Achieved 91% accuracy in drug molecular analysis using GNN.</p>
    <p><a href="https://arxiv.org/abs/your-paper" target="_blank"><i class="fas fa-file-pdf"></i> Read Paper</a> | <a href="https://github.com/your-username/project2"><i class="fab fa-github"></i> View Code</a></p>
  </div>
</div>

<style>
/* Styling for the timeline */
.timeline {
    position: relative;
    margin: 20px 0;
    padding-left: 40px;
    border-left: 2px solid #0366d6;
}

.timeline-item {
    margin-bottom: 30px;  /* Added space between items */
    position: relative;
}

.timeline-item::before {
    content: "";
    position: absolute;
    left: -9px;
    top: 0;
    width: 16px;
    height: 16px;
    border-radius: 50%;
    background-color: #0366d6;
}

.timeline-item .date {
    color: #666;
    font-size: 0.9rem;  /* Smaller date size */
    margin-bottom: 5px;  /* Space between date and title */
}

.timeline-item h3 {
    font-size: 1.2rem;  /* Larger, bolder title */
    margin-top: 0;
    font-weight: bold;
}

.timeline-item p {
    font-size: 1rem;  /* Slightly larger description font */
    color: #444;
    line-height: 1.6;
}

.timeline-item h3, .timeline-item strong {
    color: #333;  /* Darker title and bold text */
}

/* Styling for projects */
.project-grid {
    display: flex;
    gap: 20px;
}

.project-card {
    border: 1px solid #ddd;
    padding: 15px;
    border-radius: 8px;
    flex: 1;
    transition: box-shadow 0.3s ease;
}

.project-card:hover {
    box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.1);
}
</style>
