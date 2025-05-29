# Deep Learning-Based Component Detection and Analysis on PCB Cards

📍 **Project Type**: Internship @ ASAP Engineering (HCLTech)  
📅 **Duration**: 10 months (Ongoing)  
👨‍💻 **Author**: Livio SINGARIN-SOLE  
🛠 **Status**: 🔧 First version – In development and regularly updated

---

## 🚀 Overview

This repository presents a deep learning-based system designed to **detect, classify, and analyze electronic components on PCB (Printed Circuit Board) images**. It is part of an ongoing internship project conducted at ASAP Engineering (a subsidiary of HCLTech).

The solution focuses on three major areas:

- **Robust object detection** using Faster R-CNN
- **Multi-model fusion** for enhanced performance across component types
- **Embedding-based analysis** for unsupervised classification and dataset enhancement

⚠️ _Note: This project is currently under development. The present version is an initial draft and will be enhanced with new features, experiments, and results._

---

## 📦 Key Features

### 1. 🎯 Object Detection Pipeline
- Architecture: Faster R-CNN with ResNet backbone
- Dataset: Custom annotated PCB images with class-specific challenges
- Tuning: Extensive hyperparameter optimization using [Optuna](https://optuna.org/)
- Metric: Custom mAP at low IoU thresholds (e.g., 0.2) to account for small components


|                                  Component Detection                                         |
|![detections](https://github.com/user-attachments/assets/95e31e31-9a37-4760-a59f-d0c601c788e4)|

### 2. 🔄 Multi-Model Fusion Strategy
- Slicing-based models (via [SAHI](https://github.com/obss/sahi)) for small components like resistors/capacitors
- Normal full-image models for larger elements like transistors and ICs
- Smart inference pipeline filters predictions based on model-specific subclass assignments
- Final detections are merged and refined using Non-Maximum Suppression (NMS)

### 3. 🧠 Embedding-Based Analysis (🔍 Highlighted Feature)
- Embeddings are generated using **InceptionV3** (pretrained on ImageNet)
- Component crops are transformed into compact, high-dimensional vectors
- Applications:
  - **Unsupervised Clustering** (using DBSCAN and KMeans)
  - **Visual Component Classification**
  - **Dataset Cleaning** (e.g., automatic duplicate detection)
- Dimensionality reduction via **UMAP** allows intuitive 2D/3D visualization
- Use of **fuzzy clustering** to handle ambiguous samples and outliers

|                            Embedding (PCB-CARDS DATASET) Visualization                                 | 
|![embeddings_pcb-cards](https://github.com/user-attachments/assets/5fdd5992-0f6b-4c2d-80bb-e095467bba65)|
---

## 🖼 Sample Results

|                                       Components clustering                                               |
|-----------------------------------------------------------------------------------------------------------|
| ![clustering_components](https://github.com/user-attachments/assets/875e8c12-d194-4383-8f48-6bd749997508) | 

|                                           Image research                                                  |
|-----------------------------------------------------------------------------------------------------------|
|     ![image_nearest](https://github.com/user-attachments/assets/e3121415-4456-4a61-b616-c94ee3928aed)     |   

|                                         Duplicate Detection                                               |
|-----------------------------------------------------------------------------------------------------------|
|     ![duplicates](https://github.com/user-attachments/assets/b820e136-d4c6-4a7b-923d-8a84c9582815)        | 

---

## 🧪 Technical Stack

- **Programming**: Python 3.11
- **Frameworks**: PyTorch, SAHI, Scikit-learn, UMAP-learn, OpenCV, transformers
- **Modeling**: Faster R-CNN (via Torchvision), InceptionV3, (currently trying CLIP and ViT)
- **Clustering**: DBSCAN, KMeans, Fuzzy DBSCAN, OPTICS
- **Clustering**: fiftyone
---

## 📚 Structure of the Report

The full internship report includes:

1. 📖 Introduction to the PCB-KI project
2. 🔍 Object detection implementation and tuning (was already implemented)
3. 🧩 Multi-model combination strategy
4. 📊 Embedding extraction for unsupervised clustering and image research by similarity
5. 🧹 Dataset cleaning using fuzzy logic and visual matching
6. 📈 Empirical evaluation (mAP, runtime, clustering scores)
7. 🧠 Design rationale and future perspectives

---

## 💬 Notes

- This is a **research and experimentation** project: architecture and methods may change as we explore further.

---
**Livio SINGARIN-SOLE**  
🏢 Internship @ ASAP Engineering – HCLTech  
📍 Munich
---

## 📄 License

To be defined. Currently private/internal – not licensed for external use without permission.

