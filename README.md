# MovieLens Capstone Project – Predicting Movie Popularity

## Overview
This capstone project explores the MovieLens 100K dataset to analyze user ratings and build a baseline predictive model for movie popularity. The objective is to demonstrate how data-driven insights can support personalized content recommendation systems.

## Problem Statement
The task is to predict whether a movie is considered **popular**, defined as having an average rating **≥ 3.5**, based on user engagement data. This simulates a simplified version of content filtering used in modern recommendation systems.

## Dataset Summary
- **Source:** [MovieLens 100K Dataset](https://grouplens.org/datasets/movielens/100k/)
- **movies.csv**: Pipe-separated file with movie metadata (columns used: `movieId`, `title`)
- **ratings.csv**: Tab-separated file with user ratings (`userId`, `movieId`, `rating`, `timestamp`)

## Methodology

### 1. Data Loading & Diagnostics
- Files loaded with appropriate delimiters and encoding.
- Initial data inspection includes shape, types, and unique values.
- Merged ratings and movies on `movieId`.

### 2. Feature Engineering
- Aggregated movie-level statistics:
  - `rating_mean`: Average rating per movie
  - `rating_count`: Total number of ratings
- Created binary target: `popular` (1 if `rating_mean` ≥ 3.5, else 0)

### 3. Modeling
- Model: **Logistic Regression**
- Inputs: `rating_mean`, `rating_count`
- Data split: 70/30 with stratification
- Evaluation: Accuracy score, confusion matrix, classification report

## Summary of Findings
- Movies with both a higher average rating and more ratings are more likely to be popular.
- The distribution of ratings skews toward mid-to-high values.
- The baseline Logistic Regression model demonstrates that simple features can reasonably predict popularity.

## Actionable Insights
- **User engagement (rating count)** is a strong signal for popularity.
- Even a basic model can segment content effectively for recommender systems.
- Further performance gains may be unlocked by including genre or user-level behavior.

## Next Steps
- Include genre and temporal trends in feature engineering
- Test advanced models like Random Forest or XGBoost
- Add model explainability tools (e.g., SHAP, LIME)
- Apply findings in a live recommender setting or simulation

## Project Structure
MovieLensCapstone/
│
├── Capstone_EDA_MovieLens_Updated.ipynb   # Updated Jupyter Notebook with EDA and baseline modeling
├── movies.csv                             # Movie metadata
├── ratings.csv                            # User ratings data
└── README.md                              # Project overview and guide

## How to Run the Project
1. Place `movies.csv` and `ratings.csv` in the working directory.
2. Open `Capstone_EDA_MovieLens_Updated.ipynb` in JupyterLab, Colab, or VS Code.
3. Run all cells in order. The notebook will:
   - Load and merge data
   - Perform EDA and visualizations
   - Engineer features
   - Train and evaluate the model
4. Review final outputs and business insights in the conclusion section.

---

**Author:** Brenda O’Kane  
**Module:**  Capstone  
**Project:** Capstone_MovieLens
