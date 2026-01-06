# WiDS 5.0 – End-to-End Machine Learning Project  
## PlantVillage Disease Classification

**Name:** Sugandh Kumar  
**Roll Number:** 24B0357  
**Program:** WiDS 5.0 (Winter in Data Science)  
**Project Type:** End-to-End Machine Learning / Deep Learning  

---

## 📌 Project Overview

This repository contains my complete submission for **WiDS 5.0 End-to-End Machine Learning**, where I worked on the **PlantVillage leaf disease classification dataset**.

The objective of this project was to build a **full ML/DL pipeline**, starting from raw image data and ending with trained and evaluated models, while understanding the challenges involved in real-world image classification tasks.

---

## 🎯 Problem Statement

Given an image of a plant leaf, the goal is to **classify the disease category correctly**.

Key challenges include:
- High number of classes
- Visual similarity between different diseases
- Variations in lighting, texture, and leaf shape
- Risk of overfitting due to complex models

---

## 📂 Dataset

- **Dataset:** PlantVillage
- **Type:** Image dataset
- **Classes:** Multiple plant–disease combinations
- **Input:** RGB leaf images
- **Output:** Disease class label

---

## 🧠 Project Workflow

The project was completed in a **step-by-step end-to-end manner**, as outlined below:

---

### 1️⃣ Exploratory Data Analysis (EDA)

- Explored dataset structure and class distribution
- Visualized sample images from different classes
- Identified class imbalance and inter-class similarity
- Understood why plant disease classification is a challenging task

📄 Notebook: `01_eda.ipynb`

---

### 2️⃣ Data Preprocessing

- Image resizing and normalization
- Train–validation–test split with stratification
- Conversion of labels into numerical format
- Efficient data loading for model training

📄 Notebook: `02_preprocessing.ipynb`

---

### 3️⃣ Baseline Model (Classical ML / Shallow Model)

- Built a **simple baseline model** to set a performance benchmark
- Used flattened image features
- Observed **underfitting and limited generalization**
- Achieved baseline accuracy of approximately **0.67**

📄 Notebook: `03_baseline_model.ipynb`

---

### 4️⃣ Convolutional Neural Network (CNN)

- Designed a custom CNN architecture
- Trained model using image batches
- Observed:
  - Faster learning
  - Better feature extraction
  - Signs of overfitting after multiple epochs

📄 Notebook: `04_simple_cnn.ipynb`

---

### 5️⃣ Transfer Learning

- Used a **pretrained CNN model**
- Froze initial layers and fine-tuned later layers
- Achieved significantly better generalization
- Evaluated using:
  - Accuracy
  - Confusion Matrix
  - Validation performance

📄 Notebook: `05_transfer_learning.ipynb`

---

### 6️⃣ Model Evaluation

- Compared baseline, CNN, and transfer learning models
- Analyzed training vs validation accuracy
- Used confusion matrices to understand misclassifications
- Identified class-level performance issues

---

## 📊 Results Summary

| Model Type            | Accuracy |
|----------------------|----------|
| Baseline Model       | ~0.67    |
| Simple CNN           | Improved |
| Transfer Learning    | Best     |

> Transfer learning performed the best due to pretrained feature extraction and better generalization.

---

## 📝 Learnings & Observations

All key insights, challenges, mistakes, and takeaways are documented in detail here:

📄 **[`learnings.md`](learnings.md)**

This includes:
- Why EDA is critical
- Overfitting vs underfitting insights
- Why CNNs outperform classical ML for images
- Importance of validation accuracy
- Real-world ML challenges

---

## 🛠️ Tools & Technologies Used

- Python
- NumPy, Pandas
- Matplotlib, Seaborn
- Scikit-learn
- TensorFlow / Keras
- Jupyter Notebook

---

## 🚀 Conclusion

This project helped me gain hands-on experience with:
- End-to-end ML pipelines
- Image-based classification
- CNNs and transfer learning
- Model evaluation and interpretation

Overall, WiDS 5.0 strengthened my understanding of **practical machine learning beyond theory**.

---

## 📌 Repository Structure

```text
├── notebooks/
│   ├── 01_eda.ipynb
│   ├── 02_baseline_model.ipynb
│   ├── 03_cnn.ipynb
├── learnings.md
├── README.md
