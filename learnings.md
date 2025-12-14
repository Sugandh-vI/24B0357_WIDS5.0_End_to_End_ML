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
