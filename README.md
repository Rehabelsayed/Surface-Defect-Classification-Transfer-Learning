# Surface-Defect-Classification-Transfer-Learning
Industrial surface defect classification using DenseNet121 with transfer learning and fine-tuning (NEU Dataset).
# Surface Defect Classification using Transfer Learning

## Project Overview
This project applies transfer learning using a pre-trained DenseNet121 model to classify industrial surface defects from the NEU Surface Defect Dataset.

The task is a multi-class image classification problem involving six types of surface defects.

## Dataset
NEU Surface Defect Database  
Classes:
- Crazing
- Inclusion
- Patches
- Pitted Surface
- Rolled-in Scale
- Scratches

The dataset contains:
- 1440 training images
- 360 validation images

## Methodology

### 1. Transfer Learning
DenseNet121 pre-trained on ImageNet was used as the base model.

### 2. Model Modification
The original classification layer was removed and replaced with:
- GlobalAveragePooling
- BatchNormalization
- Dense layer (ReLU)
- Dropout (0.4)
- Softmax output layer (6 classes)

### 3. Training Strategy
Phase 1: Feature Extraction (frozen base model)  
Phase 2: Fine-tuning last 30 layers with reduced learning rate (1e-5)

## Results
- Training Accuracy: ~100%
- Validation Accuracy: ~99%
- Minimal overfitting observed
- Confusion matrix shows near-perfect classification

## Conclusion
Transfer learning combined with selective fine-tuning achieved high classification performance for industrial surface defect detection.
