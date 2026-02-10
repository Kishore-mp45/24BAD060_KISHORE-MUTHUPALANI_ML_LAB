# ML Experiment 3 — Regression Analysis

> **Roll No:** 24BAD060

## Objective

Explore and compare regression techniques on two real-world datasets:

| Scenario | Technique | Dataset |
|----------|-----------|---------|
| 1 | Multiple Linear Regression (+ Ridge & Lasso) | Student Performance |
| 2 | Polynomial Regression (+ Ridge Regularization) | Auto MPG |

---

## Datasets

### 1. Student Performance (`StudentsPerformance.csv`)

- **Records:** 1,000
- **Features:** gender, race/ethnicity, parental level of education, lunch type, test preparation course
- **Target:** `final_score` (average of math, reading, and writing scores)
- **Null Values:** None

### 2. Auto MPG (`auto-mpg.csv`)

- **Records:** 398
- **Features:** horsepower (used as single predictor)
- **Target:** `mpg` (miles per gallon)
- **Preprocessing:** Non-numeric horsepower values coerced and imputed with mean

---

## Workflow

### Scenario 1 — Multiple Linear Regression

1. Load and explore the Student Performance dataset
2. One-hot encode categorical features (`pd.get_dummies`)
3. Engineer target variable (`final_score` = mean of three scores)
4. Split data (80/20 train-test, `random_state=42`)
5. Standardize features using `StandardScaler`
6. Train and evaluate **Linear Regression**, **Ridge**, and **Lasso** models
7. Analyze feature coefficients
8. Visualize results (Actual vs Predicted, Coefficient bar chart, Residual distribution)

### Scenario 2 — Polynomial Regression

1. Load and clean the Auto MPG dataset
2. Select `horsepower` as the single feature, `mpg` as target
3. Handle missing values and scale features
4. Split data (80/20 train-test, `random_state=42`)
5. Fit polynomial regression for degrees **2, 3, and 4**
6. Apply **Ridge regularization** (degree 4)
7. Compare performance across degrees
8. Visualize regression curves and training vs testing error

---

## Results

### Scenario 1 — Student Performance

| Model | R² Score |
|-------|----------|
| Linear Regression | 0.1622 |
| Ridge (alpha=1.0) | 0.1621 |
| Lasso (alpha=0.1) | 0.1557 |

**Top positive predictors:** standard lunch (+4.38), race/ethnicity group E (+2.10)
**Top negative predictors:** no test preparation (-3.75), male gender (-2.04)

### Scenario 2 — Auto MPG

| Degree | MSE | RMSE | R² Score |
|--------|-----|------|----------|
| 2 | 18.42 | 4.29 | 0.6392 |
| 3 | 18.46 | 4.30 | 0.6383 |
| 4 | 18.27 | 4.27 | 0.6421 |
| 4 + Ridge | — | — | 0.6413 |

Degree 4 polynomial achieves the best fit; Ridge regularization maintains comparable performance while reducing overfitting risk.

---

## Visualizations

- **Actual vs Predicted Scatter Plot** — Student Performance
- **Feature Coefficient Bar Chart** — Student Performance
- **Residual Distribution Histogram** — Student Performance
- **Polynomial Curve Fitting Plot** — Auto MPG
- **Training vs Testing Error Line Plot** — Auto MPG

---

## Tech Stack

| Library | Purpose |
|---------|---------|
| `pandas` | Data loading and manipulation |
| `numpy` | Numerical operations |
| `matplotlib` | Plotting and visualization |
| `seaborn` | Statistical visualizations |
| `scikit-learn` | Regression models, preprocessing, evaluation |

---

## How to Run

1. Open the notebook in **Google Colab** or **Jupyter Notebook**
2. Ensure the datasets (`StudentsPerformance.csv`, `auto-mpg.csv`) are accessible
3. Run all cells sequentially

---

## Project Structure

```
24BAD060_ML_EXP_3/
├── 24BAD060_ML_EXP_3.ipynb   # Main experiment notebook
├── StudentsPerformance.csv    # Dataset for Scenario 1
├── auto-mpg.csv               # Dataset for Scenario 2
└── README.md                  # Project documentation
```
