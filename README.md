# ARMA-Time-Series-Humidity-forcasting
# Hourly Humidity Forecasting in Nairobi Using ARIMA

# 📌 Project Overview

* This project focuses on analyzing and forecasting hourly humidity data collected from Nairobi. Using the ARIMA (AutoRegressive Integrated Moving Average) model, the goal is to provide short-term humidity predictions based on historical sensor readings. The workflow includes data wrangling, visualization, time series analysis, model training, and evaluation.


---

# 🧰 Tools & Libraries Used

* Pandas & NumPy – Data manipulation and numerical operations

* Matplotlib, Seaborn, Plotly – Data visualization

* Statsmodels – Time series modeling (ARIMA, ACF, PACF)

* Scikit-learn – Model evaluation (Mean Absolute Error)

* Time – Runtime tracking



---

# 🔍 Data Preprocessing

1. Filtering Data for Humidity
* The dataset includes multiple sensor readings. We filtered it to only include records related to humidity.


2. Pivoting the Dataset
* Transformed the dataset to isolate humidity values using a pivot table.


3. Datetime Handling

* Converted timestamps from object type to datetime.

* Localized timestamps to the Africa/Nairobi timezone for accurate hourly tracking.



4. Resampling
* The data was resampled to hourly intervals (1H), and missing values were filled using forward-fill to ensure temporal continuity.




---

# 📊 Exploratory Data Analysis (EDA)

**Descriptive Statistics**
* Summary statistics (mean, std, min, max, quartiles) were computed to understand humidity distribution.

**Histogram**
* A histogram of humidity values revealed its general distribution pattern.

* Autocorrelation & Partial Autocorrelation

* ACF Plot showed clear lag patterns with alternating positive and negative correlation every few hours.

* PACF Plot helped identify relevant time lags, with significant changes occurring within the first 26 hours.




---

# 🧪 Model Development

**Data Splitting**

* Training Set: Data from April 2018

* Testing Set: Data from May 1, 2018


**Baseline Evaluation**

* Used the mean of the training set as the baseline prediction.

* The baseline Mean Absolute Error (MAE) was calculated to benchmark model performance.


**Hyperparameter Tuning**

* Explored different combinations of ARIMA parameters:

* P (AR lags): [0, 8, 16, 24]

* Q (MA lags): [0, 4, 1]


* Models were trained using different parameter combinations and evaluated using MAE.


**Model Selection**

* MAEs were compiled into a grid and visualized using a heatmap.

* The best-performing model had an MAE around 2.0, significantly improving upon the baseline.



---

# 📉 Model Diagnostics & Performance

* Diagnostic Plots: Showed residuals, standardized errors, and model fit diagnostics.

* Prediction vs Actual: A DataFrame comparing the actual and predicted humidity values was created for the training period.



---

# 🧪 Evaluation – Walk-Forward Validation

* Performed walk-forward validation to test model robustness.

* The ARIMA model was retrained for each test step, simulating a real-time forecasting scenario.

* After walk-forward validation, the MAE improved to ~1.55, demonstrating model effectiveness.



---

# 📈 Final Predictions

* Predictions for May 1, 2018 were visualized using an interactive line plot.

* The model showed good alignment with actual values and maintained consistent accuracy.



---

# ✅ Conclusion

* The ARIMA model effectively captured hourly humidity trends in Nairobi.

* Walk-forward validation significantly enhanced model performance.

* This forecasting approach could support environmental monitoring and planning in urban settings.



---
