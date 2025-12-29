# Predictive Maintenance of Oil & Gas Pipelines Using Machine Learning

Machine learning–based predictive maintenance system for oil and gas pipelines using multiple classification models and XGBoost.

---

## 📌 Project Overview

This project presents a machine learning–based predictive maintenance framework for classifying oil and gas pipeline condition into **Normal**, **Moderate**, and **Critical** states. The objective is to support **condition-based maintenance** by identifying high-risk pipelines using operational, material, and environmental data available **prior to failure**.

Multiple supervised classification models were developed and systematically compared, with particular emphasis on **safety-aware evaluation**, data leakage prevention, and practical interpretability.

---

## 🎯 Objectives

- Develop a realistic predictive maintenance model for pipeline condition assessment  
- Prevent data leakage through informed feature selection and preprocessing  
- Compare multiple machine learning models under a consistent pipeline  
- Prioritize recall for **Critical** pipeline conditions due to safety implications  
- Demonstrate applied machine learning skills in an industrial context  

---

## 🗂️ Dataset Description

The dataset consists of simulated oil and gas pipeline operational data representing typical industrial conditions.

### Feature Categories

- **Numerical Features**
  - Pipe diameter  
  - Wall thickness  
  - Maximum operating pressure  
  - Operating temperature  
  - Corrosion impact  
  - Service time  

- **Categorical Features**
  - Pipeline material  
  - Pipeline grade  

### Target Variable

- `Condition`:  
  - Normal  
  - Moderate  
  - Critical  

⚠️ Variables directly defining pipeline condition (e.g., thickness loss, material loss percentage) were **intentionally excluded** to prevent data leakage.


### Data Source

The dataset used in this project was obtained from Kaggle (Predictive maintenance oil and gas pipeline data). The original data was further cleaned, processed, and adapted for this predictive maintenance task.
---

## ⚙️ Methodology

### 1. Data Preparation
- Stratified train–test split to preserve class distribution  
- Target variable encoded using label encoding  
- Preprocessing applied **after splitting** to avoid information leakage  

### 2. Preprocessing Pipeline
Implemented using `scikit-learn` pipelines:
- Numerical features scaled using `StandardScaler`
- Categorical features encoded using `OneHotEncoder`
- No dimensionality reduction applied to preserve interpretability  

### 3. Models Evaluated
The following supervised classification models were trained and compared:

- Logistic Regression  
- Support Vector Machine (SVM)  
- Random Forest  
- XGBoost  

All models used the **same preprocessing pipeline** to ensure a fair comparison.

### 4. Evaluation Strategy
- Accuracy  
- Precision  
- Recall  
- F1-score  
- Confusion matrices  

📌 **Recall for the Critical class was prioritized**, as false negatives represent significant safety and operational risks.

---

## 📊 Results Summary

- Tree-based models outperformed linear models, indicating nonlinear relationships in pipeline degradation.
- XGBoost achieved the best balance between overall performance and class-wise stability.
- Most misclassifications occurred between Moderate and Critical classes, reflecting the gradual nature of degradation.
- Very few Critical pipelines were misclassified as Normal, supporting safe maintenance decisions.

---

## 🧠 Model Selection

**XGBoost** was selected as the final model due to:
- High recall for Critical pipeline conditions  
- Strong overall F1-score  
- Robust performance across all classes  

Feature importance analysis confirmed that influential predictors aligned with known engineering principles such as corrosion impact, operating pressure, and service time.

---

## 🛠️ Technologies Used

- Python  
- pandas, numpy  
- scikit-learn  
- xgboost  
- matplotlib, seaborn  

---

## ⚠️ Limitations

- Dataset is simulated and may not capture full real-world variability  
- Temporal degradation patterns are not explicitly modeled  
- Results should be validated on real operational data before deployment  

---

## 🚀 Future Work

- Validation using real pipeline sensor data  
- Incorporation of time-series degradation modeling  
- Integration of explainability techniques (e.g., SHAP values)  
- Deployment within asset management or monitoring systems  

---
## 📁 Repository Structure

predictive-maintenance-pipelines/ │ ├── README.md                # Project overview and documentation ├── requirements.txt         # Python dependencies ├── .gitignore               # Git ignore rules ├── LICENSE                  # MIT License │ ├── data/                    # Dataset files (from Kaggle, cleaned) │   └── pipeline_data.csv │ ├── notebooks/               # Jupyter notebooks │   └── predictive_maintenance.ipynb │ ├── results/                 # Model outputs and visualizations │   ├── confusion_matrix.png │   └── feature_importance.png │ └── report/                  # Project report └── Predictive_Maintenance_Report.pdf
---
## 👤 Author

**Ayad Ahmed Al-Hababi**

This project was developed as a portfolio demonstration of applied machine learning for predictive maintenance in industrial systems.

---

## 📜 License

This project is licensed under the **MIT License**.


