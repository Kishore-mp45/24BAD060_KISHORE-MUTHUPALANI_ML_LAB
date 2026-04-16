# MACHINE LEARNING LAB EXERCISE 10 -- 24BAD060

## Objective

Implement, evaluate, and compare **Collaborative Filtering Recommendation Systems** using Matrix Factorization techniques: **Truncated Singular Value Decomposition (SVD)** and **Non-Negative Matrix Factorization (NMF)** on a user-movie ratings dataset. Analyze model performance using evaluation metrics like RMSE, MAE, Precision@k, and Recall@k, and visualize latent features and reconstructed matrices.

---

## Scenarios

### Scenario 1 -- Recommendation System using Truncated SVD

Build a collaborative filtering recommendation system using SVD to predict missing movie ratings for users by decomposing the user-item interaction matrix into latent behavioral factors.

- **Dataset:** `ratings.csv`
- **Selected Features:** `userId` (user_id), `movieId` (movie_id), `rating`
- **Target:** Missing Ratings Prediction & Top-N Item Recommendations

#### Pipeline

1. Load the dataset and drop irrelevant features (timestamp).
2. Construct a user-item matrix mapping users to movie ratings.
3. Mean-center the user ratings and handle missing values (NaN to 0).
4. Apply `TruncatedSVD` iteratively to determine the optimal number of latent factors ($K$) varying from 5 to 50 based on the lowest **Root Mean Squared Error (RMSE)**.
5. Decompose the matrix into $U$, $\Sigma$, and $V^T$ components to obtain to the optimal model.
6. Reconstruct the user-movie rating matrix by calculating the dot product and adding the user mean back.
7. Clip the predicted ratings sequentially to boundary constraints ($1$ to $5$).
8. Evaluate the reconstructed values against actual ratings using RMSE and Mean Absolute Error (MAE).
9. Generate personalized Top-N movie recommendations for a specific user based on unrated movies.

#### Results

- **Optimal Latent Factors ($K$):** Identified through the Elbow-like plot of RMSE vs $K$.
- **Evaluation Metrics:**
  - RMSE and MAE highlight the overall accuracy and standard deviation of rating predictions.
  - SVD performs effectively on mean-centered matrices handling global user baselines.

---

### Scenario 2 -- Recommendation System using Non-Negative Matrix Factorization (NMF)

Apply a non-negative constraints matrix factorization explicitly (NMF) to the same dataset extracting purely additive un-centered features resulting in explainable part-based user and item representations.

- **Dataset:** `ratings.csv`
- **Selected Features:** `userId` (user_id), `movieId` (movie_id), `rating`
- **Target:** Missing Ratings Prediction & Top-N Item Recommendations

#### Pipeline

1. Construct the target user-item matrix directly from the parsed data, assigning unrated values to 0.
2. Initialize and train an `NMF` model with a predefined number of latent features ($k=20$) utilizing the 'nndsvd' initializer.
3. Decompose the rating matrix into non-negative User-Feature ($W$) and Item-Feature ($H$) components.
4. Calculate the dot product of the factor matrices to reconstruct the rating probabilities.
5. Evaluate overall rating accuracy using RMSE.
6. Design utility functions to generate recommendations and assess ranking significance using Information Retrieval metrics: **Precision@k** and **Recall@k**.
7. Analyze latent feature representation boundaries comparing NMF against SVD graphically.

#### Results

- **Evaluation Metrics:**
  - RMSE outlines absolute deviation across item factors.
  - Precision@k highlights relevance showing how many recommended items are mathematically deemed relevant (thresholded).
  - Recall@k outlines model inclusiveness analyzing what portion of positive items is actively intercepted.
  - Side-by-side performance review contrasts NMF limits vs. mean-centered SVD effectiveness on cold-starts.

---

## Visualizations

- RMSE vs Latent Factors (k) Plot (Elbow determination)
- Original vs Reconstructed Matrix Heatmaps (SVD)
- Top-N Recommendations Horizontal Bar Chart (SVD & NMF)
- User Latent Features Heatmap Analysis (NMF)
- Original vs Reconstructed Matrix Heatmaps (NMF)
- SVD vs NMF Performance Comparison Plot (RMSE Bar Chart)

---

## Tech Stack

| Component      | Tool / Library                     |
|----------------|------------------------------------|
| Language       | Python                             |
| Data Handling  | Pandas, NumPy                      |
| Visualization  | Matplotlib, Seaborn                |
| ML Algorithms  | Scikit-learn (TruncatedSVD, NMF)   |
| Preprocessing  | Mean Centering, NaN Handling       |
| Metrics        | RMSE, MAE, Precision@k, Recall@k   |

---

## How to Run

1. Ensure Python 3.x is installed along with the required libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn
   ```
2. Place the dataset (`ratings.csv`) in the same root project directory.
3. Open and run `EX10_ML.ipynb` in Jupyter Notebook, JupyterLab, or VS Code.

---

## Project Structure

```text
24BAD060_ML_EXP10/
|-- EX10_ML.ipynb                      # Main notebook for recommendation implementations
|-- ratings.csv                        # User-Movie ratings dataset
|-- README.md                          # Project documentation
```
