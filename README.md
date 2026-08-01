<div align="center">

  <!-- Dynamic Typing Banner Header -->
  <a href="https://git.io/typing-svg">
    <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=32&pause=1000&color=00F0FF&center=true&vcenter=true&width=700&height=70&lines=%F0%9F%8F%8D%EF%B8%8F+Smart+Helmet+Detection+System;Real-Time+YOLOv8+%2B+ResNet50+Pipeline;AI-Powered+Safety+%26+Compliance" alt="Typing SVG" />
  </a>

  <br />

  <!-- Hero Header Image -->
  <img width="420" src="https://github.com/user-attachments/assets/28fb1773-5c20-4ce5-8e30-3eefc68d6a5a" alt="Smart Helmet Banner" style="border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.15);" />

  <br /><br />

  <!-- Shields Badges -->
  <p align="center">
    <a href="https://huggingface.co/spaces/Maliktg5/Smart_Helmet_Detection_Systemt">
      <img src="https://img.shields.io/badge/🤗%20Live%20Demo-Hugging%20Face-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black" alt="HuggingFace Space" />
    </a>
    <a href="https://colab.research.google.com/drive/15uGyd72UBFkgHZAtbmllrVtsFPxPCbt_?usp=sharing">
      <img src="https://img.shields.io/badge/Open%20In-Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white" alt="Open In Colab" />
    </a>
    <a href="https://python.org">
      <img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
    </a>
    <a href="https://tensorflow.org">
      <img src="https://img.shields.io/badge/TensorFlow-2.15-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white" alt="TensorFlow" />
    </a>
    <a href="https://ultralytics.com">
      <img src="https://img.shields.io/badge/YOLOv8-Ultralytics-00ADEF?style=for-the-badge&logo=yolov8&logoColor=white" alt="YOLOv8" />
    </a>
  </p>

  <!-- Animated Wave Header Divider -->
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=24,25,26,27,28&height=100&section=header" width="100%" />

  <blockquote>
    🚀 <b>A state-of-the-art two-model AI pipeline</b> designed to detect motorcycle riders in real-time and classify helmet compliance on both images and video streams.
  </blockquote>

</div>

---

## 🎯 What It Does

This system solves a real-world **road safety problem**: automatically detecting whether motorcycle riders are wearing helmets from any image or video feed.

| Input | Output |
| :--- | :--- |
| 📷 **Image with riders** | Bounding boxes + `Helmet` / `No Helmet` label + confidence score |
| 🎥 **Uploaded video** | Fully annotated output video with per-frame detection |
| 📊 **Statistics panel** | Rider count, helmet count, compliance percentage |

---

## 🛠️ Tech Stack & Tools

<p align="center">
  <img src="https://skillicons.dev/icons?i=python,tensorflow,pytorch,opencv,vscode,github" alt="Tech Stack Icons" />
</p>

| Layer | Technology | Purpose |
| :--- | :--- | :--- |
| **Object Detection** | YOLOv8n (Ultralytics) | Locate riders in frame |
| **Classification** | ResNet50 + Transfer Learning | Classify helmet / no helmet |
| **Training Framework** | TensorFlow 2.15 / Keras | Model training & fine-tuning |
| **Training Hardware** | Google Colab T4 GPU | Fast GPU training |
| **Video Processing** | OpenCV | Frame extraction & annotation |
| **Web Interface** | Gradio 6 | Interactive upload & display |
| **Deployment** | Hugging Face Spaces (CPU) | Public cloud hosting |
| **Dataset — YOLO** | Roboflow API | Auto-download with labels |
| **Dataset — ResNet** | Kaggle (andrewmvd) | Helmet/no-helmet crops |

---

## 📸 Live Demo Screenshots

<div align="center">

  ### ✅ Image Detection — Helmet Detected (100% Compliance)
  <img width="90%" alt="demo_helmet" src="https://github.com/user-attachments/assets/54d31339-1b4c-4403-9056-cb943d53732b" style="border-radius: 8px;" />

  <br /><br />

  ### 🎥 Video Detection — Real-Time Processing
  <img width="90%" alt="demo_video" src="https://github.com/user-attachments/assets/c4363f94-69ff-4e11-bc8d-9a9c60955227" style="border-radius: 8px;" />

  <br /><br />

  ### 🔴 Image Detection — No Helmet Detected
  <img width="70%" alt="demo_result" src="https://github.com/user-attachments/assets/29d8dd10-d536-4695-be0f-8250e4c6686a" style="border-radius: 8px;" />

</div>

---

## 🧠 System Architecture

```text
Input (Image / Video / Camera)
           │
           ▼
  ┌─────────────────┐
  │    YOLOv8n      │  ← Detects WHERE riders are
  │  (Roboflow      │     Classes: person, motorcycle
  │   dataset)      │     Output: bounding boxes
  └────────┬────────┘
           │  Crop head region (top 80% of box)
           ▼
  ┌─────────────────┐
  │   ResNet50      │  ← Decides WHAT is on the head
  │  (Kaggle        │     Classes: helmet / no_helmet
  │   dataset)      │     Output: probability score
  └────────┬────────┘
           │
           ▼
  Annotated Output
  (Box + Label + Confidence + Summary Bar)
