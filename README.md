<h1 align="center">Mohammadjavad Ghorbanalivakili</h1>

<p align="center"><strong>AI Research Engineer · PhD Candidate at York University</strong></p>

<p align="center">
  I build computer vision and multimodal AI systems, from preparing datasets and training models across GPUs to building tested software.
</p>

<p align="center">
  <a href="https://linkedin.com/in/mjghvakili">LinkedIn</a>
  ·
  <a href="https://huggingface.co/m-vakili75">Hugging Face</a>
  ·
  <a href="https://hub.docker.com/u/mvakili96">Docker Hub</a>
  <br>
  Toronto, Canada · Open to relocation
</p>

## About

Over the past five years, I've worked with images, LiDAR point clouds, and language to tackle perception problems in transportation and robotics. I develop models, build the data and evaluation pipelines around them, and run reproducible experiments on GPU clusters.

I also build software beyond perception: a [document retrieval pipeline with cited answers](#05--document-retrieval-with-local-llms) and a [shared-expense application with automated tests and deployment workflows](#04--chipin).

<p align="center">
  <a href="#selected-work">Explore my projects</a> · <a href="#technical-toolkit">Browse my toolkit</a> · <a href="#experience">See my experience</a>
</p>

## Technical toolkit

<table>
  <tr>
    <td width="50%" valign="top">
      <strong>AI research areas</strong><br><br>
      Computer vision · Multimodal AI · Vision-language models<br>
      Object detection · Semantic, instance &amp; panoptic segmentation<br>
      Supervised &amp; self-supervised learning · LiDAR · Depth estimation · 3D reconstruction
    </td>
    <td width="50%" valign="top">
      <strong>ML frameworks and libraries</strong><br><br>
      Python · PyTorch · OpenCV · NumPy · Pandas · scikit-learn<br>
      TorchVision · MMDetection · MMSegmentation · LoRA/PEFT<br>
      MATLAB · Bash
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <strong>Distributed training and infrastructure</strong><br><br>
      PyTorch DDP · DeepSpeed · Slurm · Apptainer<br>
      Docker · Docker Compose · Linux (Ubuntu)<br>
      Microsoft Azure · Google Cloud Platform
    </td>
    <td width="50%" valign="top">
      <strong>Software engineering and MLOps</strong><br><br>
      Flask · Redis Stack · REST APIs · Data engineering<br>
      pytest · Playwright · GitHub Actions · CI/CD<br>
      Git · Weights &amp; Biases · OpenAI Codex
    </td>
  </tr>
  <tr>
    <td colspan="2" valign="top">
      <strong>Retrieval and language models</strong><br><br>
      LangChain · FAISS · BM25 · Hybrid search · Cross-encoder reranking · Local Qwen inference
    </td>
  </tr>
</table>

## Research trajectory

<p align="center">
  <img src="assets/research-trajectory.svg" width="100%" alt="TPE-Net candidate path extraction progresses to TRIT-Net instance tracing and vision-language ego-path reasoning segmentation. Mobile LiDAR track and switch recognition is a parallel research line.">
</p>

## Selected work

### 01 / Reasoning-Guided Railway Perception

When several tracks meet at a switch, the model must identify the route the train can follow. In collaboration with **Canadian National Railway (CN)**, I adapted **[LISA-7B](https://openaccess.thecvf.com/content/CVPR2024/html/Lai_LISA_Reasoning_Segmentation_via_Large_Language_Model_CVPR_2024_paper.html)** to predict an ego-path mask and generate a route explanation from an image and language prompt.

I built rail-specific prompts, mask and explanation supervision, and a distributed training workflow using LoRA, DeepSpeed, Slurm, and Apptainer across eight NVIDIA L40 GPUs.

[Code](https://github.com/mvakili96/Railway_Perception_FoundationModel) · [Published ISPRS 2026 paper](https://isprs-archives.copernicus.org/articles/XLIX-B3-2026/89/2026/) · [Model weights](https://huggingface.co/m-vakili75/railway-lisa-7b-semantic-reasoning-clip)

---

### 02 / TPE-Net → TRIT-Net

This research traces individual rail paths through scenes where tracks split and merge. I developed **TPE-Net** in collaboration with **Thales Canada**, combining a regression CNN with graph-based spatial clustering to construct candidate paths.

I then built **TRIT-Net**, a hybrid transformer-convolution U-Net that learns **Attraction Field Maps** for tracing and branching. The project also uses [VICReg](https://openreview.net/forum?id=xm6YD62D1Ub) self-supervised pretraining on **23,924 unlabeled railway images**.

- **TPE-Net** was published at [IEEE CASE 2023](https://doi.org/10.1109/CASE56687.2023.10260541). Its journal extension is under review at *IEEE Transactions on Intelligent Transportation Systems*.
- **TRIT-Net** was published at [CRV 2025](https://crv.pubpub.org/pub/h6d3dccv). Its journal extension is under review at *Engineering Applications of Artificial Intelligence*.

[Explore the shared repository](https://github.com/mvakili96/TRIT-Net). TRIT-Net builds on TPE-Net, and both projects share this codebase.

---

### 03 / Multi-Railway Automatic Data Extraction

In collaboration with **Thales Canada**, I developed a pipeline that extracts railway tracks and switches from mobile LiDAR point clouds. It combines Kalman filtering, minimum description length model selection, and multiscale template matching to trace rails and recognize switch configurations.

[Read the IEEE ITSC 2025 paper](https://doi.org/10.1109/ITSC60802.2025.11423103). The source repository remains private under the industry collaboration.

---

### 04 / ChipIn

ChipIn helps groups record shared expenses and calculate who owes whom. In this collaborative side project, I developed a containerized **Flask and Redis Stack** backend with REST APIs, a browser admin panel, and Telegram integration. GitHub Actions runs the project's unit and integration tests.

[Explore ChipIn](https://github.com/mvakili96/ChipIn)

---

### 05 / Document Retrieval with Local LLMs

I built a **retrieval-augmented generation (RAG)** pipeline that answers questions across six PDFs totaling **5,552 pages**, with source and page citations. It combines vector retrieval and BM25 keyword search, reranks candidates with a cross-encoder, and generates answers locally with **Qwen2.5-7B**. FAISS supports a choice between exact kNN and approximate HNSW search.

I created a **50-question evaluation benchmark** to guide changes to chunking, retrieval, and reranking. The baseline achieved **74.35% mean evidence-text recall** with the top four reranked chunks, averaged over the 47 questions with scored evidence; three unanswerable questions were retained for manual inspection. This metric measures retrieval coverage of annotated passages.

[Explore the RAG pipeline](https://github.com/mvakili96/RAG) · [Read the evaluation](https://github.com/mvakili96/RAG/blob/master/evaluation-results/summary.md)

## Experience

**Graduate Researcher · Augmented Urban Space Modelling Lab, York University · 2021–present**

I develop railway perception pipelines from RGB images and LiDAR data through model training and benchmark evaluation. My work includes collaborations with **Thales Canada**, **Metrolinx**, and the **Ontario Autonomous Vehicle Innovation Network (OAVIN)**.

**Visiting Researcher · Smart Mobility Lab, Hanyang University · 2026**

I collaborated with **Neubility**, a Korean sidewalk delivery robot company, on foundation-model pipelines for object detection, depth estimation, and 3D reconstruction.

<sub>Earlier work spans autonomous agricultural systems, 3D mapping, embedded sensing and actuation, signal processing, and mechanical design.</sub>

## Education

- I'm a **PhD candidate in Earth and Space Science and Engineering** at York University.
- I earned my **MSc in Mechanical Engineering** at Sharif University of Technology.
- I earned my **BSc in Mechanical Engineering** at the University of Tehran.

## Beyond the lab

Outside AI research, I am a personal trainer and HIIT instructor recognized as the **Tait McKenzie Centre's Personal Trainer of the Year for 2024–2025**.

---

<p align="center">
  I'm open to research engineering and applied ML opportunities, including relocation.
  <br><br>
  <a href="https://linkedin.com/in/mjghvakili">Let's connect on LinkedIn</a>
</p>
