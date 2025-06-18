
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



<h1 style=" text-align: justify; margin: 60px 0px 10px; color:#1a237e;">A Study on Hemoglobin and Glucose Levels Estimation Techniques Using Optimal PPG Characteristic Features of Smartphone Videos</h1>


<div style="display: flex; gap: 10px; margin: 18px 0 24px 0; justify-content: flex-start;">
{% assign projects = site.data.projects.main | where: "category", "ms_thesis" %}
{% assign project = projects[1] %}
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
  <img src="/assets/img/msc/systemov.jpg" alt="Overall Functional Block Diagram of Proposed Method" style="max-width: 600px; width: 100%; border-radius: 9px; margin: 18px 0; box-shadow: 0 4px 16px rgba(0,0,0,0.08);">
</p>
<p style="text-align:center; margin-top: -30px">
  <b><i>Figure: An overview of non-invasive blood component (Hb and Gl) measurement technique.</i></b>
</p>


<!-- Introduction / Background -->
<h2 style="color:#2637a1; margin-top: 30px">1. Background</h2>
<p style="text-align: justify; margin-top: -10px">
Blood is a vital component of the human body, and hemoglobin (Hb) and glucose (Gl) are two key components. A number of biological activities are done with blood. Excess glucose in the blood indicates the possibility of diabetes, which is the most common chronic metabolic disorder and a leading cause of death worldwide [1]. Similarly, hemoglobin is the protein molecule in red blood cells, and a low hemoglobin count causes anemia [2]. Therefore, measuring blood component levels regularly is imperative for evaluating one’s medical condition. Measurement techniques can be grouped into invasive, minimally invasive, and non-invasive. Conventional (invasive) techniques require a blood sample collected using finger-prick or venepuncture. These methods are painful, time-consuming, and require well-equipped laboratories with trained personnel, which are often unavailable in remote areas. Non-invasive methods are more comfortable, requiring only optical data like photoplethysmogram (PPG) signals or non-optical data like bio-impedance. These newer methods can produce similarly accurate results while being faster and easier to perform.

Currently, near-infrared (NIR) spectroscopy and PPG signals are the most widely used non-invasive techniques for monitoring vital physiological parameters [3]. PPG is an optical technique used to measure changes in blood volume in specific body parts [3]. A typical PPG system includes a light source and photodetector; the light illuminates a tissue region (e.g., finger), and the detector senses reflected light. The amount of absorbed light varies with blood volume, generating the PPG signal. Many studies have explored the use of PPG signals to monitor physiological parameters due to their low cost and simple setup [4-6], such as for anemia detection [5], blood pressure estimation [4], and blood glucose level [6]. PPG signals are typically acquired using optical sensors, chips, or pulse oximeters [4]. Recently, smartphones with built-in sensors have enabled real-time measurement of heart rate and oxygen saturation based on PPG. These non-invasive methods benefit both patients and healthcare professionals. Technological advancements have allowed smartphone cameras to function as sensors. For instance, in 2016, Wang et al. [7] developed HemaApp using Nexus-5p to estimate hemoglobin concentration. In 2017, they used Nexus-6p with upgraded hardware for the same purpose [8]. In 2018, Hasan et al. [9] developed SmartHeLP using Nexus-4p to measure hemoglobin. In 2019, Zhang et al. [10] proposed a smartphone-based non-invasive glucose estimation method using PPG signals. 

<!-- Add your figure image here if available -->
<p style="text-align:center;">
  <img src="/assets/img/msc/blood.JPG" alt="Overall Functional Block Diagram of Proposed Method" style="max-width: 500px; width: 100%; border-radius: 9px; margin: 18px 0; box-shadow: 0 4px 16px rgba(0,0,0,0.08);">
</p>
<p style="text-align:center; margin-top: -30px">
  <b><i>Figure: Photoplethysmography (PPG) principle by smartphone. PPG signal generated from volumetric blood flow changes via light passing through the fingertip, transmitting off of the tissue, and then passing to the smartphone camera’s image sensor.</i></b>
</p>

<!-- Introduction / Background -->
<h2 style="color:#2637a1; margin-top: 30px">2. Motivation</h2>
<p style="text-align: justify; margin-top: -10px">
Photoplethysmogram (PPG) is increasingly used to monitor vital physiological parameters. It is an optical technique that detects blood volume changes using a light source and sensor [22]. Due to its simplicity, low cost, and user-friendly setup, PPG has been applied to estimate hemoglobin [24], heart rate [25], sleep patterns [26], blood pressure [27], and glucose levels [28]. PPG-based near-infrared spectroscopy is especially favored for its accessibility and affordability [29]. Traditionally, PPG signals are acquired via sensors, chips, or pulse oximeters [27, 30–32]. Recently, smartphones with built-in sensors have enabled real-time monitoring of heart rate and oxygen saturation [33]. Technological advances have also allowed smartphone cameras to act as PPG sensors. For example, Devadhasan et al. [34] used a Samsung camera to estimate glucose. Wang et al. [35, 24] developed HemaApp using Nexus-5p and 6p to estimate hemoglobin. Anggraeni et al. [36] used an Asus Zenfone 2 for conjunctiva imaging. Hasan et al. [37] created SmartHeLP on Nexus-4p for Hb estimation. Chowdhury et al. [38] and Zhang et al. [39] developed smartphone-based glucose monitoring systems using PPG.


<h2 style="color:#2637a1; margin-top: 30px">3. Objectives</h2>
<p style="text-align: justify; margin-top: -10px">
The main objective of the research is to develop a smartphone based non-invasive technique for blood components measurement (hemoglobin and glucose). The specific objectives of the research are to-  
<p style="text-align: justify; margin-top: -10px">
<ul>
  <li>study the existing non-invasive methods for blood components measurement.</li>
  <li>collect the fingertip video placing index finger on NIR-LED board through smartphone primary camera.</li>
  <li>generate the PPG signal from the fingertip video and extract optimal PPG characteristic features from the generated PPG signal. </li>
  <li>develop a smartphone-based low cost, noninvasive hemoglobin and glucose levels estimation models using DNN.  </li>
</ul>

<h2 style="color:#2637a1; margin-top: 36px;">4. Methodology</h2>


<h3 style="color:#1a237e; margin-top:28px;">4.1 Dataset Preparation</h3>
<p style="text-align: justify; margin-top: -10px">
Firstly, fingertip videos (.mp4) of different gender as well as ages are collected. At the same time, Hb, and Gl levels are also collected using the clinical method with the help of a nurse. Index finger needed to be clean and dry otherwise, we cannot obtain PPG feature correctly. Placing the index finger on the NIR-LED board and illuminating the finger with light, a 10 seconds video is recorded.
</p>

<!-- Add your figure image here if available -->
<p style="text-align:center;">
  <img src="/assets/img/msc/Hardware.jpg" alt="Overall Functional Block Diagram of Proposed Method" style="max-width: 500px; width: 100%; border-radius: 9px; margin: 18px 0; box-shadow: 0 4px 16px rgba(0,0,0,0.08);">
</p>
<p style="text-align:center; margin-top: -30px">
  <b><i>Figure: Illustration of external data collection kit: (a) Circuit diagram (b) External wearable device.</i></b>
</p>

<!-- Add your figure image here if available -->
<p style="text-align:center;">
  <img src="/assets/img/msc/data_collection.jpg" alt="Overall Functional Block Diagram of Proposed Method" style="max-width: 500px; width: 100%; border-radius: 9px; margin: 18px 0; box-shadow: 0 4px 16px rgba(0,0,0,0.08);">
</p>
<p style="text-align:center; margin-top: -30px">
  <b><i>Figure: Fingertip video data collection kit/device: (A) NIR-LED device with power off, (B) NIR-LED device in turned on condition, (C) Index finger on the device while turned on, and (b) Video recorded with a Nexus-6p smartphone.</i></b>
</p>

<h3 style="color:#1a237e; margin-top:22px;">4.2 PPG Signal Generation</h3>
<p style="text-align: justify; margin-top: -10px">
PPG signal can be obtained by processing the videos. From each video 300 image frame (10 second x 30 fps) is extracted as a first step. The red, green and blue channels are extracted from individual frame of the video. The intensity of the red channel is the highest among the three channels. Therefore, other channels are discarded. The continuous PPG signal is calculated by overall pixel intensity variations in each frame. Eq. 1 calculates the PPG value of the ith frame as the sum of all pixel intensities. <br>
  <script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
  <script id="MathJax-script" async
    src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
  <p>
 $$
\mathrm{PPG}[i] = \frac{1}{\text{total pixels}} \sum_{1}^{\text{total pixels}} \text{intensity} \tag{1}
$$
  </p>
<p>
The raw PPG signal is susceptible to noise and motion artefacts. Therefore, a Butterworth bandpass with a fourth order is applied to remove the high-frequency components.
</p>

<h3 style="color:#1a237e; margin-top:22px;">4.3 Feature Extraction</h3>
<p style="text-align: justify; margin-top: -10px">
PPG signals are continuous and repetitive waveforms that usually contain the same information. A peak detection algorithm is applied to detect each systolic peak. From the continuous PPG waveform, the PPG cycle with the largest positive systolic peak is selected based on its maximum intensity variations. Features are extracted analyzing the selected PPG cycle, its first and second derivative and using fourier analysis.
</p>

<h3 style="color:#1a237e; margin-top:22px;">4.4 Feature Selection</h3>
<p style="text-align: justify; margin-top: -10px">
To discard redundant or irrelevant features before the model construction and to determine the optimum subset of features, feature selection methods should be applied. A maximal information coefficient feature selection technique [12] is proposed which could reduce model overfitting and improve model accuracy.
</p>

<h3 style="color:#1a237e; margin-top:22px;">4.5 Model Construction</h3>
<p style="text-align: justify; margin-top: -10px">
A regression model would be developed using a deep neural network applying optimal features. The proposed models will be validated using K-fold cross-validation. Therefore, the models would be used for the estimation of hemoglobin and glucose levels in the blood.
</p>

<h2 style="color:#2637a1; margin-top: 36px;">Reference</h2>
<ol style="margin-left:0; text-align: justify; padding-left:1.2em;"> <li>J. Li and C. Fernando, “Smartphone-based personalized blood glucose prediction,” <i>ICT Express</i>, vol. 2, no. 4, pp. 150–154, 2016.</li> <li>E. J. Wang, W. Li, J. Zhu, R. Rana, and S. N. Patel, “Noninvasive hemoglobin measurement using unmodified smartphone camera and white flash,” in <i>2017 39th Annual International Conference of the IEEE Engineering in Medicine and Biology Society (EMBC)</i>, pp. 2333–2336, IEEE, 2017.</li> <li>A. Hernando, M. D. Pelaez, M. T. Lozano, M. Aiger, E. Gil, and J. Lázaro, “Finger and forehead ppg signal comparison for respiratory rate estimation based on pulse amplitude variability,” in <i>2017 25th European Signal Processing Conference (EUSIPCO)</i>, pp. 2076–2080, IEEE, 2017.</li> <li>F. Miao, N. Fu, Y.-T. Zhang, X.-R. Ding, X. Hong, Q. He, and Y. Li, “A novel continuous blood pressure estimation approach based on data mining techniques,” <i>IEEE J. Biomed. Health Inform</i>, vol. 21, pp. 1730–1740, 2017.</li> <li>M. A.-u. Golap, S. M. T. U. Raju, M. R. Haque, and M. M. A. Hashem, “Hemoglobin and glucose level estimation from ppg characteristics features of fingertip video using mggp-based model,” <i>Biomedical Signal Processing and Control</i>, vol. 67, p. 102478, 2021.</li> <li>T. T. Chowdhury, T. Mishma, S. Osman, and T. Rahman, “Estimation of blood glucose level of type-2 diabetes patients using smartphone video through pca-da,” in <i>Proceedings of the 6th International Conference on Networking, Systems and Security</i>, pp. 104–108, 2019.</li> <li>E. J. Wang, W. Li, D. Hawkins, T. Gernsheimer, C. Norby-Slycord, and S. N. Patel, “Hemaapp: noninvasive blood screening of hemoglobin using smartphone cameras,” in <i>Proceedings of the 2016 ACM International Joint Conference on Pervasive and Ubiquitous Computing</i>, pp. 593–604, ACM, 2016.</li> <li>E. J. Wang, W. Li, J. Zhu, R. Rana, and S. N. Patel, “Noninvasive hemoglobin measurement using unmodified smartphone camera and white flash,” in <i>2017 39th Annual International Conference of the IEEE Engineering in Medicine and Biology Society (EMBC)</i>, pp. 2333–2336, IEEE, 2017.</li> <li>M. K. Hasan, M. M. Haque, R. Adib, J. F. Tumpa, A. Begum, R. R. Love, Y. L. Kim, and I. A. Sheikh, “Smarthelp: Smartphone-based hemoglobin level prediction using an artificial neural network,” in <i>AMIA Annual Symposium Proceedings</i>, vol. 2018. American Medical Informatics Association, p. 535, 2018.</li> <li>Y. Zhang, Y. Zhang, S. A. Siddiqui, and A. Kos, “Non-invasive blood glucose estimation using smartphone ppg signals and subspace knn classifier,” <i>Elektrotehniski Vestnik</i>, vol. 86, no. 1/2, pp. 68–74, 2019.</li> <li>A. Chatterjee and A. Prinz, “Image analysis on fingertip video to obtain ppg,” <i>Biomedical and Pharmacology Journal</i>, vol. 11, no. 4, pp. 1811–1827, 2018.</li> <li>D. N. Reshef, Y. A. Reshef, H. K. Finucane, S. R. Grossman, G. McVean, P. J. Turnbaugh, E. S. Lander, M. Mitzenmacher, and P. C. Sabeti, “Detecting novel associations in large data sets,” <i>Science</i>, vol. 334, no. 6062, pp. 1518–1524, 2011.</li> </ol>
