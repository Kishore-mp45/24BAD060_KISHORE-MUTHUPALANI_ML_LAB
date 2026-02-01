# Machine Learning Lab Exercise 2

**Roll Number:** 24BAD060  
**Subject:** Machine Learning Laboratory  
**Experiment:** 02

---

## 📋 Overview

This repository contains the implementation of **Machine Learning Lab Exercise 2**, which focuses on supervised learning techniques including **Linear Regression** and **Logistic Regression**. The experiment demonstrates data preprocessing, model training, evaluation, and visualization using real-world datasets.

---

## 📁 Repository Structure

```
24BAD060_ML_EXP2/
│
├── 24BAD060_ML_EXP_2.ipynb    # Main Jupyter Notebook
├── bottle.csv                  # Dataset for Scenario 1
├── cast.csv                    # Dataset for Scenario 1
├── LICI - minute ata.csv       # Dataset for Scenario 2
└── README.md                   # Documentation
```

---

## 🎯 Objectives

1. Understand and implement **Linear Regression** for continuous value prediction
2. Understand and implement **Logistic Regression** for binary classification
3. Perform **Exploratory Data Analysis (EDA)** on datasets
4. Apply **data preprocessing** techniques including handling missing values and feature scaling
5. Evaluate model performance using appropriate **metrics and visualizations**
6. Implement **regularization techniques** (Ridge and Lasso Regression)
7. Perform **hyperparameter tuning** using Grid Search Cross-Validation

---

## 🔬 Experiments

### Scenario 1: Linear Regression — Ocean Water Temperature Prediction

#### Dataset
- **Source:** CalCOFI Oceanographic Dataset (`bottle.csv`, `cast.csv`)
- **Target Variable:** Water Temperature (`T_degC`)
- **Features:** Depth, Salinity, Dissolved Oxygen, Latitude, Longitude

#### Methodology
1. **Data Loading & Exploration**
   - Loaded and examined both datasets
   - Performed statistical analysis using `describe()`, `info()`
   - Identified missing values

2. **Data Preprocessing**
   - Merged `bottle` and `cast` datasets on `Cst_Cnt`
   - Handled missing values using mean imputation
   - Applied **StandardScaler** for feature normalization
   - Split data into training (80%) and testing (20%) sets

3. **Model Training**
   - Implemented **Linear Regression** model
   - Applied **Ridge Regression** (α = 1) for L2 regularization
   - Applied **Lasso Regression** (α = 0.1) for L1 regularization

4. **Evaluation Metrics**
   - Mean Squared Error (MSE)
   - Root Mean Squared Error (RMSE)
   - R² Score (Coefficient of Determination)

5. **Visualizations**
   - Actual vs Predicted Temperature Scatter Plot
   - Residual Plot Analysis
   - Correlation Heatmap

---

### Scenario 2: Logistic Regression — Stock Price Movement Classification

#### Dataset
- **Source:** LICI Stock Minute Data (`LICI - minute ata.csv`)
- **Target Variable:** Price Movement (1 = Increase, 0 = Decrease)
- **Features:** Open, High, Low, Volume

#### Methodology
1. **Data Loading & Exploration**
   - Loaded stock market minute-level data
   - Performed exploratory data analysis
   - Checked for missing values and data types

2. **Feature Engineering**
   - Created binary target variable based on price movement
   - Selected relevant features for classification

3. **Data Preprocessing**
   - Handled missing values using mean imputation
   - Applied **StandardScaler** for feature normalization
   - Split data into training (80%) and testing (20%) sets

4. **Model Training**
   - Implemented **Logistic Regression** classifier
   - Performed **Hyperparameter Tuning** using GridSearchCV
   - Tested regularization parameter `C`: [0.01, 0.1, 1, 10]

5. **Evaluation Metrics**
   - Accuracy Score
   - Precision Score
   - Recall Score
   - F1 Score
   - ROC-AUC Score

6. **Visualizations**
   - Confusion Matrix Heatmap
   - ROC Curve with AUC
   - Feature Importance Bar Chart

---

## 🛠️ Technologies & Libraries

| Library | Purpose |
|---------|---------|
| `numpy` | Numerical computations |
| `pandas` | Data manipulation and analysis |
| `matplotlib` | Data visualization |
| `seaborn` | Statistical data visualization |
| `scikit-learn` | Machine learning algorithms and utilities |

---

## 📊 Key Results

### Scenario 1: Linear Regression
- Successfully predicted ocean water temperature based on environmental factors
- Evaluated model performance using MSE, RMSE, and R² Score
- Compared performance across Linear, Ridge, and Lasso Regression models

### Scenario 2: Logistic Regression
- Achieved binary classification of stock price movements
- Optimized model using Grid Search Cross-Validation
- Analyzed feature importance to understand model decisions

---

## 🚀 How to Run

1. **Clone or download** this repository
2. Ensure all required libraries are installed:
   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn
   ```
3. Place the dataset files in the same directory as the notebook
4. Open `24BAD060_ML_EXP_2.ipynb` in Jupyter Notebook or VS Code
5. Run all cells sequentially

---

## 📝 Learning Outcomes

Upon completing this experiment, the following concepts were understood:

- Implementation of **Linear Regression** for regression tasks
- Implementation of **Logistic Regression** for classification tasks
- Importance of **data preprocessing** in machine learning pipelines
- Application of **regularization techniques** to prevent overfitting
- Evaluation of models using appropriate **performance metrics**
- **Hyperparameter optimization** using cross-validation techniques
- Interpretation of results through **data visualization**

---

## 📚 References

1. Scikit-learn Documentation: https://scikit-learn.org/stable/
2. CalCOFI Dataset: https://calcofi.org/
3. Pandas Documentation: https://pandas.pydata.org/docs/

---

## 👤 Author

**Roll Number:** 24BAD060  
**Course:** Machine Learning Laboratory  
**Institution:** Kumaraguru College of Technology

---

*Last Updated: February 2026*
