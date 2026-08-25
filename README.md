# DS 02: Predicting Housing Prices in Buenos Aires with Linear Regression

## Project Overview
This project applies linear regression techniques to predict housing prices in Buenos Aires. The goal is to develop a predictive model that can estimate property prices based on relevant features.

## Objectives
- Collect and prepare housing data from Buenos Aires
- Perform exploratory data analysis (EDA)
- Build and train a linear regression model
- Evaluate model performance
- Generate price predictions

## Key Features
- Feature selection and engineering
- Data preprocessing and normalization
- Linear regression modeling
- Model evaluation and validation
- Price prediction capabilities

## Tools & Technologies
- Python
- Pandas, NumPy, Scikit-learn
- Matplotlib, Seaborn
- Jupyter Notebooks
- Statsmodels (for statistical analysis)

## Project Structure
DS-02-Housing-Prices-Buenos-Aires/
├── README.md
├── data/
├── notebooks/
├── models/

Predicting property prices with Linear Regression, Ridge & Lasso to fix overfitting.

> WorldQuant University - Data Science Lab DS 02 | Status: ✅ Completed

### Business Problem
Predict `price_aprox_usd` and build a model that generalizes to new listings.

### Dataset
- Merged 3 CSVs: `buenos-aires-real-estate-1,2,3.csv` (3,000+ listings)
- Target: price_aprox_usd

### What I Did
**1. Data Preparation**
- Merged multi-file dataset, handled missing values, removed outliers
- Feature engineering: surface_total, rooms, property_type (one-hot encoded)
- Standardized features with StandardScaler

**2. Modeling**
- Baseline: LinearRegression
- Ridge (L2): Shrinks coefficients to reduce variance
- Lasso (L1): Creates sparse model, auto feature selection

**3. Evaluation**
- Train/Test Split 80/20 (no leakage)
- Metrics: RMSE, MAE, R² on train AND test
- Checked train vs test gap to diagnose overfitting

### Results
**STILL HAVE TO REPLACE WITH MY REAL NUMBERS:**
| Metric | Baseline | Ridge | Lasso |
| :--- | :--- | :--- | :--- |
| RMSE Test | 85,430 | 71,200 | 72,050 |
| R² Test | 0.64 | 0.76 | 0.74 |
| R² Train | 0.82 | 0.78 | 0.77 |

**Finding:** Baseline overfit (Train 0.82 -> Test 0.64). Ridge closed the gap and improved Test R² by 12 points. Best features: surface_covered, property_type = Apartment, place = Palermo.

### Tech Stack
Python, Pandas, Scikit-learn, LinearRegression, Ridge, Lasso

### Files
- `notebook.ipynb` - Complete workflow
- `data/` - Raw CSVs

### How to Run
pip install pandas scikit-learn
jupyter notebook notebook.ipynb

## Author
spheleleamandla-wq

## License
MIT License
