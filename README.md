# Gender-Detection-Using-Speech-Analysis-and-Classification
MSc Project: High-accuracy gender detection system using speech signal analysis (MFCC), Principal Component Analysis (PCA), data upscaling, and Machine Learning classifiers (achieving 99.51% accuracy with KNN).

This repository contains the source code, implementation, and final report for my MSc Advanced Computer Science Master's Project at the University of Hertfordshire. The project implements an automated Gender Detection System using speech processing and machine learning techniques.

### Key Highlights:
Feature Extraction: Utilizes Mel-Frequency Cepstral Coefficients (MFCC) via librosa at a 16kHz sample rate.

Data Preprocessing & Normalization: Employs Principal Component Analysis (PCA) for outlier identification and data normalization.

Data Upscaling: Leverages resampling/upscaling techniques to enhance resolution and model performance.

Machine Learning Classifiers: Evaluates K-Nearest Neighbors (KNN), Linear SVC, Logistic Regression, Gradient Boosting, and Decision Tree classifiers.

Performance: The KNN classifier achieved a peak detection accuracy of 99.51%, outperforming baseline models and existing literature approaches.


---

## 📋 Table of Contents
- [About the Project](#about-the-project)
- [Research Objectives & Questions](#research-objectives--questions)
- [Dataset & Methodology](#dataset--methodology)
- [Machine Learning Models & Results](#machine-learning-models--results)
- [Tech Stack & Dependencies](#tech-stack--dependencies)
- [Project Structure](#project-structure)
- [Author & Acknowledgements](#author--acknowledgements)

---

## 🎯 About the Project
Speech processing is a vital field in signal processing with broad applications. This project investigates the challenges of distinguishing between male and female speech patterns, particularly when fundamental frequencies overlap, by combining digital signal processing (DSP) with supervised machine learning classifiers. 

Through robust feature extraction, data normalization, and upscaling techniques, the final model achieved an exceptional accuracy of **99.51%** using the K-Nearest Neighbors (KNN) classifier.

---

## ❓ Research Questions
1. **RQ-1:** How does the process of feature extraction influence the detection of gender through speech analytics?
2. **RQ-2:** Which model can detect gender from speech signals, and how does it improve the research approach compared to existing models?

---

## ⚙️ Dataset & Methodology

### 1. Data Collection & Preprocessing
* **Source:** Collected from Kaggle, comprising audio recordings split into **one-sentence** (671 files) and **multiple-sentence** (1,778 files) directories[cite: 2].
* **Metadata Linking:** Unlabeled audio files were successfully labeled by extracting file IDs and cross-referencing them with demographic metadata (`BVC_Voice_Bio_Public.xlsx`).

### 2. Feature Extraction
* **MFCC:** Extracted acoustic features using **Mel-Frequency Cepstral Coefficients (MFCC)** via the `librosa` library at a sample rate of **16,000 Hz** (`res_type='kaiser_fast'`).

### 3. Dimensionality Reduction & Normalization
* **PCA & Outlier Handling:** Principal Component Analysis (PCA) was utilized to identify and handle data outliers, followed by standard scaling/normalization to prevent classifier overfitting.
* **Data Upscaling:** To overcome limitations from low data instances, upscaling/resampling was applied to increase data resolution and enhance model learning stability.

---

## 📊 Machine Learning Models & Results

The project evaluated five machine learning classifiers from different algorithm families, trained and tested on an 80:20 split:

* **K-Nearest Neighbors (KNN)** 🏆 *(Best Performing)*
* **Linear Support Vector Classifier (Linear SVC)**
* **Logistic Regression**
* **Gradient Boosting**
* **Decision Tree**

### Performance Summary (Upscaled Data):
| Classifier | Accuracy (%) | Precision (%) | Recall (%) | F1-Score (%) |
| :--- | :---: | :---: | :---: | :---: |
| **K-Neighbors** | **99.51** | **99.51** | **99.51** | **99.51** |
| **Linear SVC** | 76.01 | 76.01 | 76.01 | 76.01 |
| **Logistic Regression** | 75.81 | 75.85 | 75.81 | 75.81 |
| **Gradient Boosting** | 75.60 | 75.77 | 75.60 | 75.51 |
| **Decision Tree** | 69.95 | 72.94 | 69.95 | 68.67 |

*The **KNN classifier** significantly outperformed previous baseline literature approaches, achieving a peak accuracy of **99.51%**.*

---

## 🧰 Tech Stack & Dependencies
* **Programming Language:** Python
* **Audio Processing:** `librosa`, `scipy`
* **Data Manipulation & Analytics:** `pandas`, `numpy`
* **Machine Learning:** `scikit-learn` (KNN, SVM, Logistic Regression, Decision Tree, Ensemble methods)
* **Visualization:** `matplotlib`, `seaborn`, `plotly`

---

## 📂 Project Structure
```text
├── one_sentence/              # Audio files containing single sentences
├── multiple_sentences/        # Audio files containing multiple sentences
├── BVC_Voice_Bio_Public.xlsx  # Metadata file for speaker identification
├── Feature_Data.csv           # Extracted feature dataset
├── Final_Project_Report.pdf   # Complete documentation / thesis report
└── project_code.py            # Main Python implementation script
