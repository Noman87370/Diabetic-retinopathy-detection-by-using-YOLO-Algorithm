# Integrating YOLOv10 and Dual-Head Inference for Automated Diabetic Retinopathy Diagnosis

<p align="center">
  <strong>IEEE 2nd International Conference on Computing, Applications and Systems (COMPAS 2025)</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/IEEE-Published-blue?style=for-the-badge&logo=ieee" />
  <img src="https://img.shields.io/badge/Domain-Medical%20AI-red?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Model-YOLOv10-orange?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Computer-Vision-purple?style=for-the-badge" />
</p>

## 📌 Overview

This repository contains the implementation of our research paper, **"Integrating YOLOv10 and Dual-Head Inference for Automated Diabetic Retinopathy Diagnosis,"** published at the IEEE 2nd International Conference on Computing, Applications and Systems (COMPAS 2025).

Diabetic Retinopathy (DR) is a diabetes-related eye disease that can lead to vision impairment and blindness if not detected early.

This research proposes an automated diabetic retinopathy detection framework integrating **YOLOv10 with a dual-head inference architecture** to identify DR-related retinal abnormalities and distinguish between diabetic retinopathy (DR) and non-diabetic retinopathy (No-DR).

The proposed framework uses a custom-annotated retinal fundus image dataset prepared and augmented using Roboflow. It combines lesion detection, feature extraction, and classification to support automated retinal image analysis.

## 🎯 Research Objectives

- Develop an automated diabetic retinopathy detection framework using YOLOv10.
- Integrate dual-head inference for improved detection and classification.
- Identify diabetic retinopathy-related abnormalities in retinal fundus images.
- Support binary classification (DR vs. No-DR).
- Explore multiclass classification based on DR severity.
- Improve detection performance through image preprocessing, annotation, and data augmentation.
- Evaluate the model using precision, recall, accuracy, and mean Average Precision (mAP).

## 🧠 Proposed Methodology

The proposed framework integrates YOLOv10's object detection capabilities with a dual-head architecture.

### Key Components

**1. YOLOv10 Architecture**

The model uses an enhanced Cross Stage Partial Network (CSPNet) for feature extraction and a Path Aggregation Network (PAN) for feature fusion.

**2. Dual-Head Inference**

The architecture incorporates:

- One-to-many training to learn richer lesion-level representations.
- One-to-one inference for efficient and accurate predictions.
- NMS-free inference to reduce redundant predictions.
- Lightweight classification heads for efficient output generation.

**3. Dataset Annotation and Augmentation**

Roboflow is used to annotate retinal fundus images and prepare the dataset. Preprocessing and augmentation techniques include:

- Image resizing and auto-orientation.
- Flipping and cropping.
- Rotation.
- Noise addition.

## 🔄 System Workflow

```text
Retinal Fundus Images
          |
          v
   Dataset Collection
          |
          v
  Annotation using Roboflow
          |
          v
 Image Preprocessing
          |
          v
  Data Augmentation
          |
          v
   Dataset Splitting
          |
          v
    YOLOv10 Model
          |
          v
  Dual-Head Inference
          |
          v
  Lesion Detection and
     Classification
          |
          v
      Final Output
       /       \
      v         v
     DR       No-DR
```

## 📊 Dataset Description

The study uses a custom-annotated retinal fundus image dataset containing 9,600 images.

| Class | Total Images | Training | Testing | Validation |
|---|---:|---:|---:|---:|
| Diabetic Retinopathy (DR) | 4,800 | 4,200 | 200 | 400 |
| No Diabetic Retinopathy (No-DR) | 4,800 | 4,200 | 200 | 400 |
| **Total** | **9,600** | **8,400** | **400** | **800** |

### Dataset Distribution

- Training: 88%
- Testing: 4%
- Validation: 8%

### Classification Categories

The research describes a hierarchical classification structure:

**Binary
