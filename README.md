# Skin Cancer Classification: Machine Learning vs Deep learning Techniques

## Project Overview

Skin cancer is one of the most prevalent cancers worldwide, and early detection is crucial for effective treatment. This project aims to develop a Computer-Aided Diagnostic (CAD) system for the binary classification of skin lesions, distinguishing between benign and malignant cases.

This project is part of a larger comparative study of Machine Learning (ML) and Deep Learning (DL) approaches for skin cancer classification. This repository currently contains the ML-based approach. DL techniques and their comparison will be added later.

## Dataset

We utilized two skin lesion datasets. With two main categories for binary classification:
- **Nevus (Benign)**
- **Other Lesions (Malignant)**

And three categories for multiclass classification:

- **bcc (Basal cell carcinoma)**
- **mel (Melanoma)**
- **scc (Squamous cell carcinoma)**

The dataset was divided into training and validation sets to ensure robust evaluation.

### Binary Dataset Details
| Class   | Train Samples | Validation Samples |
|---------|---------------|--------------------|
| Nevus   | 7,725         | 1,931             |
| Others  | 7,470         | 1,865             |

### Multiclass Dataset Details
| Class   | Train Samples | Validation Samples |
|---------|---------------|--------------------|
| BCC     | 1,993         | 498               |
| Mel     | 2,713         | 678               |
| SCC     | 376           | 94                |
---

## Preprocessing

To ensure consistency and improve model performance, we applied the following preprocessing steps:

1. **Hair Removal**: Used a blackhat filter with multiple oriented structural elements and thresholding.
2. **Color Normalization**: Adjusted color balance across images to minimize lighting and color variations.
3. **Region of Interest (ROI) Extraction**: Isolated regions of interest by identifying high-contrast areas within the lesion images.

![Preprocessing Steps](https://raw.githubusercontent.com/mahdiislam79/ISIC_Skin_Cancer_Classification-ML/main/ML/Binary%20Classification%20Challenge/Images/Preprocessing.PNG)

The above image shows the preprocessing pipeline, including hair removal, color normalization, and ROI extraction.

---

## Feature Extraction

Features were extracted from the images to capture essential characteristics. We categorized them into color, texture, and gradient features.

1. **Color Features**: Including color statistics, color moments, and histograms across RGB, HSV, and LAB color spaces.
2. **Texture Features**: LBP (Local Binary Pattern), GLCM (Gray Level Co-occurrence Matrix), and Haralick features.
3. **Gradient Features**: Extracted Histogram of Oriented Gradients (HOG) and wavelet features, followed by dimensionality reduction using PCA.

**Total Features**: 842

---

## Classifier Models

Several Machine Learning models were implemented for the classification task:

1. **Single Models**:
   - Random Forest
   - LightGBM
   - XGBoost
   - Support Vector Machine (SVM)

2. **Ensemble Models**:
   - Stacking
   - Majority Voting

---

## Deep Learning Models

- EfficientNetB0
- EfficientNetB4
- Swin Transformer 

---

## Evaluation Metrics

### Binary Classification Metrics
- **Accuracy**
- **F1 Score**

### Multi-Class Classification Metrics (For Extended Analysis)
- **Kappa Score**
- **Balanced Accuracy**

---

## Results

## Results

### Binary Class (Accuracy)

| Method | Accuracy |
|--------|----------|
| ML     | **0.8363** |
| DL     | **0.9130** |

## Multi-Class (Kappa)

| Method | Kappa  |
|--------|--------|
| ML     | **0.7128** |
| DL     | **0.872** |



## Key Findings

- **Color and texture features** proved essential for this project.
- Despite implementing resampling techniques like SMOTE, the imbalance issue persisted due to overlapping labels (scc and bcc).
- **Feature selection** did not impact performance, suggesting the robustness of our feature extraction approach.

---

## Future Work

To further improve the CAD system:
- Implement a multi-resolution framework.
- Explore deep learning methods for lesion segmentation and feature extraction.

---

## References

For more insights on sampling techniques and skin cancer classification research, see:
- [A Comprehensive Evaluation of Sampling Techniques](https://github.com/newaz-aa/Sampling-algorithms-experimental-analysis)
- [Skin Cancer Classification Using Image Processing and Machine Learning](https://ieeexplore.ieee.org/document/9393198)

---

Thank you for checking out this project! Contributions and feedback are welcome.
