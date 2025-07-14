# 🏥 H-Predict: Hospital Treatment Cost Prediction Using Machine Learning

## 📌 Overview

**H-Predict** is a supervised machine learning project that predicts hospital treatment costs using real-world inpatient discharge data combined with clinical metadata (procedure and diagnosis codes). The goal is to bring transparency to healthcare costs and enable hospitals, insurers, and patients to make informed decisions.

We built an end-to-end ML pipeline including data preprocessing, feature engineering, model training, hyperparameter tuning, and evaluation. The best-performing model (XGBoost) achieved an R² ≈ 0.90.

---
## 📁 Repository Structure

├── Data270_project.ipynb # Main Jupyter notebook with full ML pipeline

├── README.md # This README file

├── Project ppt and report/ # Presentation slides and final report (PDF, PPTX)

├── PolyandLinearPickles/ # Saved models for Polynomial and Linear Regression

├── XGBoost Pickle/ # Saved tuned XGBoost model (.pkl)

---

## 🚀 Project Objective

- Predict **Total Hospital Charges** using demographic, clinical, and hospitalization data.
- Integrate procedure (`pcode`) and diagnosis (`dcode`) metadata from AHRQ to improve model interpretability.
- Provide a reproducible and explainable ML framework for healthcare cost analytics.

---

## 🛠️ Key Steps

### 1. **Data Preprocessing**
- Merged inpatient discharge data with AHRQ procedure and diagnosis code metadata.
- Handled missing values (columns with >1% nulls dropped; others imputed).
- Detected and removed outliers in **Length of Stay** and **Total Charges** using IQR.
- Converted skewed target (`Total Charges`) using square root transformation.

### 2. **Feature Engineering**
- Ordinal and one-hot encoding of categorical fields.
- Transformed ICD codes into readable medical categories via metadata joins.
- Final dataset: ~1.8 million rows × 170 features.

### 3. **Modeling & Evaluation**
- Models tried:
  - Linear Regression
  - Polynomial Regression
  - Random Forest Regressor
  - Gradient Boosting Regressor
  - **XGBoost Regressor** (best performance)
- Metrics used: MAE, MSE, RMSE, R²
- Final XGBoost model tuned via `GridSearchCV`, R² ≈ 0.90 on test set.

---

## 🧪 Results

| Model               | R² Score | RMSE   |
|--------------------|----------|--------|
| Linear Regression  | ~0.75    | ~40    |
| Polynomial Reg.    | ~0.83    | ~33    |
| Random Forest      | ~0.91    | ~24    |
| Gradient Boosting  | ~0.81    | ~35    |
| **XGBoost (tuned)**| **~0.90**| **~26**|

---

## 💾 Deployment Artifacts

- Saved model files (.pkl) available in:
  - `PolyandLinearPickles/`
  - `XGBoost Pickle/`

These models can be loaded and used for inference or deployment via REST API or dashboards.

---

## 📊 Reports & Visuals

- 📁 `Project ppt and report/` contains:
  - Final PowerPoint Presentation
  - Group Project Report (PDF)

These files summarize project motivation, technical approach, challenges, and outcomes — ideal for academic or stakeholder presentations.

---

## 🧠 Tech Stack

- Python (Pandas, NumPy, Scikit-learn, XGBoost, Matplotlib, Seaborn)
- Jupyter Notebook
- Pickle (for model serialization)

---

## 📌 How to Use

1. Clone the repo  
2. Open `Data270_project.ipynb`  
3. Run all cells to see preprocessing, model training, evaluation  
4. Load pickled models for prediction or integration into applications  

---

## 📬 Contact

For queries or collaborations, open an issue or connect via LinkedIn/GitHub.

---

