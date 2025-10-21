# Pima Indians Diabetes Prediction — SVM Classifier

A machine learning notebook developed to **analyze and predict diabetes** among Pima Indian women using clinical and biometric data.  
This version focuses on the **Support Vector Machine (SVM)** model — exploring how kernel choice, regularization, and validation strategy affect performance.

---

## Table of Contents
1. [Overview](#overview)
2. [Objetives](#objetives)
3. [Dataset](#dataset)
4. [Methodology](#methodology)
5. [Results Summary](#results-summary) 
6. [Tech Stack](#tech-stack)
7. [Author](#author)
8. [Poster](#poster)

---

## Overview

This project demonstrates a **complete ML workflow**:
- Data preprocessing with **imputation** and **scaling**
- Hyperparameter tuning using **GridSearchCV**
- Model evaluation using multiple **cross-validation strategies**
- Visualization and performance reporting for reproducibility

The notebook is fully compatible with **Google Colab** and designed to be **modular, readable, and extendable** for future experiments (e.g. Random Forest, Logistic Regression, or Neural Networks).

---

## Objectives

- Compare **KFold** vs **StratifiedKFold** cross-validation on SVM models  
- Evaluate kernel effects: `linear`, `rbf`, `poly`, and `sigmoid`  
- Optimize hyperparameters **C** and **gamma** via grid search  
- Measure generalization through **F1**, **Recall**, and **Precision**  
- Build a **reproducible and exportable pipeline**  

---

## Dataset

**Source:** [Pima Indians Diabetes Database (Kaggle)](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database)

**Description:**  
The dataset contains diagnostic measurements from 768 female patients of Pima Indian heritage — all aged 21 or older.  
The **goal** is to predict whether a patient shows signs of diabetes (binary classification).

---

## Methodology

### 1. Data Preprocessing
- **Imputation:** Missing or zero values replaced using the *median*.
- **Standardization:** `StandardScaler()` applied to normalize feature ranges.
- **Balanced weighting:** `class_weight="balanced"` used to handle class imbalance.

### 2. Modeling
- Core model: **`sklearn.svm.SVC()`**
- Hyperparameter tuning:
  - `C`: regularization strength
  - `gamma`: kernel coefficient (for RBF)
  - `kernel`: `linear`, `rbf`, `poly`, `sigmoid`

### 3. Cross-Validation
- `KFold(n_splits=10)` — general performance
- `StratifiedKFold(n_splits=3)` — preserves label ratio for medical fairness

### 4. Metrics
- **Accuracy**
- **Precision**
- **Recall**
- **F1-score**
- **Confusion Matrix**
- Optional: **ROC-AUC** and **Precision-Recall Curves**

### 5. Reporting
- Automatic creation of a **DataFrame** from the classification report for cleaner visualization.
- Artifacts (`.joblib`) saved for model reuse or deployment.

---

##  Results Summary

| Model / CV | Kernel | Accuracy | F1 | Recall | CV Type |
|-------------|---------|-----------|------|----------|----------|
| SVM | RBF | ≈ 75.3% | 0.74 | 0.72 | KFold(10) |
| SVM | RBF | ≈ 72.0% | 0.71 | 0.68 | StratifiedKFold(3) |
| Fixed RBF (C=10, γ=0.01) | RBF | ≈ 76.4% | 0.75 | 0.73 | Hold-out |

**Top Predictive Features:**  
`Glucose`, `BMI`, and `Age` consistently contribute most to correct predictions.

---

##  Insights

- **Cross-validation choice matters:** Stratified folds are crucial in unbalanced medical data.  
- **Kernel selection:** RBF outperformed others, balancing bias and variance effectively.  
- **Model interpretability:** Although SVMs aren’t inherently explainable, scaling and feature analysis still reveal strong medical correlations.  
- **Clinical relevance:** In healthcare, **Recall > Accuracy** — missing diabetic cases (false negatives) is more harmful than false positives.

---

## Tech Stack

- **Language:** Python 3.10+  
- **Libraries:** `scikit-learn`, `pandas`, `numpy`, `matplotlib`, `joblib`, `seaborn`  
- **Environment:** Google Colab / Jupyter Notebook  

---

## Author

**Mauro Junior**, **Julio Franz**, **Pablo Souza**, **Victor Teixeira**, **Matheus Herique**, **Fabiano Menegidio**  
🔗 [LinkedIn](https://www.linkedin.com/feed/update/urn:li:activity:7379939858934476800/) 

## Poster 

<img width="757" height="932" alt="poster" src="https://github.com/user-attachments/assets/fbf4fb6f-0b20-4c5d-a7d3-1f5cd8b62220" />

