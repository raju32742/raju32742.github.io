<style>
.btn.btn-primary {
  background-color: #1976d2;
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
  margin-right: 0px;
}
.btn.btn-primary:hover {
  background-color: #1565c0;
  color: #fff;
  box-shadow: 0 4px 16px rgba(25, 118, 210, 0.22);
  text-decoration: none;
}
</style>

<h1 style="text-align: justify; margin: 60px 0px 10px; color:#1a237e;">Advanced AI for Histopathological Whole Slide Image Classification and Captioning</h1>

<div style="display: flex; gap: 10px; margin: 18px 0 24px 0; justify-content: flex-start;">
{% assign projects = site.data.projects.main | where: "category", "ms_thesis" %}
{% assign project = projects[0] %}
  {% if project.pdf %}
    <a href="{{ project.pdf }}" class="btn btn-primary" target="_blank">PDF</a>
  {% endif %}
  {% if project.slide %}
    <a href="{{ project.slide }}" class="btn btn-primary" target="_blank">Slide</a>
  {% endif %}
  {% if project.code %}
    <a href="{{ project.code }}" class="btn btn-primary" target="_blank">Code</a>
  {% endif %}
  <!-- {% if project.video %}
    <a href="{{ project.video }}" class="btn btn-primary" target="_blank">Video</a>
  {% endif %} -->
</div>

<p style="text-align:center;">
  <img src="/assets/img/msc/Picture1.png" alt="Overall Functional Block Diagram of Proposed Method" style="max-width: 500px; width: 100%; border-radius: 9px; margin: 18px 0; box-shadow: 0 4px 16px rgba(0,0,0,0.08);">
</p>
<p style="text-align:center; margin-top: -30px">
  <b><i>Figure: Digital pathology for image analysis.</i></b>
</p>

<h2 style="color:#2637a1; margin-top: 30px">1. Background</h2>
<p style="text-align: justify; margin-top: -10px">
Histopathology, the microscopic analysis of tissue sections, serves as a cornerstone for diagnosing and characterizing various diseases, particularly cancer [2,3]. The traditional diagnostic workflow involves the manual examination of Hematoxylin and Eosin (H&E)-stained slides by expert pathologists, relying on morphological patterns to guide clinical decisions. Despite its reliability, this manual process is time-intensive, subject to intra- and inter-observer variability, and increasingly burdensome given the rising volume of clinical cases. The emergence of deep learning methods has significantly advanced the field of computational histopathology, allowing for high-throughput and scalable analysis of gigapixel whole slide images (WSIs) [4]. These digital scans, however, pose substantial computational challenges due to their massive resolution and complex tissue structures. Multiple Instance Learning (MIL) has gained popularity for slide-level classification by dividing WSIs into smaller, manageable patches. Yet, standard MIL assumes independence among instances, ignoring spatial and contextual dependencies that are crucial for accurate histopathological assessment [6].
</p>
<p style="text-align: justify;">
Microscopic imaging, while more memory-efficient and cost-effective than WSI scanning, introduces additional complications. Unlike scanned WSIs, microscope-based patches often lack absolute spatial coordinates and contain redundancy due to subjective sampling by the pathologist. These factors hinder the construction of structured inputs for downstream learning, especially in models like ABMIL [6], TransMIL [7], and graph-based MIL approaches [8]. Caption generation from histopathological images presents its own set of challenges. Models relying on Recurrent Neural Networks (RNNs), Long Short-Term Memory (LSTM), or spatial feature grids [10] fail to adequately model the complex and dispersed regions of interest typical in pathology slides [9,11].
</p>


<h2 style="color:#2637a1; margin-top: 30px">2. Motivation</h2>
<p style="text-align: justify; margin-top: -10px">
The ability to automatically generate descriptive captions from WSIs holds immense potential for augmenting diagnostic workflows. Captioning models can help synthesize the visual complexity of pathology images into interpretable textual information, allowing pathologists to quickly identify regions of interest and gain additional context for diagnosis [2,12]. However, the field remains underexplored due to the lack of large, annotated datasets and the inherent complexity of medical images [13]. The growing success of AI-driven diagnostic tools in classification tasks has paved the way for more advanced applications, such as multimodal captioning and interpretability [14,15]. Large Language Models (LLMs), such as LLaMA [16], ClinicalT5 [17], and BioGPT [18], have demonstrated impressive performance in understanding and generating domain-specific text. When combined with Vision Transformers (ViTs) [20], which excel in capturing spatial hierarchies from visual data, these models enable robust multimodal learning pipelines. Such integration facilitates accurate and context-rich caption generation for complex biomedical tasks [21–22]. The proposed research is motivated by this potential and aims to develop hybrid models that effectively leverage both visual and linguistic representations to improve pathological image interpretation and reporting.
</p>


<h2 style="color:#2637a1; margin-top: 30px">3. Objectives</h2>
<ul style="text-align: justify; margin-top: -10px">
  <li>Designed an efficient feature extractor which captures the complex attributes of tissues in histopathological patches</li>
  <li>Employed a clustering method to reduce the redundancy and established the spatial relationship among the patches</li>
  <li>Integrate vision transformers and large language models (LLMs) to enhance interpretability.</li>
  <li>Evaluate performance against state-of-the-art models using benchmark datasets.</li>
</ul>

<h2 style="color:#2637a1; margin-top: 36px;">4. Methodology</h2>

<h3 style="color:#1a237e; margin-top:28px;">4.1 TransUAAE-CapGen</h3>
<p style="text-align: justify; margin-top: -10px">
The TransUAAE-CapGen model comprises a UNet-based Adversarial Autoencoder (AAE) that serves as a feature extractor. It captures both local and global histopathological features through a deep hierarchical architecture. These features are subsequently passed to a Transformer network designed to generate descriptive captions. The Transformer utilizes self-attention mechanisms and positional encodings to effectively model sequential dependencies, producing accurate and clinically relevant textual descriptions.
</p>

<p style="text-align:center;">
  <img src="/assets/img/msc/trans.jpg" alt="Overall Functional Block Diagram of Proposed Method" style="max-width: 600px; width: 100%; border-radius: 9px; margin: 18px 0; box-shadow: 0 4px 16px rgba(0,0,0,0.08);">
</p>
<p style="text-align:center; margin-top: -30px">
  <b><i>Figure: Architecture of our proposed TransUAAE-CapGen model for histopathological caption generation.</i></b>
</p>

<h3 style="color:#1a237e; margin-top:22px;">4.2 GNN-ViTCap</h3>
<p style="text-align: justify; margin-top: -10px">
The GNN-ViTCap architecture integrates advanced modules to overcome redundancy and spatial ambiguity. Initially, histopathological patches undergo feature extraction using a Vision Transformer (ViT), converting image patches into meaningful embeddings. An attention-based deep embedded clustering technique then identifies and selects representative patches, reducing data redundancy. Next, Graph Neural Networks (GNN) are employed to construct relational graphs capturing spatial and contextual information between selected representative patches. Lastly, the aggregated embeddings from the GNN are projected into a language model space, integrating with large language models (LLMs) to perform classification and sophisticated caption generation tasks.
</p>

<p style="text-align:center;">
  <img src="/assets/img/msc/system overview.png" alt="Overall Functional Block Diagram of Proposed Method" style="max-width: 600px; width: 100%; border-radius: 9px; margin: 18px 0; box-shadow: 0 4px 16px rgba(0,0,0,0.08);">
</p>
<p style="text-align:justify; margin-top: -30px">
  <b><i>Figure: Overview of the GNN-ViTCap framework for microscopic whole slide images classification and captioning. (a) Scanner WSI where the absolute position of each patch is known. (b) Microscopic WSI lacks patch position and contains redundant patches due to multiple captures from a pathologist’s subjective perspective. (c) GNN-ViTCap architecture: (i) extracting the patches from whole slide image, (ii) extracting image embeddings using a visual feature extractor, (iii) removing redundancy through deep embedded clustering, (iv) extracting representative images with scalar dot attention mechanism, (v) constructing a graph neural network (GNN) using the similarity of representative patches to capture contextual information within clusters (local) and between different clusters (regional), (vi) applying global mean pooling, which aggregates all node representations, (vii) classifying microscopic WSI using aggregated image embeddings and, (viii) projecting the aggregated image embeddings into the language model’s input space using a linear layer, and combining these projections with input caption tokens fine-tunes the LLMs for caption generation.</i></b>
</p>


<h2 style="color:#2637a1; margin-top: 30px">References</h2>
<ol style="margin-left:0; text-align: justify;  padding-left:1.2em;">
  <li>N. Islam, K. M. Hasib, M. F. Mridha, S. Alfarhood, M. Safran, and M. K. Bhuyan, “Fusing global context with multiscale context for enhanced breast cancer classification,” <i>Scientific Reports</i>, vol. 14, no. 1, p. 27358, 2024.</li>
  <li>M. Tsuneki and F. Kanavati, “Inference of captions from histopathological patches,” in <i>Proc. Med. Imag. Deep Learn. (MIDL)</i>, 2022, pp. 1235–1250.</li>
  <li>Z. Zhang et al., “Pathologist-level interpretable whole-slide cancer diagnosis with deep learning,” <i>Nat. Mach. Intell.</i>, vol. 1, no. 5, pp. 236–245, 2019.</li>
  <li>A. H. Song et al., “Artificial intelligence for digital and computational pathology,” <i>Nat. Rev. Bioeng.</i>, vol. 1, no. 12, pp. 930–949, 2023.</li>
  <li>F. Ahmed et al., “PathAlign: A vision-language model for whole slide images in histopathology,” <i>arXiv preprint arXiv:2406.19578</i>, 2024.</li>
  <li>M. Ilse, J. Tomczak, and M. Welling, “Attention-based deep multiple instance learning,” in <i>Proc. Int. Conf. Mach. Learn. (ICML)</i>, 2018, pp. 2127–2136.</li>
  <li>Z. Shao et al., “TransMIL: Transformer based correlated multiple instance learning for whole slide image classification,” in <i>Adv. Neural Inf. Process. Syst. (NeurIPS)</i>, vol. 34, pp. 2136–2147, 2021.</li>
  <li>D. Ahmedt-Aristizabal et al., “A survey on graph-based deep learning for computational histopathology,” <i>Comput. Med. Imag. Graph.</i>, vol. 95, p. 102027, 2022.</li>
  <li>S. Elbedwehy et al., “Enhanced descriptive captioning model for histopathological patches,” <i>Multimed. Tools Appl.</i>, vol. 83, no. 12, pp. 36645–36664, 2024.</li>
  <li>L. Wu et al., “Recall what you see continually using gridLSTM in image captioning,” <i>IEEE Trans. Multimedia</i>, vol. 22, no. 3, pp. 808–818, 2019.</li>
  <li>S. Ren, K. He, R. Girshick, and J. Sun, “Faster R-CNN: Towards real-time object detection with region proposal networks,” <i>IEEE Trans. Pattern Anal. Mach. Intell.</i>, vol. 39, no. 6, pp. 1137–1149, 2016.</li>
  <li>D.-R. Beddiar, M. Oussalah, and T. Seppänen, “Automatic captioning for medical imaging (MIC): A rapid review of literature,” <i>Artif. Intell. Rev.</i>, vol. 56, no. 5, pp. 4019–4076, 2023.</li>
  <li>Y. Sun et al., “PathMMU: A massive multimodal expert-level benchmark for understanding and reasoning in pathology,” <i>arXiv preprint arXiv:2401.16355</i>, 2024.</li>
  <li>N. Dimitriou, O. Arandjelović, and P. D. Caie, “Deep learning for whole slide image analysis: An overview,” <i>Front. Med.</i>, vol. 6, p. 264, 2019.</li>
  <li>J. Barker et al., “Automated classification of brain tumor type in whole-slide digital pathology images using local representative tiles,” <i>Med. Image Anal.</i>, vol. 30, pp. 60–71, 2016.</li>
  <li>H. Touvron et al., “LLaMA: Open and efficient foundation language models,” <i>arXiv preprint arXiv:2302.13971</i>, 2023.</li>
  <li>Q. Lu, D. Dou, and T. Nguyen, “ClinicalT5: A generative language model for clinical text,” in <i>Findings Assoc. Comput. Linguist.: EMNLP</i>, 2022, pp. 5436–5443.</li>
  <li>R. Luo et al., “BioGPT: Generative pre-trained transformer for biomedical text generation and mining,” <i>Brief. Bioinform.</i>, vol. 23, no. 6, p. bbac409, 2022.</li>
  <li>K. Zhang et al., “A generalist vision–language foundation model for diverse biomedical tasks,” <i>Nat. Med.</i>, pp. 1–13, 2024.</li>
  <li>O. Russakovsky et al., “ImageNet large scale visual recognition challenge,” <i>Int. J. Comput. Vis.</i>, vol. 115, pp. 211–252, 2015.</li>
  <li>A. Radford et al., “Learning transferable visual models from natural language supervision,” in <i>Proc. Int. Conf. Mach. Learn. (ICML)</i>, 2021, pp. 8748–8763.</li>
  <li>C. Jia et al., “Scaling up visual and vision-language representation learning with noisy text supervision,” in <i>Proc. Int. Conf. Mach. Learn. (ICML)</i>, 2021, pp. 4904–4916.</li>
</ol>