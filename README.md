# Multi-Model Breast Lesion Detection using Deep Learning

This repository presents a deep learning framework for automated breast lesion detection in mammography images. The system evaluates multiple state-of-the-art object detection and transformer-based architectures including **YOLOv8, Faster R-CNN, DETR, Vision Transformer (ViT), and a hybrid YOLOv8 + Mamba model**.

The framework is trained and evaluated on two publicly available mammography datasets: **CBIS-DDSM** and **INBreast**. The goal is to analyze model detection accuracy, computational complexity, and cross-dataset generalization capability for reliable breast cancer detection.

---

# Detection Architecture

![Detection Architecture](results/detailed_detection_architecture_flow.png)

The detection architecture integrates CNN-based object detection models and transformer-based architectures. Feature extraction is performed using convolutional or transformer encoders, followed by lesion localization through bounding box prediction. The Mamba state-space module enhances contextual modeling for improved feature representation.

---

# Data Processing Pipeline

![Data Processing Pipeline](results/dataprecrossingpipeline.png)

The preprocessing pipeline includes:

- CLAHE contrast enhancement
- Image normalization
- Image resizing
- ROI mask extraction
- Bounding box generation
- Dataset splitting (train / validation / test)

These preprocessing steps improve lesion visibility and ensure consistent model training.

---

# Models Implemented

The following deep learning models were implemented and evaluated:

- YOLOv8n
- YOLOv8m
- YOLOv8 + Mamba
- Faster R-CNN
- DETR (Detection Transformer)
- Vision Transformer (ViT)

All models were trained using the same preprocessing pipeline to ensure fair comparison.

---

# Experimental Results

## Model Performance Comparison

![Model Performance](results/modelperformancecomparison.jpg)

This graph compares the detection performance of all implemented models using **Precision, Recall, and F1-Score** metrics.

YOLOv8 + Mamba achieves the highest overall performance due to improved contextual feature modeling.

---

## Mean Average Precision (mAP@50)

![mAP Comparison](results/map.jpg)

The **YOLOv8 + Mamba architecture achieved the highest mAP@50 score**, indicating superior lesion localization capability compared to the baseline models.

---

## Model Complexity vs Accuracy

![Accuracy Comparison](results/accuracy.jpg)

This analysis demonstrates the relationship between **model complexity and detection accuracy**. YOLOv8 models provide a strong balance between computational efficiency and performance.

---

## Model Comparison Table

![Model Table](results/comparisontableofmodels.png)

The comparison table summarizes the detection performance of all models using standard evaluation metrics.

| Model | Precision | Recall | F1 Score | mAP@50 |
|------|------|------|------|------|
| YOLOv8n | 0.82 | 0.79 | 0.80 | 0.85 |
| YOLOv8m | 0.86 | 0.83 | 0.84 | 0.88 |
| YOLOv8 + Mamba | **0.88** | **0.87** | **0.87** | **0.90** |
| Faster R-CNN | 0.84 | 0.82 | 0.83 | 0.86 |
| DETR | 0.83 | 0.81 | 0.82 | 0.85 |
| Vision Transformer | 0.80 | 0.78 | 0.79 | 0.83 |

The results demonstrate that the hybrid **YOLOv8 + Mamba architecture provides the best detection performance** across multiple evaluation metrics.

---

## Training Time Comparison

![Training Time](results/comparison%20model.jpg)

Training time comparison shows that **YOLO-based architectures train faster**, while transformer-based models require higher computational resources.

---

## Model Performance Visualization

![Performance Model](results/performancemodel.jpg)

The performance visualization highlights detection efficiency and accuracy differences among the evaluated architectures.

---

# Dataset

This project uses two publicly available mammography datasets.

### CBIS-DDSM

Curated Breast Imaging Subset of the Digital Database for Screening Mammography.

Dataset link:

https://www.cancerimagingarchive.net/collection/cbis-ddsm/

Reference:
Lee RS et al., 2017, The Cancer Imaging Archive.

---

### INBreast

A full-field digital mammography dataset with annotated breast lesions.

Dataset link:

https://medicalresearch.inescporto.pt/breastresearch/index.php/Get_INbreast_Database

Reference:
Moreira IC et al., Academic Radiology, 2012.

---

# Project Structure
breast-lesion-detection
│
├── results/ # graphs and experimental outputs
├── experiments/ # experiment configurations
├── BreastLesion_Project_All_Models_Added.ipynb
├── requirements.txt
└── README.md
