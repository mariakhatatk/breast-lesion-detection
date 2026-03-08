# Breast Lesion Detection using Deep Learning

This project presents a deep learning framework for breast lesion detection in mammography images using multiple state-of-the-art detection architectures. The framework evaluates the performance of modern object detection and transformer-based models on two publicly available mammography datasets.

---

# Models Implemented

The following models are implemented and compared:

- YOLOv8n
- YOLOv8m
- YOLOv8 + Mamba
- Faster R-CNN
- DETR
- Vision Transformer (ViT)

These models are evaluated for detection accuracy, generalization capability, and computational complexity.

---

# Datasets

Two public mammography datasets are used in this project:

### CBIS-DDSM
https://www.cancerimagingarchive.net/collection/cbis-ddsm/

### INbreast
https://www.kaggle.com/datasets/ramanathansp20/inbreast-dataset

Note: Large raw datasets are not included in this repository.

---

# Project Pipeline

![Pipeline](results/pipeline_diagram.png)

The pipeline includes:

1. Dataset acquisition
2. Image preprocessing
3. ROI extraction
4. Bounding box generation
5. Model training
6. Model evaluation
7. Cross-dataset generalization analysis

---

## Detection Architecture

The following diagram illustrates the proposed breast lesion detection framework integrating multiple deep learning models.

![Detection Architecture](results/detailed_detection_architecture_flow.png)

---

# Experimental Results

The repository includes experiment results and model comparison graphs.

## Model Performance Results

### Model Comparison Table

![Model Comparison Table](results/comparisontableofmodels.png)

---

## Detection Architecture

![Detection Architecture](results/detailed_detection_architecture_flow.png)

---

## Data Processing Pipeline

![Pipeline](results/data_processing_pipeline.png)

### Model Complexity vs Accuracy

![Model Complexity](results/model_complexity_accuracy.png)

---

### Cross Dataset Generalization

![Cross Dataset](results/cross_dataset_generalization.png)

---

### mAP@50 Comparison

![mAP Comparison](results/map_comparison.png)

---

### Model Performance Comparison

![Performance Comparison](results/model_performance_comparison.png)

---

### Training Time Comparison

![Training Time](results/training_time_comparison.png)

# Evaluation Metrics

Models are evaluated using the following metrics:

- Precision
- Recall
- F1 Score
- Mean Average Precision (mAP)

---

# Installation

Install required dependencies:
