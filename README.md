# House Price Prediction

Internship project (Week 1) — a regression model that predicts house prices from property features such as area, bedrooms, bathrooms, and amenities, and identifies which features influence price the most.

**Author:** Poorvi Sharma

## Dataset

[Kaggle — Housing Prices Dataset](https://www.kaggle.com/datasets/yasserh/housing-prices-dataset) (`Housing.csv`): 545 properties, 13 features (price, area, bedrooms, bathrooms, stories, mainroad, guestroom, basement, hotwaterheating, airconditioning, parking, prefarea, furnishingstatus). No missing values or duplicates.

## What's in this repo

| File | Description |
|---|---|
| `analysis.ipynb` | Full notebook — data exploration, cleaning, model training, evaluation, and visualization |
| `Housing.csv` | Dataset used |
| `summary.pdf` / `summary.docx` | 1-page written summary of findings |
| `charts/` | Saved chart images (price distribution, correlation heatmap, actual vs predicted) |

## Approach

1. **Exploration** — loaded the data, checked shape, dtypes, and missing values.
2. **Cleaning** — dropped duplicates (none found), encoded yes/no columns as 1/0, one-hot encoded `furnishingstatus`.
3. **Modeling** — 80/20 train-test split; trained Linear Regression and Random Forest Regressor.
4. **Evaluation** — compared both models on MAE, RMSE, and R².
5. **Visualization** — price distribution histogram, correlation heatmap, and an actual-vs-predicted scatter plot.

## Results

| Model | MAE (₹) | RMSE (₹) | R² Score |
|---|---|---|---|
| Linear Regression | 970,043 | 1,324,507 | **0.653** |
| Random Forest Regressor | 1,022,560 | 1,401,497 | 0.611 |

Linear Regression slightly outperformed Random Forest — on a dataset this size (545 rows) with mostly linear feature relationships, the simpler model generalized better.

## Key Insight

`area` is the strongest driver of price, followed by `bathrooms` and `airconditioning`. Predictions are typically within ~₹9–10 lakh of actual price — useful as a ballpark estimate rather than a precise valuation.

## Tools

Python, Pandas, Scikit-learn, Matplotlib, Seaborn, Jupyter Notebook

## How to run

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
jupyter notebook analysis.ipynb
```

Make sure `Housing.csv` is in the same folder as the notebook before running.
