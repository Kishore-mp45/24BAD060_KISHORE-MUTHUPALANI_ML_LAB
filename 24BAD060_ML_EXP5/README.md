# MACHINE LEARNING LAB EXERCISE 5 -- 24BAD060

## Objective

Implement and evaluate **K-Nearest Neighbors (KNN)** and **Decision Tree** classification algorithms on real-world datasets, analyze model performance, and visualize decision boundaries and feature importance.

---

## Scenarios

### Scenario 1 -- KNN Classification (Breast Cancer Detection)

Classify breast tumors as **Malignant** or **Benign** using the Wisconsin Breast Cancer dataset.

- **Dataset:** `breast-cancer.csv` (569 samples, 32 features)
- **Selected Features:** `radius_mean`, `texture_mean`, `perimeter_mean`, `area_mean`, `smoothness_mean`
- **Target:** `diagnosis` (M = Malignant, B = Benign)

#### Pipeline

1. Load and inspect the dataset
2. Select features and encode target labels using `LabelEncoder`
3. Scale features using `StandardScaler`
4. Split data (80/20 train-test split)
5. Train KNN model with `k=5`
6. Evaluate using accuracy, classification report, and confusion matrix
7. Experiment with K values (1-20) to find optimal K
8. Identify misclassified cases
9. Visualize 2D decision boundary using `radius_mean` and `texture_mean`

#### Results

| Metric    | Benign | Malignant |
|-----------|--------|-----------|
| Precision | 0.94   | 0.91      |
| Recall    | 0.94   | 0.91      |
| F1-Score  | 0.94   | 0.91      |

- **Overall Accuracy:** 92.98%
- **Misclassified Cases:** 8

---

### Scenario 2 -- Decision Tree Classification (Loan Approval Prediction)

Predict loan approval status (**Approved / Rejected**) using applicant data.

- **Dataset:** `train_u6lujuX_CVtuZ9i (1).csv` (614 samples, 13 features)
- **Selected Features:** `ApplicantIncome`, `LoanAmount`, `Credit_History`, `Education`, `Property_Area`
- **Target:** `Loan_Status` (Y = Approved, N = Rejected)

#### Pipeline

1. Load and inspect the dataset
2. Select features and handle missing values (median/mode imputation)
3. Encode categorical variables using one-hot encoding (`pd.get_dummies`)
4. Encode target labels using `LabelEncoder`
5. Split data (80/20 train-test split)
6. Train Decision Tree classifier (default parameters)
7. Evaluate using accuracy, classification report, and confusion matrix
8. Analyze feature importance
9. Visualize the full tree structure
10. Experiment with tree depths (1-10) for overfitting analysis

#### Results

| Metric    | Rejected | Approved |
|-----------|----------|----------|
| Precision | 0.60     | 0.75     |
| Recall    | 0.49     | 0.82     |
| F1-Score  | 0.54     | 0.79     |

- **Overall Accuracy:** 70.73%

---

## Visualizations

- Confusion Matrix (both scenarios)
- Accuracy vs K Value curve (KNN)
- 2D Decision Boundary plot (KNN)
- Feature Importance bar chart (Decision Tree)
- Full Tree Structure plot (Decision Tree)
- Train vs Test Accuracy across tree depths -- Overfitting Analysis (Decision Tree)

---

## Tech Stack

| Component      | Tool / Library                     |
|----------------|------------------------------------|
| Language       | Python                             |
| Data Handling  | Pandas, NumPy                      |
| Visualization  | Matplotlib, Seaborn                |
| ML Algorithms  | Scikit-learn (KNN, Decision Tree)  |
| Preprocessing  | StandardScaler, LabelEncoder, get_dummies |

---

## How to Run

1. Ensure Python 3.x is installed along with the required libraries:
   ```
   pip install pandas numpy matplotlib seaborn scikit-learn
   ```
2. Place the datasets (`breast-cancer.csv` and `train_u6lujuX_CVtuZ9i (1).csv`) in the project directory.
3. Open and run `24BAD060_ML_EXP5.ipynb` in Jupyter Notebook or JupyterLab.

---

## Project Structure

```
24BAD060_ML_EXP5/
|-- 24BAD060_ML_EXP5.ipynb            # Main notebook
|-- breast-cancer.csv                  # Breast cancer dataset
|-- train_u6lujuX_CVtuZ9i (1).csv     # Loan approval dataset
|-- README.md                          # Project documentation
```
