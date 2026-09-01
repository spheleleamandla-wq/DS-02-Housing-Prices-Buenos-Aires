# Buenos Aires Housing Prices - Linear Regression

Predicting property prices with Linear Regression, Ridge & Lasso to fix overfitting.

> WQU Data Science Lab DS 02 | Completed

### 1. Business Problem
Predict `price_aprox_usd` in Buenos Aires and build a model that generalizes.

### 2. Dataset
- 3 files: `buenos-aires-real-estate-1,2,3.csv` (~3,000 listings)
- Target: `price_aprox_usd`
- Features: `surface_total`, `surface_covered`, `rooms`, `property_type`, `place`

### 3. What I Did (Detailed)

**A. Data Preparation**
- Merged 3 CSVs with `pd.concat`
- Missing values: median imputation for surface, mode for property_type
- Outliers: Removed price > 99th percentile
- Feature Engineering: one-hot encoded `property_type` and `place`
- Scaling: `StandardScaler` for Ridge/Lasso

**B. EDA (Quick)**
- Price distribution is right-skewed
- Palermo / Recoleta highest median price
- Correlation surface_total vs price ~0.7

**C. Modeling**
- Baseline: `LinearRegression()`
- Ridge: Tuned alpha via cross-validation (L2 penalty)
- Lasso: Tuned alpha, produces sparsity

**D. Evaluation**
- 80/20 train_test_split with random_state=42
- Metrics: RMSE, MAE, R² (train + test)
- Monitored overfitting: Train R² vs Test R² gap


**Interpretation:** Baseline overfit. Ridge gave best generalization and closed train/test gap. Key drivers: surface_covered, Palermo location.

### 5. Tech Stack
Python, Pandas, NumPy, Scikit-learn, Matplotlib

### 6. How to Run
jupyter notebook notebook.ipynb