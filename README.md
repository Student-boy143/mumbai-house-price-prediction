# Mumbai House Price Prediction

A machine learning portfolio project that explores property asking prices in Mumbai and builds regression models to estimate prices from property characteristics.

## Project Overview

This project uses property attributes such as BHK, property type, locality, region, area, construction status, and property age to predict asking prices in Indian rupees.

The workflow includes data exploration, visualization, duplicate handling, preprocessing, regression modelling, model comparison, and error analysis.

**Note:** Predictions are estimates of asking prices, not verified transaction prices or professional property valuations.

## Models Evaluated

Three approaches were evaluated on the same strict test split:

| Model | MAE (₹ lakhs) | RMSE (₹ lakhs) |
|---|---:|---:|
| Median Baseline | 103.79 | 240.31 |
| Linear Regression | 41.12 | 93.81 |
| Ridge Regression | 74.12 | 131.60 |

Linear Regression performed best among the three models tested, reducing MAE by approximately 60.4% compared with the median baseline.

## Methodology

1. Explored the dataset and examined price distributions and locality-level patterns.
2. Investigated and removed exact duplicate rows.
3. Prepared numerical and categorical features using imputation and one-hot encoding.
4. Evaluated Linear Regression and Ridge Regression against a median baseline.
5. Used a group-based train/test split to prevent identical combinations of the selected property features from appearing in both sets.
6. Examined actual-versus-predicted prices and residuals to identify model limitations.
7. Tested predictions on a few example properties.

## Key Findings

- Property asking prices vary substantially across locations and property characteristics.
- Linear Regression outperformed the baseline and the tested Ridge Regression configuration on the evaluation split.
- Large errors remain for some expensive properties.
- Prediction quality may be weaker for unseen locality categories.

## Limitations

- Dataset provenance requires further verification.
- The unit used for the area feature requires verification.
- Asking prices may differ from final transaction prices.
- Evaluation used a group-based random split rather than a time-based split.
- The Ridge Regression regularization parameter was not extensively tuned.
- The small demonstration sample is illustrative and is not an independent evaluation.

## Project Structure

```text
mumbai-house-price-prediction/
├── data/
│   ├── raw/
│   └── processed/
├── notebooks/
│   └── 01_data_exploration.ipynb
├── models/
├── reports/
├── src/
├── .gitignore
└── README.md
```

## Technologies

- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- Jupyter Notebook

## Running the Project

1. Clone the repository.
2. Create and activate a Python virtual environment.
3. Install the required libraries.
4. Place the dataset in the expected local data directory.
5. Open and run `notebooks/01_data_exploration.ipynb`.

The raw dataset is not included in the repository by default. Confirm dataset access and update any required paths before running the notebook.

## Conclusion

This project demonstrates an end-to-end regression workflow, from exploratory data analysis to model evaluation and error interpretation. Linear Regression is the best-performing approach among the configurations evaluated so far. Further work could investigate feature engineering, regularization tuning, and additional regression models.
