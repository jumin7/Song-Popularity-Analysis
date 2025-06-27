# Song Popularity Analysis (2023)

This project analyzes a Spotify dataset from 2023 to understand and predict song popularity based on various features such as audio characteristics, chart performance, and playlist inclusions. The goal is to explore which features contribute most to a song's success and to implement predictive models to estimate stream counts and classify potential hits.
Authors : Isabella Garcia & Jumin Shrestha

## Project Overview

The project includes the following major components:

### 1. **Data Loading and Exploration**

* Loaded and explored a Spotify dataset with track metadata, audio features, and streaming numbers.
* Identified and handled missing values in key columns such as `in_shazam_charts` and `key`.

### 2. **Data Cleaning and Preprocessing**

* Dropped rows with null values and cleaned formatting (e.g., removing commas).
* Encoded categorical variables (e.g., `key`, `mode`) into numeric form.
* Created a binary target variable `hit`, defined as songs with over 100 million streams.

### 3. **Regression Modeling**

* **Linear Regression** used to predict the number of streams.
* Features were standardized, and model performance was evaluated using:

  * **R² (coefficient of determination)**: moderate explanatory power.
  * **MSE (Mean Squared Error)**: high error for very popular songs due to stream distribution skew.

### 4. **Classification Modeling**

* A simple classification model was built based on the linear regression predictions and the `hit` threshold.
* Achieved reasonable accuracy in identifying hits vs. non-hits.

### 5. **Visualizations and Insights**

* **Actual vs. Predicted Scatter Plot**: Shows model’s underestimation of viral hits.
* **Feature Importance Plot**: Playlist-related features had the strongest influence.
* **Residuals vs. Predicted Plot**: Error increases with predicted stream values.
* **Correlation Heatmap**: Identifies relationships among features and their potential impact on popularity.

### 6. **Additional Models**

* **Decision Tree Regressor & Classifier**:

  * Decision Tree models improved R² slightly.
  * Classifier performed well, reinforcing the dominance of playlist features.
* **K-Nearest Neighbors (KNN)**:

  * KNN Regressor showed comparable performance to Linear Regression.
  * Tuned optimal `k` for best performance.

### 7. **Clustering with K-Means**

* Applied **K-Means Clustering** to discover natural groupings of songs.
* Used **PCA** for dimensionality reduction and cluster visualization.
* Analyzed cluster profiles with heatmaps to interpret feature trends across groups.

---

## Key Takeaways

* **Playlist inclusions** are highly predictive of song success.
* Regression models struggle with predicting extreme outliers (viral hits).
* Combining regression, classification, and clustering provides a more holistic view of song popularity.
* Visualization is essential for interpreting model performance and feature impact.

---

## Technologies Used

* Python (Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn)
* Machine Learning: Linear Regression, Decision Tree, KNN, K-Means Clustering, PCA
* Google Colab

---

## Future Improvements

* Implement more advanced models (e.g., Random Forest, XGBoost) for better performance.
* Explore time-series aspects using release dates.
* Balance the dataset or use log transformations to better handle skewed stream distributions.

