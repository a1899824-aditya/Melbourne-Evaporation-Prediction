# 🌦️ Melbourne Evaporation Prediction for Water Resource Planning

This project models the evaporation rate at Melbourne’s Cardinia Reservoir using daily weather observations from the 2018–2019 financial year. Developed as a consulting report for the Melbourne Water Corporation (MWC), it predicts which days will exceed 9mm evaporation — the threshold for triggering water transfer operations.

---

## 📄 Dataset
- `melbourne.csv` – Contains daily weather observations including temperature, wind gust, humidity, and evaporation.

---

## 🛠 Tools & Packages
- R, RStudio  
- tidyverse (`dplyr`, `ggplot2`, `lubridate`)  
- `car`, `caret`, `inspectdf`

---

## 📊 Project Summary
- **Bivariate analysis**: Explored relationship of evaporation with month, day of week, wind gust, humidity, min temperature, sunlight hours.  
- **Model building**: Iterative variable elimination via ANOVA (`car::Anova()`); included interaction term (humidity × month).  
- **Final model**:  
  - Positive predictors: wind gust speed, minimum temperature  
  - Negative predictor: 9am relative humidity  
  - Significant interaction: humidity varies in effect by month

---

## 🔍 Key Results
- For each 1°C increase in minimum temperature → +0.329 mm evaporation  
- For each 1 km/h wind gust increase → +0.052 mm  
- For each 1% increase in humidity → −0.084 mm  
- Adjusted R²: **~0.63**

---

## 📈 Predictions
MWC requires interventions when evaporation exceeds 9mm. The model forecasts:

| Date         | Evaporation (mm) | 95% Prediction Interval |
|--------------|------------------|--------------------------|
| 2024-01-11   | 14.4             | [9.7, 19.2] ✅ |
| 2024-02-21   | 5.2              | [0.8, 9.5] ❌ |
| 2024-07-11   | 0.9              | [−3.5, 5.3] ❌ |
| 2024-12-26   | 12.1             | [7.4, 16.8] ✅ |

---

## 📁 Files
- `Assignment4_datataminga1899824uni.Rmd`: Full R analysis  
- `Assignment4_datataminga1899824uni.pdf`: Final report  
- `melbourne.csv`: Weather dataset

---

## 🧠 Learnings
- Statistical model building (stepwise ANOVA elimination)  
- Diagnostics: residuals, normality, homoscedasticity  
- Scenario-based forecasting with prediction intervals

---

## 👤 Author
Aditya Venugopalan Nediyirippil  
GitHub: [a1899824-aditya](https://github.com/a1899824-aditya)
