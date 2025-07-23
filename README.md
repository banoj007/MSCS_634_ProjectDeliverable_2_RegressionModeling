# Lab 4: Regression Analysis with Regularization Techniques

**Name:** Banoj Kumar Jena  
**Course:** MSCS 634  
**Lab Title:** Regression Analysis with Regularization  
**Dataset:** Diabetes Dataset from `sklearn.datasets`  

---

## Purpose

The purpose of this lab is to explore and apply different regression techniques on a real-world dataset. The objective is to understand how model complexity and regularization techniques like Ridge and Lasso impact performance and generalizability.

---

## Description of the Dataset

The dataset used in this lab is the **Diabetes Dataset**, available through `sklearn.datasets`. It contains 10 baseline variables (age, sex, body mass index, average blood pressure, and six blood serum measurements) obtained from 442 diabetes patients. The target variable is a quantitative measure of disease progression one year after baseline.

---

## Models Implemented

### 1. Simple Linear Regression  
- Used **BMI** as a single predictor to estimate disease progression.
- This model provides a baseline for comparison with more complex models.

### 2. Multiple Linear Regression  
- Used all features in the dataset to improve prediction accuracy.
- Showed significant improvement over simple regression.

### 3. Polynomial Regression  
- Applied polynomial transformation (degree 2 and 3) to BMI.
- Intended to capture non-linear relationships.
- Did not outperform multiple regression due to limited complexity in the single feature used.

### 4. Ridge Regression  
- Applied L2 regularization to penalize large coefficients.
- Useful when multicollinearity is present or overfitting occurs.
- Required tuning for better performance.

### 5. Lasso Regression  
- Applied L1 regularization to shrink coefficients and possibly eliminate features.
- Helps in feature selection but underperformed without hyperparameter tuning.

---

## Evaluation Metrics

The following metrics were used to evaluate each model:

- **Mean Absolute Error (MAE)**: Measures average magnitude of errors.
- **Mean Squared Error (MSE)**: Penalizes larger errors more than MAE.
- **Root Mean Squared Error (RMSE)**: Interpretable in the same units as the target.
- **R² Score (R-squared)**: Represents the proportion of variance explained by the model.

---

## Key Results

| Model                          | MAE    | MSE     | RMSE   | R²     |
|-------------------------------|--------|---------|--------|--------|
| Simple Linear Regression (BMI)| 52.26  | 4061.83 | 63.73  | 0.23   |
| Multiple Linear Regression     | 42.79  | 2900.19 | 53.85  | 0.45   |
| Polynomial Regression          | 52.18  | 4064.44 | 63.75  | 0.23   |
| Ridge Regression               | 55.96  | 4196.97 | 64.78  | 0.21   |
| Lasso Regression               | 52.26  | 4017.03 | 63.38  | 0.24   |

---

## Analysis and Interpretation

- **Multiple Linear Regression** had the best performance, demonstrating the importance of using all relevant features.
- **Simple and Polynomial Regression** using BMI alone underperformed, showing the limitation of relying on a single predictor.
- **Polynomial Regression** did not improve results, likely due to the lack of non-linearity in the BMI feature or overfitting.
- **Ridge and Lasso** showed slightly poorer performance without tuning the regularization strength (`alpha`).
- Regularization is more effective when properly tuned or used with high-dimensional datasets.

---

## Challenges Faced

- Selecting the optimal feature for Simple and Polynomial Regression.
- Deciding the polynomial degree without overfitting the model.
- Ridge and Lasso regressions required tuning, which was not included due to time constraints.
- Visualizing models with high-dimensional input was more challenging.

---

## Suggestions for Improvement

- **Hyperparameter tuning**: Use techniques like `GridSearchCV` or `RidgeCV`/`LassoCV` to find optimal values of `alpha`.
- **Cross-validation**: Improve robustness of model evaluation using k-fold cross-validation.
- **Feature selection**: Apply statistical or model-based techniques to determine the most informative predictors.
- **Regularization with polynomial regression**: Combine polynomial features with regularized models to reduce overfitting risk.

---

## Files in Repository

- `Lab4_Regression_BanojKumarJena.ipynb`: Complete Jupyter Notebook with code, output, and visualizations.
- `README.md`: Summary and explanation of the lab, methods, and results.

---

## Tools and Libraries Used

- Python 3.x
- NumPy
- Pandas
- Matplotlib
- Seaborn
- scikit-learn

---

## Conclusion

This lab provided valuable insights into the trade-offs between model complexity and generalization in regression. Regularization is a powerful concept but must be used carefully with proper tuning. Multiple regression models using all features proved to be the most effective for predicting disease progression in the diabetes dataset.

---
