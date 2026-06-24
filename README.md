# Boston House Price Prediction

A regression-based machine learning project to predict median house prices in Boston suburbs using socio-economic and geographic features. Built with Linear Regression and StandardScaler feature engineering.

---

## Problem Statement

Predicting real estate prices is a classic regression challenge in data science. This project models the relationship between 13 socio-economic features (crime rate, number of rooms, tax rate, etc.) and median house values in Boston, helping understand which factors most influence property prices.

---

## Dataset

**Source:** Boston Housing Dataset — StatLib / UCI Machine Learning Repository
**Loaded from:** [selva86/datasets on GitHub](https://raw.githubusercontent.com/selva86/datasets/master/BostonHousing.csv)

> ⚠️ Note: `sklearn.datasets.load_boston` was **deprecated in v1.0 and removed in v1.2** due to ethical concerns about the dataset's LSTAT variable. This project loads the data directly from a public CSV source to remain compatible with all modern scikit-learn versions.

| Feature | Description |
|---|---|
| `CRIM` | Per capita crime rate by town |
| `ZN` | Proportion of residential land zoned for large lots |
| `INDUS` | Proportion of non-retail business acres |
| `CHAS` | Charles River dummy variable (1 if tract bounds river) |
| `NOX` | Nitric oxide concentration |
| `RM` | Average number of rooms per dwelling |
| `AGE` | Proportion of owner-occupied units built before 1940 |
| `DIS` | Weighted distances to employment centres |
| `RAD` | Index of accessibility to radial highways |
| `TAX` | Full-value property tax rate |
| `PTRATIO` | Pupil-teacher ratio by town |
| `B` | Proportion of residents by town |
| `LSTAT` | % of lower status population |
| `PRICE` | Median house value in $1000s (target) |

---

## Approach

```
Load Data → EDA → Visualisation → Train/Test Split → StandardScaler → Linear Regression → Evaluation
```

1. **EDA** — descriptive statistics, missing value check, unique value analysis
2. **Visualisation** — correlation heatmap, price distribution, key feature scatter plots
3. **Preprocessing** — StandardScaler fitted on train set only (no data leakage)
4. **Modelling** — Linear Regression
5. **Evaluation** — R², Adjusted R², MAE, MSE, RMSE on both train and test sets

---

## Results

| Metric | Train | Test |
|---|---|---|
| R² | ~0.74 | ~0.71 |
| Adjusted R² | ~0.73 | ~0.69 |
| MAE | ~3.2 | ~3.5 |
| RMSE | ~4.7 | ~5.0 |

> Train and test scores are close, confirming the model is **not overfitting**.
> Test RMSE of ~5.0 means predictions are off by approximately $5,000 on average.

---

## Visualisations

- Feature correlation heatmap
- House price distribution
- Key feature scatter plots (RM, LSTAT, CRIM vs Price)
- Actual vs Predicted scatter plot
- Residual plot
- Feature importance (regression coefficients)

---

## Key Findings

- `RM` (average rooms) has the strongest **positive** correlation with price — more rooms → higher price
- `LSTAT` (lower status %) has the strongest **negative** correlation — higher poverty → lower price
- `CRIM` (crime rate) also negatively impacts price but with high variance at low crime levels
- Linear Regression achieves ~71% explained variance (R²) on test data — a solid baseline

---

## Project Structure

```
boston-house-price/
├── boston_house_price.py     # Main script
├── requirements.txt          # Python dependencies
├── .gitignore
└── README.md
```

---

## How to Run

```bash
# 1. Clone the repository
git clone https://github.com/vanshika2003/boston-house-price.git
cd boston-house-price

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run — dataset is loaded automatically from the web
python boston_house_price.py
```

> No dataset download needed — the script loads it directly from GitHub.

---

## Tech Stack

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.3+-orange?logo=scikit-learn)
![Pandas](https://img.shields.io/badge/Pandas-2.0+-green?logo=pandas)

- **Language:** Python 3.10+
- **Libraries:** pandas, numpy, scikit-learn, matplotlib, seaborn

---

## Author

**Vanshika Aggarwal**
M.Sc. Data Science — Chandigarh University
[LinkedIn](https://www.linkedin.com/in/vanshika2003) • [GitHub](https://github.com/vanshika2003)
