
<style>
.btn.btn-primary {
  background-color: #1976d2;   /* Brighter blue */
  color: #fff;
  border: none;
  font-weight: 600;
  font-size: 13px;
  padding: 6px 17px;
  border-radius: 6px;
  transition: background 0.18s, box-shadow 0.15s;
  box-shadow: 0 2px 7px rgba(25, 118, 210, 0.13);
  text-decoration: none;
  display: inline-block;
  margin-right: 0px; /* optional, for spacing if not using flex gap */
}
.btn.btn-primary:hover {
  background-color: #1565c0;
  color: #fff;
  box-shadow: 0 4px 16px rgba(25, 118, 210, 0.22);
  text-decoration: none;
}
</style>


<h1 style=" text-align: justify; margin: 60px 0px 10px; color:#1a237e;">A Study on Non-Invasive Hemoglobin Measurement Techniques</h1>




<div style="display: flex; gap: 10px; margin: 18px 0 24px 0; justify-content: flex-start;">
{% assign projects = site.data.projects.main | where: "category", "bsc_thesis" %}
{% assign project = projects[0] %}
  {% if project.pdf %}
    <a href="{{ project.pdf }}" class="btn btn-primary" target="_blank" style="font-size:13px; font-weight:600; padding:6px 17px; border-radius:6px;">PDF</a>
  {% endif %}
  {% if project.slide %}
    <a href="{{ project.slide }}" class="btn btn-primary" target="_blank" style="font-size:13px; font-weight:600; padding:6px 17px; border-radius:6px;">Slide</a>
  {% endif %}
  {% if project.code %}
    <a href="{{ project.code }}" class="btn btn-primary" target="_blank" style="font-size:13px; font-weight:600; padding:6px 17px; border-radius:6px;">Code</a>
  {% endif %}
  <!-- {% if project.video %}
    <a href="{{ project.video }}" class="btn btn-primary" target="_blank" style="font-size:13px; font-weight:600; padding:6px 17px; border-radius:6px;">Video</a>
  {% endif %} -->
</div>


<!-- Add your figure image here if available -->
<p style="text-align:center;">
  <img src="/assets/img/bsc/system.png" alt="Overall Functional Block Diagram of Proposed Method" style="max-width: 600px; width: 100%; border-radius: 9px; margin: 18px 0; box-shadow: 0 4px 16px rgba(0,0,0,0.08);">
</p>
<p style="text-align:center; margin-top: -30px">
  <b><i>Figure: An overview of non-invasive blood component hemoglobin (Hb) measurement technique.</i></b>
</p>

<!-- Introduction / Background --> 
<h2 style="color:#2637a1; margin-top: 30px">1. Background</h2> 
<p style="text-align: justify; margin-top: -10px"> 
Anemia is a critical public health issue worldwide, especially in developing countries, due to the high prevalence of iron deficiency. Hemoglobin (Hb) concentration is a standard marker for diagnosing anemia, but traditional measurement methods are invasive, requiring blood draws, laboratory processing, and specialized personnel. These procedures are often painful, costly, and inaccessible for routine or large-scale screening—particularly in resource-limited settings. To address these challenges, researchers are increasingly turning toward non-invasive technologies, especially those based on optical principles such as near-infrared spectroscopy (NIRS) and photoplethysmography (PPG) [1–3]. These techniques allow hemoglobin estimation by analyzing the absorption and reflection of light through tissue, offering painless, rapid, and cost-effective alternatives [4–6]. Smartphones and custom-built LED devices now make it feasible to collect fingertip video data for PPG signal extraction, laying the groundwork for portable and accessible hemoglobin monitoring solutions [7–8]. </p>


<!-- Motivation --> 
<h2 style="color:#2637a1; margin-top: 30px">2. Motivation</h2> 
<p style="text-align: justify; margin-top: -10px"> Conventional hemoglobin testing methods are limited by their invasiveness and logistical demands. The need for simple, reliable, and noninvasive alternatives is underscored by the global burden of anemia and the growing focus on patient-centric, at-home health monitoring [1]. Recent advances in optical sensing, combined with the ubiquity of smartphones, have opened new possibilities for real-time, pain-free Hb estimation [5–8]. By leveraging PPG signals captured via consumer devices and applying advanced machine learning techniques [9–10], noninvasive hemoglobin monitoring can be democratized—making frequent self-assessment feasible for at-risk populations. The motivation behind this work is to develop and validate a low-cost, user-friendly solution that minimizes discomfort and barriers to care, supporting early diagnosis and management of anemia in both clinical and remote settings [1,11]. </p> 

<!-- Objectives --> 
<h2 style="color:#2637a1; margin-top: 30px">3. Objectives</h2> 
<p style="text-align: justify; margin-top: -10px"> 
The core objectives of this thesis are to: 
<ul>
<li>Review and compare existing non-invasive hemoglobin measurement technologies </li> 
<li>Design and develop a near-infrared (NIR) LED-based data collection board and a companion Android application for fingertip video capture</li> 
<li>Acquire a multimodal dataset, including fingertip videos and reference blood test results, from a diverse participant cohort.</li> <li>Extract and analyze optimal PPG features from recorded videos using advanced signal processing techniques</li> 
<li>Implement and evaluate several machine learning and deep learning models (e.g., LR, SVR, MLPR, DNN) for noninvasive Hb estimation</li>
</ul> </p> 

<!-- Methodology --> 
<h2 style="color:#2637a1; margin-top: 36px;">4. Methodology</h2> 
<h3 style="color:#1a237e; margin-top:28px;">4.1 System Overview</h3> 
<p style="text-align: justify; margin-top: -10px"> The system integrates a custom NIR-LED board with a smartphone camera to acquire fingertip videos under various lighting conditions [7]. The board is user-friendly, portable, and features multiple NIR LEDs to enhance signal quality. </p> 

<h3 style="color:#1a237e; margin-top:22px;">4.2 Data Collection Process</h3> 
<p style="text-align: justify; margin-top: -10px"> 
Fingertip videos were collected from subjects (aged 15–65, various genders) under three scenarios: (1) smartphone with built-in flash, (2) smartphone with NIR-LED board (no flash), and (3) reference blood sample collection. Each video was 10+ seconds (600 frames at 60 fps), with the index finger positioned on the illuminated board [8]. </p> 

<!-- Add your figure image here if available --> 
 <p style="text-align:center;"> <img src="/assets/img/bsc/Data_collection.png" alt="Overall Functional Block Diagram of Proposed Method" style="max-width: 500px; width: 100%; border-radius: 9px; margin: 18px 0; box-shadow: 0 4px 16px rgba(0,0,0,0.08);"> </p> <p style="text-align:center; margin-top: -30px"> <b><i>Figure: Video Data Collection Kit with LED-Board.</i></b> </p> 

<h3 style="color:#1a237e; margin-top:22px;">4.3 Video Processing & Signal Extraction</h3> 
<p style="text-align: justify; margin-top: -10px"> For each video, the central 500x500 pixel region was extracted from every frame, and the mean red channel intensity was computed to generate the raw PPG signal [4]. A fourth-order Butterworth bandpass filter was applied to suppress noise and motion artefacts [9]. The three highest-quality PPG waveforms (with prominent systolic peaks) were selected for further analysis. </p> 

<h3 style="color:#1a237e; margin-top:22px;">4.4 Feature Engineering & Selection</h3>
 <p style="text-align: justify; margin-top: -10px"> Comprehensive feature extraction was performed on each PPG cycle, including analysis of the original signal, its first and second derivatives, and frequency-domain characteristics [4,9]. Feature selection leveraged genetic algorithms to optimize the subset for model input, reducing redundancy and overfitting [10,11]. </p>
 
<h3 style="color:#1a237e; margin-top:22px;">4.5 Model Development & Validation</h3> <p style="text-align: justify; margin-top: -10px"> Multiple regression models (Linear Regression, Support Vector Regression, Multilayer Perceptron Regression, Deep Neural Networks) were trained using the selected features. K-fold (K=10) cross-validation was used for robust performance evaluation [10]. 



<!-- References --> 
<h2 style="color:#2637a1; margin-top: 36px;">References</h2> 
<ol style="margin-left:0; text-align: justify; padding-left:1.2em;"> <li>N. J. Kassebaum et al., “A systematic analysis of global anemia burden from 1990 to 2010,” <i>Blood</i>, vol. 123, no. 5, pp. 615–624, 2014.</li> <li>M. W. Wukitsch et al., “Pulse oximetry: analysis of theory, technology, and practice,” <i>J. Clin. Monit.</i>, vol. 4, no. 4, pp. 290–301, 1988.</li> <li>K. König, “Multiphoton microscopy in life sciences,” <i>J. Microscopy</i>, vol. 200, no. 2, pp. 83–104, 2000.</li> <li>J. Allen, “Photoplethysmography and its application in clinical physiological measurement,” <i>Physiol. Meas.</i>, vol. 28, no. 3, p. R1, 2007.</li> <li>E. J. Wang et al., “HemaApp: noninvasive blood screening of hemoglobin using smartphone cameras,” in <i>Proc. 2016 ACM Int. Joint Conf. Pervasive Ubiquitous Comput.</i>, pp. 593–604, 2016.</li> <li>M. K. Hasan et al., “SmartHeLP: Smartphone-based hemoglobin level prediction using an artificial neural network,” <i>AMIA Annu. Symp. Proc.</i>, vol. 2018, p. 535, 2018.</li> <li>X. Zhang et al., “Non-invasive blood glucose estimation using smartphone PPG signals and subspace KNN classifier,” <i>Elektrotehniski Vestnik</i>, vol. 86, no. 1/2, pp. 68–74, 2019.</li> <li>D. Basak et al., “Support vector regression,” <i>Neural Inf. Process. Lett. Rev.</i>, vol. 11, no. 10, pp. 203–224, 2007.</li> <li>J. Koza, “Genetic programming as a means for programming computers by natural selection,” <i>Stat. Comput.</i>, vol. 4, no. 2, pp. 87–112, 1994.</li> <li>M. Rezwanul Haque et al., “Performance evaluation of random forests and artificial neural networks for the classification of liver disorder,” in <i>IC4ME2</i>, pp. 1–5, IEEE, 2018.</li> <li>J. M. Bland and D. G. Altman, “Statistical methods for assessing agreement between two methods of clinical measurement,” <i>The Lancet</i>, vol. 327, no. 8476, pp. 307–310, 1986.</li> <li>D. N. Reshef, Y. A. Reshef, H. K. Finucane, S. R. Grossman, G. McVean, P. J. Turnbaugh, E. S. Lander, M. Mitzenmacher, and P. C. Sabeti, “Detecting novel associations in large data sets,” <i>Science</i>, vol. 334, no. 6062, pp. 1518–1524, 2011.</li> </ol>