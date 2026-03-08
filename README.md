# Multi-Model Breast Lesion Detection using Deep Learning

This repository contains the implementation of a deep learning framework for automated breast lesion detection in mammography images. The project evaluates multiple state-of-the-art object detection and transformer-based architectures to analyze lesion localization performance and model generalization across different medical imaging datasets.

The system integrates convolutional detection models and transformer architectures to compare detection accuracy, computational complexity, and cross-dataset generalization capability.

---

# Implemented Models

The following models were implemented and evaluated:

- YOLOv8n
- YOLOv8m
- YOLOv8 + Mamba
- Faster R-CNN
- DETR (Detection Transformer)
- Vision Transformer (ViT)

These models were trained and evaluated using standardized object detection metrics including Precision, Recall, F1-Score, and Mean Average Precision (mAP@50).

---

# Datasets

Two publicly available mammography datasets were used in this study.

## CBIS-DDSM

Curated Breast Imaging Subset of the Digital Database for Screening Mammography.

Dataset link:

https://www.cancerimagingarchive.net/collection/cbis-ddsm/

Citation:

Lee RS, Gimenez F, Hoogi A, Rubin DL. Curated Breast Imaging Subset of DDSM. The Cancer Imaging Archive, 2017.

---

## INBreast

A high-resolution mammography dataset for breast cancer detection research.

Dataset link:

https://www.kaggle.com/datasets/ramanathansp20/inbreast-dataset

Citation:

Moreira IC et al. INbreast: Toward a Full-Field Digital Mammographic Database. Academic Radiology, 2012.

---

# Detection Architecture

The proposed detection architecture integrates multiple deep learning models for lesion localization and classification.

![Detection Architecture](results/detection_architecture.png)

The framework performs feature extraction using CNN or transformer encoders and applies different detection branches including YOLOv8, Faster-R-CNN, DETR, and Vision Transformer. Context modeling using the Mamba module enhances spatial representation for improved lesion detection.

---

# Data Processing Pipeline

The following pipeline illustrates the preprocessing and training workflow used in the project.

![Data Processing Pipeline](results/data_processing_pipeline.png)

Pipeline steps include:

1. Dataset acquisition
2. CLAHE contrast enhancement
3. Image normalization and resizing
4. ROI mask processing
5. Bounding box generation
6. Dataset splitting (train/validation/test)
7. Model training and evaluation

---

# Experimental Results

## Model Comparison Table

![Model Comparison](results/comparisontableofmodels.png)

| Model | Precision | Recall | F1 Score | mAP@50 |
|------|------|------|------|------|
| YOLOv8n | 0.82 | 0.79 | 0.80 | 0.85 |
| YOLOv8m | 0.86 | 0.83 | 0.84 | 0.88 |
| YOLOv8 + Mamba | **0.88** | **0.87** | **0.87** | **0.90** |
| Faster R-CNN | 0.84 | 0.82 | 0.83 | 0.86 |
| DETR | 0.83 | 0.81 | 0.82 | 0.85 |
| Vision Transformer | 0.80 | 0.78 | 0.79 | 0.83 |

The YOLOv8 + Mamba architecture achieved the best detection performance across all evaluation metrics.

---

# Model Complexity vs Accuracy

![Complexity Accuracy](results/model_complexity_accuracy.png)

The comparison highlights the trade-off between model parameter size and detection accuracy. YOLOv8 + Mamba achieves the highest mAP while maintaining moderate model complexity.

---

# Cross-Dataset Generalization

![Cross Dataset](results/cross_dataset_generalization.png)

Cross-dataset evaluation shows the ability of models trained on CBIS-DDSM to generalize to the INBreast dataset.

---

# mAP@50 Comparison

![mAP Comparison](results/map_comparison.png)

The YOLOv8 + Mamba model achieved the highest detection accuracy with an mAP@50 of 0.90.

---

# Training Time Comparison

![Training Time](results/training_time_comparison.png)

The training time comparison shows that lightweight YOLO models train faster than transformer-based detection models.

---

# Installation

Install required dependencies using:
