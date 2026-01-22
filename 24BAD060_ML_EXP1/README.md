# Machine Learning Experiment 1: Exploratory Data Analysis (EDA)

A comprehensive exploratory data analysis project analyzing four real-world datasets to understand data characteristics, identify missing information, and visualize key patterns.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Datasets](#datasets)
- [Scenarios](#scenarios)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Key Findings](#key-findings)
- [Technologies Used](#technologies-used)
- [Author](#author)

---

## 🎯 Overview

This project performs exploratory data analysis (EDA) on four diverse datasets from Kaggle, covering domains such as e-commerce, healthcare, real estate, and banking. The analysis focuses on:

- Understanding data structure and characteristics
- Identifying and handling missing values
- Visualizing distributions and relationships
- Extracting meaningful insights from each dataset

---

## 📊 Datasets

| Scenario | Dataset | Source | Records |
|----------|---------|--------|---------|
| 1 | E-commerce Sales Data | [Kaggle](https://www.kaggle.com/datasets/carrie1/ecommerce-data) | ~541K |
| 2 | Pima Indians Diabetes | [Kaggle](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database) | 768 |
| 3 | Housing Price Prediction | [Kaggle](https://www.kaggle.com/datasets/harishkumardatalab/housing-price-prediction) | 545 |
| 4 | Customer Personality Analysis | [Kaggle](https://www.kaggle.com/datasets/imakash3011/customer-personality-analysis) | 2,240 |

---

## 📁 Scenarios

### Scenario 1: E-commerce Sales Data
**Objective:** Analyze e-commerce transactions to understand product categories, sales trends, and identify missing information.

**Key Analysis:**
- Transaction patterns and trends
- Product category distribution
- Customer purchase behavior
- Missing value detection in order details

---

### Scenario 2: Hospital Patient Records (Diabetes Dataset)
**Objective:** Examine patient health metrics to identify missing data and visualize health indicator distributions.

**Key Analysis:**
- Distribution of health metrics (Glucose, BMI, Blood Pressure, etc.)
- Identification of zero/missing values in medical measurements
- Correlation between health indicators
- Diabetes outcome analysis

---

### Scenario 3: Housing Dataset
**Objective:** Investigate housing features to understand relationships between house attributes and identify missing data.

**Key Analysis:**
- Price distribution analysis
- Feature correlations (area, bedrooms, bathrooms, etc.)
- Categorical feature analysis (furnishing status, location preferences)
- Missing value patterns in property features

---

### Scenario 4: Banking Customer Data
**Objective:** Analyze customer demographics and detect missing account information in banking data.

**Key Analysis:**
- Customer demographic profiling
- Income and spending patterns
- Purchase behavior across channels (web, catalog, store)
- Missing data detection in customer records

---

## 🛠️ Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/ml-eda-experiment.git
   cd ml-eda-experiment
   ```

2. **Create a virtual environment (recommended):**
   ```bash
   python -m venv .venv
   
   # Windows
   .venv\Scripts\activate
   
   # macOS/Linux
   source .venv/bin/activate
   ```

3. **Install required packages:**
   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```

---

## 🚀 Usage

1. **Launch Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```

2. **Open the notebook:**
   - Navigate to `24BAD060_ML_EXP1.ipynb`
   - Run cells sequentially to reproduce the analysis

3. **Datasets:**
   - Ensure all CSV files are in the same directory as the notebook
   - Required files: `data.csv`, `diabetes.csv`, `Housing.csv`, `marketing_campaign.csv`

---

## 📂 Project Structure

```
EXP_1 DATASETS/
│
├── 24BAD060_ML_EXP1.ipynb    # Main Jupyter notebook with all analyses
├── data.csv                   # E-commerce sales dataset
├── diabetes.csv               # Pima Indians diabetes dataset
├── Housing.csv                # Housing price prediction dataset
├── marketing_campaign.csv     # Customer personality analysis dataset
├── README.md                  # Project documentation
└── .venv/                     # Virtual environment (not tracked)
```

---

## 🔍 Key Findings

### Data Quality Insights
- **E-commerce Data:** Contains missing customer IDs and product descriptions requiring attention
- **Diabetes Data:** Several features contain zeros representing missing values (Glucose, Blood Pressure, BMI)
- **Housing Data:** Categorical variables need encoding for advanced analysis
- **Banking Data:** Income field has missing values; age distribution shows diverse customer base

### Analysis Techniques Applied
- ✅ Data loading and initial exploration
- ✅ Missing value analysis and visualization
- ✅ Statistical summary generation
- ✅ Distribution plots and histograms
- ✅ Correlation analysis
- ✅ Categorical variable analysis

---

## 💻 Technologies Used

| Technology | Purpose |
|------------|---------|
| Python 3.x | Programming Language |
| Pandas | Data Manipulation & Analysis |
| NumPy | Numerical Computing |
| Matplotlib | Data Visualization |
| Seaborn | Statistical Visualization |
| Jupyter Notebook | Interactive Development |

---

## 📝 License

This project is for educational purposes. The datasets used are publicly available on Kaggle under their respective licenses.

---

## 👤 Author

**Student ID:** 24BAD060

---

## 🙏 Acknowledgments

- [Kaggle](https://www.kaggle.com/) for providing public datasets
- UCI Machine Learning Repository for the Pima Indians Diabetes dataset
- Course instructors for guidance on EDA techniques

---

*Last Updated: January 2026*
