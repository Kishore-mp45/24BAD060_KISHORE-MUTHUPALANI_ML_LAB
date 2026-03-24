# 🚀 Machine Learning Lab Exercise 6: Ensemble Techniques & SMOTE

Welcome to **Lab Exercise 6**, a comprehensive exploration of advanced machine learning concepts, specifically focusing on **Ensemble Learning Techniques** and **Handling Imbalanced Datasets** using SMOTE.

**Student Roll No:** `24BAD060`

---

## 📖 Overview

This notebook implements multiple scenarios addressing real-world datasets with different ensemble methods and data balancing strategies. The primary goal is to evaluate the performance improvement and robustness offered by Bagging, Boosting, Random Forests, Stacking, and the Synthetic Minority Over-sampling Technique (SMOTE).

## 🧪 Experimental Scenarios

### 1️⃣ Scenario 1: Bagging (Diabetes Prediction)
- **Dataset:** `diabetes_bagging.csv`
- **Objective:** Predict the onset of diabetes based on diagnostic measures.
- **Models Used:** Decision Tree vs. Bagging Classifier
- **Key Metrics:** Accuracy comparison and Confusion Matrix evaluation.

### 2️⃣ Scenario 2: Boosting (Customer Churn)
- **Dataset:** `churn_boosting.csv`
- **Objective:** Identify customers likely to churn.
- **Models Used:** AdaBoost vs. Gradient Boosting
- **Key Metrics:** Accuracy, ROC Curve (AUC comparison), and Feature Importance visualization.

### 3️⃣ Scenario 3: Random Forest (Income Prediction)
- **Dataset:** `income_random_forest.csv`
- **Objective:** Predict income levels based on demographic data.
- **Models Used:** Random Forest Classifier
- **Key Focus:** Evaluating model accuracy against the variance in the number of decision trees (`n_estimators`).

### 4️⃣ Scenario 4: Stacking (Heart Disease Prediction)
- **Dataset:** `heart_stacking.csv`
- **Objective:** Assess the likelihood of heart disease in patients.
- **Models Used:** Base models (Logistic Regression, SVM, Decision Tree) combined into a Stacking Classifier (Meta-Learner: Logistic Regression).
- **Key Metrics:** Comparative model visualization and stacking generalization evaluation.

### 5️⃣ Handling Class Imbalance with SMOTE (Fraud Detection)
- **Dataset:** `fraud_smote.csv`
- **Objective:** Detect fraudulent transactions in a highly imbalanced dataset.
- **Technique:** Synthetic Minority Over-sampling Technique (SMOTE).
- **Model Used:** Random Forest Classifier.
- **Key Metrics:** Classification Reports and Precision-Recall Curve (AUC) evaluation before and after applying SMOTE.

---

## 🛠️ Technologies Used
- **Python 3**
- **Pandas & NumPy:** Data Manipulation and Analysis.
- **Matplotlib & Seaborn:** Data Visualization.
- **Scikit-Learn:** Machine Learning Models and Evaluation Metrics.
- **Imbalanced-Learn (imblearn):** Implementation of the SMOTE Technique.

## ⚙️ How to Run
1. Ensure your environment supports Jupyter Notebooks (e.g., JupyterLab, VS Code, or Google Colab).
2. Install the necessary Python dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn
   ```
3. Place the `24BAD060_ML_EXP6.ipynb` notebook and all required datasets in the same working directory:
   - `diabetes_bagging.csv`
   - `churn_boosting.csv`
   - `income_random_forest.csv`
   - `heart_stacking.csv`
   - `fraud_smote.csv`
4. Open and execute the notebook cell-by-cell to observe model evaluations, performance metrics, and visualizations.

---
*Created as part of the Machine Learning Lab coursework.*
