# MACHINE LEARNING LAB EXERCISE 7 -- 24BAD060

## Objective

Implement, evaluate, and compare **K-Means Clustering** and **Gaussian Mixture Models (GMM)** on a customer dataset to discover segments based on annual income and spending behavior. Analyze model performance using intrinsic metrics and visualize cluster structures and probability densities.

---

## Scenarios

### Scenario 1 -- Customer Segmentation using K-Means Clustering

Group retail customers into distinct segments using K-Means to identify spending patterns.

- **Dataset:** `Mall_Customers.csv`
- **Selected Features:** `Annual Income (k$)`, `Spending Score (1-100)`
- **Target:** Unsupervised (Customer Segments)

#### Pipeline

1. Load and inspect the dataset (`head`, `shape`, null-check).
2. Select relevant features: Annual Income and Spending Score.
3. Visualize feature distributions using histograms.
4. Scale features to a standard range using `StandardScaler`.
5. Determine the optimal number of clusters ($K$) using the **Elbow Method** (testing $K=1$ to $10$).
6. Train the K-Means model with the optimal number of clusters ($K=5$).
7. Assign cluster labels to the original dataset.
8. Visualize the customer segments and their respective cluster centroids using scatter plots.
9. Evaluate the model performance using Inertia and Silhouette Score, and interpret the cluster means.

#### Results

- **Optimal Clusters ($K$):** 5
- **Evaluation Metrics:**
  - Inertia represents the sum of squared distances to the closest cluster centroid.
  - Silhouette Score determines the separation distance between the resulting clusters.
  - Cluster summaries indicate clear distinctions based on High/Low Income vs. High/Low Spending behavior.

---

### Scenario 2 -- Customer Segmentation using Gaussian Mixture Models (GMM)

Apply a probabilistic model (GMM) to the same customer dataset allowing for soft clustering and understanding data distributions.

- **Dataset:** `Mall_Customers.csv`
- **Selected Features:** `Annual Income (k$)`, `Spending Score (1-100)`
- **Target:** Unsupervised (Soft / Hard Customer Segments)

#### Pipeline

1. Initialize and train a `GaussianMixture` model with 5 components.
2. Predict soft assignments (probabilities of belonging to each cluster).
3. Extract hard assignments (definitive labels) and append them to the dataset.
4. Evaluate the model using probabilistic metrics: Log-Likelihood, *Akaike Information Criterion (AIC)*, and *Bayesian Information Criterion (BIC)*.
5. Compute the Silhouette Score for the GMM hard assignments.
6. Visualize the clusters with scatter plots (Hard Assignment).
7. Generate an advanced Contour Density Plot showing the probability distributions of the clusters.
8. Perform a side-by-side visual comparison between K-Means and GMM clustering results.

#### Results

- **Evaluation Metrics:**
  - Log-Likelihood measures the goodness of fit of the model.
  - AIC / BIC scores evaluate model quality by penalizing model complexity.
  - Compared clustering assignments side-by-side with K-Means showcasing density-based nuances.

---

## Visualizations

- Feature Distributions (Income & Spending Score Histograms)
- Elbow Method Curve (Inertia vs $K$)
- K-Means Cluster Scatter Plot
- K-Means Cluster Centroids Plot
- GMM Clustering Scatter Plot (Soft → Hard Assignment)
- GMM Probability Density Contour Plot
- K-Means vs GMM Side-by-Side Comparison Plot

---

## Tech Stack

| Component      | Tool / Library                     |
|----------------|------------------------------------|
| Language       | Python                             |
| Data Handling  | Pandas, NumPy                      |
| Visualization  | Matplotlib, Seaborn                |
| ML Algorithms  | Scikit-learn (KMeans, GaussianMixture)  |
| Preprocessing  | StandardScaler, silhouette_score   |

---

## How to Run

1. Ensure Python 3.x is installed along with the required libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn
   ```
2. Place the dataset (`Mall_Customers.csv`) in the same root project directory.
3. Open and run `L7.ipynb` in Jupyter Notebook, JupyterLab, or VS Code.

---

## Project Structure

```text
24BAD060_ML_EXP7/
|-- L7.ipynb                           # Main notebook for clustering implementations
|-- Mall_Customers.csv                 # Customer dataset
|-- README.md                          # Project documentation
```