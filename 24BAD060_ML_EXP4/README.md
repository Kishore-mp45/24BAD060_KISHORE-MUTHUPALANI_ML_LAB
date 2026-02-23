# Machine Learning Lab Exercise 4 — 24BAD060
## Naive Bayes Classification — SMS Spam Detection & Iris Flower Classification

This project demonstrates two core variants of the Naive Bayes algorithm applied to distinct classification problems:

| Scenario | Algorithm | Dataset | Task |
|----------|-----------|---------|------|
| 1 | Multinomial Naive Bayes | SMS Spam Collection | Text classification (Spam vs Ham) |
| 2 | Gaussian Naive Bayes | Iris | Multi-class flower species classification |

---

## Table of Contents

- [Scenario 1 — Multinomial Naive Bayes (Spam Detection)](#scenario-1--multinomial-naive-bayes-spam-detection)
- [Scenario 2 — Gaussian Naive Bayes (Iris Classification)](#scenario-2--gaussian-naive-bayes-iris-classification)
- [Results Summary](#results-summary)
- [Dependencies](#dependencies)
- [How to Run](#how-to-run)
- [Project Structure](#project-structure)

---

## Scenario 1 — Multinomial Naive Bayes (Spam Detection)

### Objective

Classify SMS messages as **spam** or **ham** (not spam) using the Multinomial Naive Bayes algorithm with TF-IDF feature extraction.

### Dataset

- **Source:** SMS Spam Collection (`spam.csv`)
- **Size:** 5,572 messages (4,825 ham, 747 spam)
- **Features:** Raw SMS text messages
- **Target:** Binary label — `ham` (0) / `spam` (1)

### Pipeline

1. **Data Loading & Cleaning** — Lowercase conversion, punctuation removal
2. **Label Encoding** — `ham` → 0, `spam` → 1
3. **Feature Extraction** — TF-IDF Vectorization with English stop-word removal
4. **Train/Test Split** — 80/20 split (random state = 42)
5. **Model Training** — `MultinomialNB(alpha=1.0)` with Laplace smoothing
6. **Evaluation** — Accuracy, Precision, Recall, F1-Score, Confusion Matrix

### Key Results

| Metric | Score |
|--------|-------|
| Accuracy | 96.77% |
| Precision | 100% |
| Recall | 76% |
| F1-Score | 86.36% |

### Additional Analysis

- **Misclassification Analysis** — Inspection of false negatives to understand model limitations
- **Feature Importance** — Top 20 words influencing spam classification (e.g., `free`, `txt`, `mobile`, `claim`, `prize`, `win`)
- **Word Frequency Comparison** — Visual comparison of top word frequencies in spam vs ham
- **Laplace Smoothing Experiment** — Impact of varying alpha values on accuracy:

  | Alpha | Accuracy |
  |-------|----------|
  | 0.1 | 98.03% |
  | 0.5 | 97.76% |
  | 1.0 | 96.77% |
  | 2.0 | 93.36% |

---

## Scenario 2 — Gaussian Naive Bayes (Iris Classification)

### Objective

Classify iris flowers into three species using Gaussian Naive Bayes on continuous numerical features, and compare performance against Logistic Regression.

### Dataset

- **Source:** Scikit-learn built-in Iris dataset
- **Size:** 150 samples (50 per class, perfectly balanced)
- **Features:** Sepal length, Sepal width, Petal length, Petal width
- **Target:** 3 classes — Setosa (0), Versicolor (1), Virginica (2)

### Pipeline

1. **Data Loading & Inspection** — Summary statistics, class distribution check
2. **Feature Scaling** — StandardScaler normalization
3. **Train/Test Split** — 80/20 split (random state = 42)
4. **Model Training** — `GaussianNB()`
5. **Evaluation** — Accuracy, Classification Report, Confusion Matrix

### Key Results

| Model | Accuracy |
|-------|----------|
| Gaussian Naive Bayes | 100% |
| Logistic Regression | 100% |

### Additional Analysis

- **Class Probability Outputs** — Per-sample posterior probabilities for each species
- **Decision Boundary Visualization** — 2D boundary plot using petal length and petal width
- **Probability Distribution Plot** — KDE plots of petal length across the three species
- **Model Comparison** — Side-by-side accuracy comparison with Logistic Regression

---

## Results Summary

| Scenario | Model | Dataset | Accuracy |
|----------|-------|---------|----------|
| 1 | Multinomial NB (alpha=0.1) | SMS Spam | 98.03% |
| 1 | Multinomial NB (alpha=1.0) | SMS Spam | 96.77% |
| 2 | Gaussian NB | Iris | 100% |
| 2 | Logistic Regression | Iris | 100% |

---

## Dependencies

- Python 3.x
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn

Install all dependencies:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn
```

---

## How to Run

1. Clone the repository or download the project files.
2. Ensure `spam.csv` is present in the working directory.
3. Open the notebook:

```bash
jupyter notebook 24BAD060_ML_EXP4.ipynb
```

4. Run all cells sequentially.

---

## Project Structure

```
.
├── 24BAD060_ML_EXP4.ipynb   # Main notebook with both scenarios
├── spam.csv                  # SMS Spam Collection dataset
└── README.md                 # Project documentation
```
