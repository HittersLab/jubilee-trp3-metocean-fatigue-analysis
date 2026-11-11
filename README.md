# Jubilee TRP3 Metocean Analysis and Fatigue Modelling

## Project Overview

This project applies Python, data analytics, statistical modelling and machine learning techniques to synthetic metocean data for offshore and subsea engineering applications.

The project focuses on understanding environmental conditions, analysing extreme wave events and exploring the relationship between metocean parameters and structural fatigue damage.

It is organised into three engineering case studies:

1. Metocean Exploratory Data Analysis (EDA) and Seasonal Analysis.
2. Extreme Value Analysis (GEV and Peaks Over Threshold).
3. Metocean Fatigue Correlation and Machine Learning Model Development.

The overall objective is to demonstrate how data analytics and predictive modelling can support offshore engineering assessments, environmental characterisation and asset integrity studies.

**Important:** All input data used in this project are synthetic and intended for educational and analytical purposes. They are not actual Jubilee field operating records.

---

## Project Objectives

- Perform exploratory analysis of offshore metocean conditions.
- Identify seasonal patterns and relationships between environmental variables.
- Fit statistical distributions to significant wave height and wave period.
- Apply extreme value analysis to estimate wave return levels.
- Explore wave-induced fatigue damage using spectral methods.
- Develop polynomial regression models to predict fatigue damage.
- Evaluate model performance using cross-validation and residual analysis.
- Present engineering findings through data visualisations and a dashboard.

---

## Project Structure

```text
jubilee-trp3-metocean-fatigue-analysis/
│
├── data/
│   └── jubilee_trp3_synthetic_metocean_1year.csv
│
├── 01_Metocean_EDA_Seasonal_Analysis.ipynb
├── 02_Extreme_Value_Analysis.ipynb
├── 03_Metocean_Fatigue_Correlation_Model.ipynb
│
├── outputs/
│   ├── processed_data/
│   │   ├── jubilee_trp3_enriched_metocean.csv
│   │   ├── gev_pot_return_level_comparison.csv
│   │   ├── jubilee_trp3_hourly_fatigue_damage.csv
│   │   ├── polynomial_regression_model_comparison.csv
│   │   ├── five_fold_cross_validation_results.csv
│   │   ├── fatigue_model_residuals.csv
│   │   ├── residual_pattern_analysis.csv
│   │   ├── monthly_fatigue_damage.csv
│   │   ├── actual_vs_predicted_fatigue_damage.csv
│   │   └── jubilee_trp3_dashboard_dataset.csv
│   │
│   └── jubilee_trp3_metocean_fatigue_dashboard.png
│
└── README.md
```

---

## Case 1: Metocean Exploratory Data Analysis and Seasonal Analysis

**Notebook:** `01_Metocean_EDA_Seasonal_Analysis.ipynb`

### Objective

To examine the synthetic metocean dataset, understand the distribution of environmental parameters and identify seasonal patterns and relationships that may influence offshore operations.

### Key Activities

- Loaded and inspected the hourly metocean dataset.
- Checked data quality, missing values and duplicate records.
- Fitted Weibull and Lognormal distributions to significant wave height (Hs) and peak wave period (Tp).
- Evaluated distribution goodness of fit using the Kolmogorov-Smirnov test.
- Investigated correlations between wave height, wave period, current speed and wind speed.
- Performed directional analysis and developed wave-related visualisations.
- Engineered temporal, rolling-window and environmental features.

### Main Output

`jubilee_trp3_enriched_metocean.csv`

This dataset contains the additional engineered features produced during the analysis.

---

## Case 2: Extreme Value Analysis

**Notebook:** `02_Extreme_Value_Analysis.ipynb`

### Objective

To investigate extreme significant wave heights and estimate potential return levels using statistical extreme value techniques.

### Key Activities

- Extracted monthly maximum significant wave heights.
- Applied the Generalised Extreme Value (GEV) distribution.
- Applied the Peaks Over Threshold (POT) method using the Generalised Pareto Distribution (GPD).
- Examined threshold selection using mean residual life analysis.
- Estimated 1, 10, 50 and 100-year return levels.
- Compared GEV and POT return-level estimates.
- Applied bootstrap resampling to examine uncertainty.
- Compared estimates against illustrative Gulf of Guinea regional reference values.

### Main Output

`gev_pot_return_level_comparison.csv`

This file contains the return-level comparison results from the GEV and POT analyses.

---

## Case 3: Metocean Fatigue Correlation and Machine Learning

**Notebook:** `03_Metocean_Fatigue_Correlation_Model.ipynb`

### Objective

To explore the relationship between environmental loading conditions and estimated fatigue damage, and develop regression models for fatigue damage prediction.

### Key Activities

- Developed a JONSWAP wave spectrum model.
- Examined spectral characteristics of the metocean conditions.
- Applied a simplified spectral fatigue damage calculation.
- Generated hourly and cumulative fatigue damage estimates.
- Developed polynomial regression models using metocean parameters.
- Compared polynomial regression models of different degrees.
- Evaluated model performance using training and testing datasets.
- Applied five-fold cross-validation.
- Examined model residuals and prediction errors.
- Developed a four-chart fatigue analysis dashboard.

### Machine Learning Approach

Polynomial regression models were developed using:

- Significant wave height (Hs).
- Peak wave period (Tp).
- Current speed.

Model degrees 1, 2 and 3 were compared using R² and Mean Absolute Error (MAE).

The third-degree polynomial model achieved the highest test performance in the implemented experiment.

### Main Outputs

- `jubilee_trp3_hourly_fatigue_damage.csv`
- `polynomial_regression_model_comparison.csv`
- `five_fold_cross_validation_results.csv`
- `fatigue_model_residuals.csv`
- `residual_pattern_analysis.csv`
- `monthly_fatigue_damage.csv`
- `actual_vs_predicted_fatigue_damage.csv`
- `jubilee_trp3_dashboard_dataset.csv`

### Dashboard Visualisation

The dashboard presents four aspects of the fatigue analysis:

1. Monthly fatigue damage accumulation.
2. Significant wave height versus fatigue damage.
3. Actual versus predicted fatigue damage.
4. Cumulative fatigue damage over time.

---

## Tools and Technologies

| Technology     | Application                                          |
| -------------- | ---------------------------------------------------- |
| Python         | Data processing and engineering calculations         |
| Google Colab   | Notebook development and execution                   |
| Pandas         | Data manipulation and analysis                       |
| NumPy          | Numerical and scientific calculations                |
| SciPy          | Statistical distributions and extreme value analysis |
| Matplotlib     | Data visualisation                                   |
| Seaborn        | Statistical visualisation                            |
| Scikit-learn   | Regression modelling and model evaluation            |
| Git and GitHub | Version control and project documentation            |

---

## Engineering Assumptions and Limitations

This project is an educational demonstration of engineering data analytics and predictive modelling.

The following limitations should be considered when interpreting the results:

1. The metocean dataset is synthetic and covers one year of hourly observations.
2. Long-period return-level estimates, particularly 50-year and 100-year estimates, are highly uncertain because of the limited observation period.
3. Distribution fitting and extreme value estimates require further validation using longer-term, representative environmental data.
4. The fatigue calculation uses an illustrative constant structural transfer function rather than a calibrated structural response model.
5. The fatigue results depend on assumed spectral and S-N curve parameters and should not be treated as validated structural fatigue predictions.
6. The regression model performance is based on the synthetic dataset. Further testing using independent, time-based validation data is required to establish generalisation performance.

**These results are not approved engineering design values and should not be used directly for operational or structural integrity decisions.**

---

## Project Learning Outcomes

Through this project, I developed practical experience in:

- Applying Python to offshore engineering data.
- Performing exploratory data analysis and feature engineering.
- Understanding statistical distribution fitting and extreme value analysis.
- Exploring wave spectral modelling and fatigue damage estimation.
- Developing and evaluating machine learning regression models.
- Interpreting model performance and uncertainty.
- Managing analytical workflows using GitHub and Google Colab.

---

## Conclusion

This project demonstrates an integrated approach to metocean data analysis, extreme wave characterisation and exploratory fatigue damage prediction.

It also highlights the potential application of Python, statistical analysis and machine learning in offshore engineering and subsea asset integrity.

The work provides a foundation for further development towards data-driven engineering, predictive analytics and AI-assisted asset integrity monitoring.

---

**Author:** Ndolo Nekabari

**Project:** Jubilee TRP3 Metocean Analysis and Fatigue Modelling

**Repository:** [https://github.com/HittersLab/jubilee-trp3-metocean-fatigue-analysis](https://github.com/HittersLab/jubilee-trp3-metocean-fatigue-analysis)
