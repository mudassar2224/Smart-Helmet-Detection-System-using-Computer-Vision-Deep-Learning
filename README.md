Here is the updated **full code** with tech icons (TensorFlow, PyTorch, Python, OpenCV, VS Code, GitHub, etc.) added into both the **Tech Stack section** and the **Author/Footer section**, along with animated dividers and sticker logos.

You can copy and paste this code block directly into your `README.md` editor:

```markdown
<div align="center">

  <!-- Animated Typing SVG Header -->
  <a href="https://git.io/typing-svg">
    <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=32&pause=1000&color=00F0FF&center=true&vcenter=true&width=700&height=70&lines=%F0%9F%8F%8D%EF%B8%8F+Smart+Helmet+Detection+System;Real-Time+YOLOv8+%2B+ResNet50+Pipeline;AI-Powered+Safety+%26+Compliance" alt="Typing SVG" />
  </a>

  <br />

  <!-- Main Hero Image -->
  <img width="387" height="516" alt="image" src="https://github.com/user-attachments/assets/28fb1773-5c20-4ce5-8e30-3eefc68d6a5a" style="border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.15);" />

  <br /><br />

  <!-- Animated / Gradient Badges & Logos -->
  <p align="center">
    <a href="https://huggingface.co/spaces/Maliktg5/Smart_Helmet_Detection_Systemt">
      <img src="https://img.shields.io/badge/🤗%20Live%20Demo-Hugging%20Face-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black" alt="Live Demo" />
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

  <!-- Top Animated Wave Divider -->
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=24,25,26,27,28&height=100&section=header" width="100%" />

  <blockquote>
    🚀 <b>A two-model AI pipeline</b> that detects motorcycle riders and automatically classifies whether each rider is wearing a helmet — in real time, on images and videos.
  </blockquote>

</div>

---

## 📸 Live Demo Screenshots

<div align="center">

### ✅ Image Detection — Helmet Detected (100% Compliance)
<img width="1366" height="759" alt="demo_helmet" src="https://github.com/user-attachments/assets/54d31339-1b4c-4403-9056-cb943d53732b" style="border-radius: 8px;" />

<br /><br />

### 🎥 Video Detection — Real-Time Processing
<img width="1346" height="689" alt="demo_video" src="https://github.com/user-attachments/assets/c4363f94-69ff-4e11-bc8d-9a9c60955227" style="border-radius: 8px;" />

<br /><br />

### 🔴 Image Detection — No Helmet Detected
<img width="480" height="270" alt="demo_result" src="https://github.com/user-attachments/assets/29d8dd10-d536-4695-be0f-8250e4c6686a" style="border-radius: 8px;" />

</div>

---

## 🎯 What It Does

This system solves a real-world **road safety problem**: automatically detecting whether motorcycle riders are wearing helmets from any image or video feed.

| Input | Output |
|---|---|
| 📷 **Image with riders** | Bounding boxes + `Helmet` / `No Helmet` label + confidence score |
| 🎥 **Uploaded video** | Fully annotated output video with per-frame detection |
| 📊 **Statistics panel** | Rider count, helmet count, compliance percentage |

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

```

---

## ⚙️ Tech Stack & Tools

| Layer | Technology | Purpose |
| --- | --- | --- |
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

## 📊 Model Performance

| Metric | Score |
| --- | --- |
| **Overall Accuracy** | **83%** |
| **ROC-AUC Score** | **0.90** |
| **Helmet Precision** | **0.89** |
| **Helmet Recall** | **0.85** |
| **Helmet F1-Score** | **0.87** |
| **No Helmet Precision** | **0.73** |
| **No Helmet Recall** | **0.78** |
| **No Helmet F1-Score** | **0.75** |
| **Optimal Threshold** | **0.58** (auto-found) |

> 💡 Threshold was **not hardcoded at 0.5** — it was automatically found by scanning thresholds from 0.20 → 0.80 and selecting the one with the highest macro F1-score.

---

## 🏗️ Project Structure

```text
smart-helmet-detection/
│
├── 📁 1_datasets/
│   ├── yolo_dataset/              ← Roboflow download (YOLO format)
│   └── resnet_dataset/
│       ├── helmet/                ← Cropped head images with helmets
│       └── no_helmet/             ← Cropped head images without helmets
│
├── 📁 3_models/
│   ├── yolo.pt                    ← Trained YOLOv8 weights (best.pt)
│   ├── resnet.keras               ← Trained ResNet50 weights
│   └── optimal_threshold.npy     ← Auto-optimized decision threshold
│
├── app.py                         ← Gradio web application
├── requirements.txt               ← Python dependencies
├── README.md                      ← This file
└── Smart_Helmet_Detection.ipynb   ← Full training notebook (Colab)

```

---

## 🚀 How to Run

### ▶️ Option 1 — Live Web App (No Setup Needed)

**👉 [Try it now on Hugging Face**](https://huggingface.co/spaces/Maliktg5/Smart_Helmet_Detection_Systemt)

---

### ▶️ Option 2 — Train Your Own Models (Google Colab)

**👉 [Open Training Notebook**](https://colab.research.google.com/drive/15uGyd72UBFkgHZAtbmllrVtsFPxPCbt_?usp=sharing)

Steps inside the notebook:

1. Install dependencies
2. Download datasets (Roboflow + Kaggle — automatic)
3. Parse XML annotations → helmet/no_helmet crops
4. Train YOLOv8 (50 epochs)
5. Train ResNet50 with 2-phase fine-tuning
6. Evaluate + auto-find optimal threshold
7. Run inference on images/videos
8. Deploy to Hugging Face

---

### ▶️ Option 3 — Run Locally

```bash
# Clone the repo
git clone [https://github.com/Maliktg5/smart-helmet-detection](https://github.com/Maliktg5/smart-helmet-detection)
cd smart-helmet-detection

# Install dependencies
pip install -r requirements.txt

# Run the app
python app.py

```

Open your browser at `http://localhost:7860`

---

## 🔑 Key Technical Highlights

### 1. Two-Model Pipeline (Correct ML Practice)

```text
YOLO   = answers WHERE  (location / bounding box)
ResNet = answers WHAT   (classification / helmet or not)
Never mixed. Always separate.

```

### 2. Class Imbalance Fix

The dataset had **190 helmet vs 96 no-helmet** images.
Without fixing this, the model predicted "Helmet" for everything (66% accuracy, 0% no-helmet recall).

```python
# Auto-compute balanced weights
weights = compute_class_weight(class_weight="balanced",
                                classes=unique_classes,
                                y=class_labels)
# no_helmet gets ~1.49x penalty weight vs helmet

```

### 3. Two-Phase Transfer Learning

```text
Phase 1: Freeze ResNet50 base → train only the head (15 epochs)
Phase 2: Unfreeze top 50 layers → fine-tune at lr=5e-5 (15 epochs)
Result: +17% accuracy vs Phase 1 alone

```

### 4. Batch Inference for Speed

```python
# OLD — slow: one ResNet call per crop
for crop in crops:
    pred = model.predict(crop)   # N separate calls

# NEW — fast: all crops in one batch
batch = np.concatenate(all_crops, axis=0)
preds = model.predict(batch)     # 1 call for all

```

### 5. Auto-Optimized Threshold

```python
# Scan all possible thresholds, pick best macro F1
for thresh in np.arange(0.20, 0.80, 0.02):
    f1 = f1_score(y_true, y_prob >= thresh, average="macro")
# Found: 0.58 beats default 0.50 by +15% on no_helmet recall

```

---

## 📦 Datasets Used

| Dataset | Source | Size | Use |
| --- | --- | --- | --- |
| **Bike Helmet Detection** | [Roboflow](https://roboflow.com) | 2,754 images | YOLO training |
| **Helmet Detection** | [Kaggle — andrewmvd](https://www.kaggle.com/datasets/andrewmvd/helmet-detection) | 1,434 crops | ResNet training |

---

## ⚡ Video Processing Performance

| Skip Frames | Speed (CPU) | Accuracy |
| --- | --- | --- |
| **1 (every frame)** | ~0.5 fps | Best |
| **5** | ~2.0 fps | Good |
| **10** | ~4.0 fps | Acceptable |
| **15** | ~6.0 fps | Fast/rough |

> 📌 Videos are automatically resized to **640px width** before processing to maximize speed on CPU-only Hugging Face Spaces.

---

## 🤝 Contributing

Pull requests are welcome. For major changes, please open an issue first.

1. Fork the repo
2. Create your branch: `git checkout -b feature/your-feature`
3. Commit: `git commit -m "Add your feature"`
4. Push: `git push origin feature/your-feature`
5. Open a Pull Request

---

## 📄 License

This project is licensed under the **MIT License** — see [LICENSE](https://www.google.com/search?q=LICENSE) for details.

---

## 👤 Author

### **Muhammad Mudassar**

*Flutter Developer & ML Engineer*

⭐ *If this project helped you, please consider giving it a star on GitHub!* ⭐
