# Pima Indians Diabetes Prediction — SVM Classifier

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)

A machine learning notebook developed to **analyze and predict diabetes** among Pima Indian women using clinical and biometric data.  
This version focuses on the **Support Vector Machine (SVM)** model — exploring how kernel choice, regularization, and validation strategy affect performance.

---

## 📜 Overview

This project demonstrates a **complete ML workflow**:
- Data preprocessing (imputation + scaling)
- Hyperparameter tuning with **GridSearchCV**
- Multiple **cross-validation** strategies
- Confusion matrix + classification report visualization

Fully compatible with **Google Colab**, and designed to be modular, readable, and extendable.

---

## Objectives

- Compare **KFold** vs **StratifiedKFold**  
- Test kernels: `linear`, `rbf`, `poly`, `sigmoid`  
- Optimize **C** and **gamma**  
- Evaluate **precision**, **recall**, **F1-score**  
- Build a reproducible ML pipeline  

---

## 📊 Dataset

**Source:**  
[Pima Indians Diabetes Database (Kaggle)](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database)

**Description:**  
768 female patients (21+ years old) with diagnostic measurements.  
Goal: **Predict diabetes (0/1)**.

---

## Methodology

### 1. Preprocessing
- Replace missing/zero values via **median imputation**
- Apply `StandardScaler()`  
- Use `class_weight="balanced"` for fairness  

### 2. Modeling (SVM)
- `SVC()`  
- Tuned parameters:  
  - **C** (regularization)  
  - **gamma** (kernel coefficient)  
  - **kernel** type  

### 3. Cross-Validation
- `KFold(10)` — general estimation  
- `StratifiedKFold(3)` — maintains label proportion  

### 4. Metrics
- Accuracy  
- Precision  
- Recall  
- F1-score  
- Confusion Matrix  

### 5. Reporting & Export
- Classification report → DataFrame  
- `.joblib` model export  

---

## 📈 Results Summary

| Model / CV | Kernel | Accuracy | F1 | Recall | CV Type |
|-------------|---------|-----------|------|----------|----------|
| SVM | RBF | ≈ 75.3% | 0.74 | 0.72 | KFold(10) |
| SVM | RBF | ≈ 72.0% | 0.71 | 0.68 | StratifiedKFold(3) |
| Fixed RBF (C=10, γ=0.01) | RBF | ≈ 76.4% | 0.75 | 0.73 | Hold-out |

**Top Features:**  
- Glucose  
- BMI  
- Age  

---

## Insights

- Stratified CV is essential for medical data  
- RBF kernel provides best bias–variance balance  
- Recall is more critical than accuracy in healthcare  
- Feature scaling strongly improves SVM performance  

---

## Tech Stack

- Python 3.10+  
- scikit-learn  
- pandas  
- numpy  
- seaborn  
- matplotlib  
- joblib  

---

## 👤 Authors

**Mauro Junior**, **Julio Franz**, **Pablo Souza**, **Victor Teixeira**, **Matheus Herique**, **Fabiano Menegidio**  
🔗 LinkedIn: https://www.linkedin.com/feed/update/urn:li:activity:7379939858934476800/

---

## Poster

<img width="757" height="932" alt="poster" src="https://github.com/user-attachments/assets/fbf4fb6f-0b20-4c5d-a7d3-1f5cd8b62220" />
