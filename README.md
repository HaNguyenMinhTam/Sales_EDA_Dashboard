# Sales Time Series Forecasting

##  Project Overview

This project focuses on **sales time series forecasting and analysis**, designed to be suitable for both:

* **Data Analyst / BI Analyst** – understanding trends, seasonality, and business insights
* **AI Engineer / Data Scientist** – building, comparing, and evaluating forecasting models

The project covers the **end-to-end pipeline**:

> Data Understanding → EDA → Feature Preparation → Forecasting Models → Evaluation → Business Insights

---

##  Dataset & Business Context

* Sales transaction data aggregated over time (daily / monthly)
* Target variable: **Sales**
* Typical characteristics:

  * Long-term trend
  * Strong seasonality (monthly / yearly)
  * Irregular fluctuations

### Business Questions Addressed

* How do sales change over time?
* Are there clear seasonal patterns?
* Which forecasting approach provides the most reliable predictions?
* How can forecasts support inventory and planning decisions?

---

##  Exploratory Data Analysis (EDA)

*(Relevant for Data Analyst / BI Analyst)*

The EDA phase focuses on:

* Visualizing sales trends over time
* Identifying seasonality and peak periods
* Detecting anomalies and volatility
* Understanding data distribution and variance

Key outputs:

* Time series plots
* Seasonal decomposition
* Summary statistics

These insights help stakeholders understand historical performance before applying predictive models.

---

##  Forecasting Models

*(Relevant for AI Engineer / Data Scientist)*

### SARIMA (Seasonal ARIMA)

* Statistical time series model
* Captures:

  * Linear trends
  * Seasonal components
* Strengths:

  * Interpretable
  * Strong baseline model
* Limitations:

  * Limited ability to model nonlinear behavior

---

### LSTM (Long Short-Term Memory)

* Deep learning model for sequential data
* Captures:

  * Nonlinear temporal patterns
  * Long-term dependencies
* Strengths:

  * Flexible and expressive
* Limitations:

  * Requires careful tuning
  * Less interpretable compared to statistical models

---

### Hybrid SARIMA + LSTM (Key Contribution)

* Motivation:

  * SARIMA models trend & seasonality effectively
  * LSTM learns nonlinear patterns left in residuals

#### Workflow

1. Train SARIMA on the original series
2. Compute residuals (actual − SARIMA prediction)
3. Train LSTM on residuals
4. Final forecast = SARIMA forecast + LSTM residual forecast

 This hybrid approach combines **interpretability** and **predictive power**.

---

##  Model Evaluation

Models are evaluated using standard regression metrics:

* **MAE** – Mean Absolute Error
* **RMSE** – Root Mean Squared Error
* **MAPE** – Mean Absolute Percentage Error

### Model Comparison (Illustrative)

| Model                    | MAE      | RMSE     | MAPE     |
| ------------------------ | -------- | -------- | -------- |
| SARIMA                   | ✓        | ✓        | ✓        |
| LSTM                     | ✓        | ✓        | ✓        |
| **Hybrid SARIMA + LSTM** | **Best** | **Best** | **Best** |

*(Exact values depend on dataset and configuration.)*

---

##  Business Insights & Use Cases

*(Relevant for Data Analyst / BI Analyst)*

* Clear identification of seasonal peaks and low-demand periods
* Forecasts support:

  * Inventory planning
  * Promotion timing
  * Resource allocation

### Model Selection Perspective

* **SARIMA**: preferred when interpretability and stability are critical
* **LSTM / Hybrid**: preferred when accuracy and complex patterns matter

---

## Project Structure

```
Sales_TimeSeries_Forecasting/
│
├── data/              # Raw & processed data
├── notebooks/         # EDA & modeling experiments
├── models/            # Trained models
├── src/               # Preprocessing & utilities
├── results/           # Forecast plots & metrics
└── README.md
```

---

##  Future Improvements

* Add external (exogenous) variables:

  * Holidays
  * Promotions
  * Pricing
* Try additional models:

  * Prophet
  * Gradient Boosting
  * Transformer-based time series models
* Deploy forecasting as an API (FastAPI)
* Integrate forecasts into BI dashboards (Power BI / Tableau)

---

##  Author

**Ha Nguyen Minh Tam**
Data / AI Enthusiast

---

##  Notes for Recruiters & Interviewers

This project demonstrates:

* Data exploration and business insight generation
* Multiple forecasting techniques
* Hybrid modeling strategy
* Clear reasoning behind model selection
* Ability to bridge **analytics** and **machine learning**
