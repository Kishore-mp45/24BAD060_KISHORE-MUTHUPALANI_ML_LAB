# MACHINE LEARNING LAB EXERCISE 8 -- 24BAD060

## Objective

Implement, evaluate, and analyze **Association Rule Mining** to discover purchasing patterns in consumer data, and apply **Principal Component Analysis (PCA)** for dimensionality reduction and data visualization. The exercise explores frequent itemsets, market basket analysis metrics (support, confidence, lift), and variance preservation in lower-dimensional transformations.

---

## Scenarios

### Scenario 1 -- Market Basket Analysis using Apriori Algorithm

Discover underlying relationships and frequent item associations from transactional consumer data to understand buying behaviors.

- **Dataset:** `Groceries_dataset.csv`
- **Model:** Apriori Algorithm
- **Target:** Unsupervised (Frequent Itemsets & Association Rules)

#### Pipeline

1. Load and inspect the Groceries dataset.
2. Group records by member and convert the item descriptions into a list of transactions.
3. Encode the transaction dataset using `TransactionEncoder` to structurally represent transactions.
4. Apply the `apriori` algorithm to find frequent itemsets based on a minimum support threshold (e.g., `0.02`).
5. Generate association rules derived from the frequent itemsets based on metrics like `confidence`.
6. Filter models to isolate "strong" rules (e.g., confidence > 0.5, lift > 1).
7. Visualize top frequent itemsets using bar charts.
8. Visualize Support vs. Confidence correlations with scatter plots.
9. Construct a directed network graph showcasing connections between antecedents and consequents.

#### Results

- Successfully identified frequent individual items and combinations.
- **Evaluation Metrics:** 
  - **Support:** Measured itemset occurrence frequency.
  - **Confidence:** Identified conditional likelihoods between items.
  - **Lift:** Captured the core strength and correlation of associations beyond basic probabilities.
- Visualizations established intuitive visual nodes illustrating how key staple items interlink.

---

### Scenario 2 -- Dimensionality Reduction using Principal Component Analysis (PCA)

Reduce the dimensionality of the Iris dataset to capture the data's core variance while simplifying its representation into 2D and 3D spaces.

- **Dataset:** Iris Dataset (loaded from `sklearn.datasets`)
- **Model:** Principal Component Analysis (PCA)
- **Target:** Unsupervised (Dimensionality Reduction)

#### Pipeline

1. Load the standardized Iris dataset and inspect structural integrity (null checks).
2. Globally scale the feature distribution using `StandardScaler` to prepare for PCA components.
3. Initialize and fit the PCA model across all features.
4. Calculate and report the **Explained Variance Ratio** and **Cumulative Variance**.
5. Plot the Scree Plot and Cumulative Variance curve to aid in choosing minimal sufficient components.
6. Initialize separate `PCA(n_components=2)` and `PCA(n_components=3)` models.
7. Transform the scaled feature space and plot distinct 2D and 3D projection scatter graphs colored by original target classifications.

#### Results

- **Evaluation Metrics:** 
  - **Explained Variance Ratio** revealed the independent variance weight of each principal component.
  - The **Cumulative Variance** demonstrated how much information is retained by selecting the first $n$ components.
- Reduced a multidimensional dataset efficiently into 2D and 3D planes while preserving cluster separability and spatial distinctions directly observable through the projections.

---

## Visualizations

- Top Frequent Itemsets (Bar Chart)
- Support vs Confidence (Scatter Plot)
- Association Rules Network (Directed Graph via NetworkX)
- PCA Scree Plot (Explained Variance vs Components)
- Cumulative Variance Curve
- 2D PCA Projection (Scatter Plot)
- 3D PCA Projection (3D Scatter Plot)

---

## Tech Stack

| Component      | Tool / Library                     |
|----------------|------------------------------------|
| Language       | Python                             |
| Data Handling  | Pandas, NumPy                      |
| Visualization  | Matplotlib, NetworkX               |
| ML Algorithms  | Scikit-learn (PCA)                 |
| Mining Rules   | mlxtend (Apriori, association_rules, TransactionEncoder) |
| Preprocessing  | StandardScaler                     |

---

## How to Run

1. Ensure Python 3.x is installed along with the required libraries:
   ```bash
   pip install pandas numpy matplotlib networkx scikit-learn mlxtend
   ```
2. Place the dataset (`Groceries_dataset.csv`) in the same root project directory.
3. Open and run `L8.ipynb` in Jupyter Notebook, JupyterLab, or VS Code.

---

## Project Structure

```text
24BAD060_ML_EXP8/
|-- Groceries_dataset.csv              # Groceries transaction dataset
|-- L8.ipynb                           # Main notebook for Apriori and PCA implementations
|-- README.md                          # Project documentation
```
