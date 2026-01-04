# Week 1 Learnings – Plant Disease Classification (EDA)

This document summarizes the key observations, insights, and challenges identified during the exploratory data analysis (EDA) of the PlantVillage dataset as part of Week 1 of the WiDS project.

---

## 1. Dataset Structure and Variant Selection

- The PlantVillage dataset provides multiple versions of the same images: **color**, **grayscale**, and **segmented**.
- For this analysis, we worked with the **color images**, as they best represent real-world conditions where plant disease detection systems would be deployed.
- Each class corresponds to a unique **plant–disease combination**, organized as separate folders (e.g., `Apple___Apple_scab`).

**Learning:** Choosing the appropriate dataset variant is a critical decision that impacts the relevance and realism of the analysis.

---

## 2. Class Distribution and Imbalance

- The dataset exhibits **class imbalance**, with certain disease classes having significantly more images than others.
- Tomato-related diseases are particularly overrepresented compared to some other plant–disease combinations.

**Learning:** Class imbalance can bias model predictions toward majority classes and must be addressed during model training using techniques such as data augmentation or class weighting.

---

## 3. Sample Image Visualization and Visual Similarity

- Visualizing multiple images per class revealed that:
  - Images within a class are relatively consistent in terms of disease patterns.
  - Some diseases affecting the same plant appear **visually very similar**, even to the human eye.
- Differences between classes often involve subtle variations in texture, spot distribution, and color intensity.

**Learning:** Plant disease classification is a challenging task due to high inter-class similarity and subtle visual cues.

---

## 4. Image Resolution and Data Curation

- All sampled images have a uniform resolution of **256 × 256 pixels**.
- This indicates that the dataset has been preprocessed and standardized.

**Learning:** While uniform image sizes simplify preprocessing and model design, they may not fully reflect the variability found in real-world images.

---

## 5. Color Channel Distribution Insights

- RGB channel analysis of representative images showed:
  - A strong dominance of the **green channel**, which is expected due to chlorophyll in leaves.
  - Noticeable variation in color distributions across different disease classes.
- Disease symptoms often manifest as color changes on the leaf surface.

**Learning:** Color information is an important discriminative feature, and converting images to grayscale would result in loss of valuable information.

---

## 6. Key Challenges Identified

- Class imbalance across disease categories.
- High visual similarity between certain disease classes.
- Clean, lab-controlled backgrounds that may limit real-world generalization.
- Subtle disease indicators that require robust feature extraction.

**Learning:** Thorough EDA is essential to understand these challenges before proceeding to model development.

---


---

## Final Reflection

This exploratory analysis helped build a strong foundational understanding of the dataset. By focusing on data characteristics and challenges early on, we are better equipped to make informed decisions regarding preprocessing, model selection, and evaluation strategies in the next stages of the project.


# Week 2 Learnings - Baseline Challenge

## Overview
In Week 2, I worked on building an end-to-end machine learning pipeline for plant disease classification using traditional machine learning techniques. This week focused on understanding how image data can be processed and used with classical ML models instead of deep learning.

---

## Key Learnings

### 1. Image Data Handling for Machine Learning
I learned how raw image data cannot be directly used by traditional machine learning models. Images must be converted into numerical feature vectors by:
- Resizing images to a fixed dimension for consistency
- Normalizing pixel values to bring them into a common range
- Flattening images into one-dimensional vectors

This step is crucial for making image data compatible with classical ML algorithms.

---

### 2. Dataset Structure and Label Extraction
I understood how folder-based datasets work, where each folder represents a class label. Extracting labels directly from directory names helps automate dataset labeling and reduces manual errors.

---

### 3. Importance of Train-Test Splitting
I learned how to properly split data into training and testing sets using:
- An 80–20 split for fair evaluation
- Stratification to preserve class distribution
- Fixed random state to ensure reproducibility

This ensures reliable and unbiased model evaluation.

---

### 4. Feature Scaling and Preprocessing
I learned why feature scaling is important, especially for machine learning models that rely on distance or magnitude of features. Applying scaling after splitting the dataset helps avoid data leakage.

---

### 5. Baseline Modeling
I understood the importance of establishing a baseline using a Dummy Classifier. This helped in setting a minimum performance benchmark and evaluating whether the trained model is actually learning meaningful patterns.

---

### 6. Random Forest Classifier
I gained practical experience with Random Forest, an ensemble learning algorithm that combines multiple decision trees. I learned how:
- Multiple trees reduce overfitting
- Random sampling improves generalization
- Majority voting determines final predictions

This model significantly outperformed the baseline classifier.


# Learnings – Week 3 (Deep Learning on PlantVillage Dataset)

## 1. From Hand-Crafted Features to Learned Features
In Week 2, classical machine learning models relied on manually engineered
features and achieved limited performance (baseline accuracy ≈ 0.67).
In Week 3, Convolutional Neural Networks learned features directly from raw
images, capturing spatial patterns such as edges, textures, and disease regions.

## 2. Understanding CNN Behavior
Training a simple CNN from scratch significantly improved performance
(≈ 90% validation accuracy). Early epochs showed rapid learning, while later
epochs revealed signs of overfitting, emphasizing the importance of monitoring
training and validation curves rather than relying only on final accuracy.

## 3. Importance of Transfer Learning
Transfer Learning using MobileNetV2 further improved accuracy (≈ 93%) with
faster convergence and reduced overfitting. Pretrained models already encode
general visual knowledge, allowing the classifier to focus on disease-specific
patterns with fewer trainable parameters.

## 4. Role of Data Augmentation
Applying random rotations, flips, and zoom helped improve generalization by
exposing the model to varied representations of the same disease class, making
the model more robust to real-world variations.

## 5. Practical Insights from Confusion Matrix Analysis
With 38 classes, raw confusion matrices become difficult to interpret.
Normalized confusion matrices provided clearer insights into class-wise
performance and revealed that most misclassifications occurred between visually
similar plant diseases.

## 6. Key Takeaway
Deep learning models outperform shallow machine learning approaches for
image-based tasks, and transfer learning offers a practical and efficient
solution for achieving high accuracy with limited training time and reduced
overfitting.

Overall, this week demonstrated how modern deep learning models move beyond
manual feature design and enable scalable, real-world image classification.


---


## Key Takeaway
This week helped me understand that even without deep learning, traditional machine learning models combined with proper preprocessing can achieve strong performance on image classification tasks. It strengthened my understanding of end-to-end ML workflows and model evaluation strategies.

