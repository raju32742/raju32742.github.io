---
layout: homepage
---

<h1 id="about-me"></h1>
<h2 style="margin: 60px 0px 10px;">About Me</h2>

<p style="text-align: justify;">
I hold a MASc in Electrical and Computer Engineering (ECE) from the <a href="https://uwaterloo.ca/">University of Waterloo</a>, specializing in <a href="https://uwaterloo.ca/centre-pattern-analysis-machine-intelligence/">Pattern Analysis and Machine Intelligence</a>, where I was advised by <a href="https://uwaterloo.ca/scholar/karray">Prof. Fakhri Karray</a>. My MASc research focuses on <strong>AI methods</strong> for <strong>digital pathology</strong>, emphasizing <strong>classification</strong> and <strong>caption generation</strong> from microscopic <strong>whole slide images (WSIs)</strong>. I am on study leave from <a href="https://www.kuet.ac.bd/">Khulna University of Engineering & Technology (KUET)</a>, where I serve as a <a href="https://www.kuet.ac.bd/cse/raju_taslim">Lecturer</a> in the Department of <a href="https://www.kuet.ac.bd/dept/cse">Computer Science and Engineering (CSE)</a>.
</p>

<p style="text-align: justify;">
  I completed both my Bachelor of Science (B.Sc.) and Master of Science (M.Sc.) in CSE from <a href="https://www.kuet.ac.bd" target="_blank" rel="noopener noreferrer">KUET</a>. Under the supervision of <a href="https://scholar.google.com/citations?user=zLdETScAAAAJ&hl=en">Prof. M.M.A Hashem</a>, my master's research focused on non-invasive estimation of <strong>hemoglobin</strong> and <strong>glucose</strong> levels using <strong>smartphone-based PPG signals</strong>, establishing a strong foundation in <strong>signal processing</strong> and <strong>deep learning for physiological measurement</strong>.
</p>

<!-- My research lies at the intersection of **privacy compliance** and **formal verification** -- with a special focus on building privacy-secured systems that satisfies system specification requirement. My research interests include **privacy compliance**, **formal verification**, **security**, and **large language models**.
<!-- , **3D geometry models**, and **medical imaging**. -->

<!-- Previously, I successfully completed my graduate studies in Computer Science at the [University of New Brunswick](https://unb.ca/), Canada. During my time pursuing my graduate studies, I served as a Graduate Research Assistant at the [Canadian Institute of Cybersecurity](https://www.unb.ca/cic/). My research interests spanned the Internet of Things (IoT), Anomaly Detection, and Security under the supevision of Professor [Ali Ghorbani](https://www.cs.unb.ca/people/ghorbani). My biography is [here](./biography/).
 --> 

<!-- <strong style="color:#e74d3c; font-weight:600"><strong style="color:#e74d3c; font-weight:600">I am currently looking for summer 2025 internship positions which I hope will help hone my skills and attain industry experience. You can find my resume  [here](./assets/resume_summarized_2025.pdf).</strong> --> 


<div class="call-to-action">
  <h2 style="color: #e74d3c; font-weight: 600; margin-bottom: 10px;">
    Looking for Summer 2025 Internship!
  </h2>
  <p style="font-size: 16px; color: #555; margin-bottom: 20px;">
I am currently seeking PhD opportunities in Computer Science for Fall 2026, with a focus on advancing my research in AI and healthcare.
  </p>
   <a href="./assets/resume_summarized_2025.pdf" download class="resume-button">
    Download My Resume
  </a> 
  <a href="./assets/cv.pdf" download class="resume-button">
      View Research Summary
  </a>
</div>

<!-- <div class="call-to-action">
  <h2 style="color: #e74d3c; font-weight: 600; margin-bottom: 10px;">
    Looking for Summer 2025 Internship!
  </h2>
  <p style="font-size: 16px; color: #555; margin-bottom: 20px;">
    I am currently looking for summer 2025 internship positions which I hope will help hone my skills and attain industry experience.
  </p>
    <div class="button-container">
    <a href="./assets/cv.pdf" target="_blank" class="resume-button">
      View My Resume
    </a>
    <a href="./assets/research_summary.pdf" target="_blank" class="resume-button">
      View Research Summary
    </a>
  </div>
</div> -->

{% include_relative _includes/research.md %}

{% include_relative _includes/news.md %}

{% include_relative _includes/contact.md %}

<style>
@keyframes blink {
  0% { opacity: 1; }
  50% { opacity: 0; }
  100% { opacity: 1; }
}

.blinking-text {
  animation: blink 1.5s infinite;
}

.resume-button {
  display: inline-block;
  padding: 10px 20px;
  font-size: 16px;
  font-weight: 600;
  color: #fff;
  background-color: #0b192f;
  border-radius: 5px;
  text-decoration: none;
  transition: background-color 0.3s ease;
}

.resume-button:hover {
  background-color: #64ffda;
}

.call-to-action {
  background-color: #f8f9fa;
  padding: 20px;
  text-align: center;
  border-radius: 10px;
  margin: 30px 0;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.call-to-action:hover {
  transform: scale(1.02);
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
}
</style>
