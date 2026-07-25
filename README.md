## Bitcoin Time Series Analysis: ARIMA & GARCH Volatility Modeling

This project involves exploratory data analysis and statistical time series modeling on Bitcoin's historical daily price data. The objective is to test whether Bitcoin's daily returns are predictable, and to model how its volatility behaves over time, using classical time series methods.

### Files

* `bitcoin_codes.txt` — R script containing the entire workflow:

  * Data loading and cleaning
  * Exploratory Data Analysis (EDA)
  * Feature selection
  * Stationarity and seasonality testing
  * ARIMA and GARCH modeling
  * Model validation and evaluation

* `bitcoin_2010-07-17_2024-06-28.csv` — The dataset used for analysis (expected to be in the same directory).
* `bitcoin_plots.pdf` — All generated plots (EDA, ACF/PACF, GARCH validation), compiled into a single PDF.
* `Bitcoin_Project_Report.docx` — Full project report summarizing the problem, methodology, results, and conclusions.

---

### Features

* **EDA** using base R and ggplot2 to visualize price trends, return distributions, and volatility clustering.
* **Feature selection** using correlation analysis and regression p-values (not intuition) to identify significant lagged predictors.
* **Stationarity testing** using the Augmented Dickey-Fuller (ADF) test.
* **Seasonality testing** using one-way ANOVA (day-of-week effects).
* **Model training** using:

  * ARIMA (return direction)
  * GARCH (volatility)
* **Model evaluation** using R-squared, RMSE, MAE, and correlation against an independent realized volatility measure.

---

### Results

The analysis shows that Bitcoin's daily return **direction** is close to unpredictable (ARIMA R² ≈ 0), consistent with market efficiency — though ARIMA still outperforms a naive baseline on RMSE/MAE. In contrast, Bitcoin's **volatility** is strongly predictable and persistent: GARCH's alpha and beta coefficients are highly significant, a simple volatility-persistence regression achieves R² = 0.986, and GARCH's estimated volatility correlates at 0.478 with an independent, model-free realized volatility measure.

---
📌 Author

Ananya
