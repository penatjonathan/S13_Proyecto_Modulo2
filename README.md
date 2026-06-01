# 🏆 Sprint 13 Project — Gold Recovery Process Optimization (Machine Learning)

---

## 🧠 Project Overview

In this project, I worked as a Data Scientist for a mining company seeking to optimize the **gold recovery process**.

The objective was to develop a machine learning model capable of predicting the efficiency of gold recovery at different stages of the extraction process. Accurate predictions help optimize production, reduce operational costs, and improve overall plant performance.

The project involved extensive data validation, exploratory analysis, anomaly detection, feature selection, custom metric implementation, and model evaluation using **sMAPE (Symmetric Mean Absolute Percentage Error)**.

---

## 🎯 Project Objectives

* Prepare and validate the mining process data.
* Verify the correctness of the gold recovery calculation.
* Identify features unavailable in the test dataset.
* Analyze metal concentrations throughout purification stages.
* Detect and remove anomalous observations.
* Develop a custom sMAPE evaluation function.
* Train and compare multiple machine learning models.
* Select the model with the best cross-validation performance.
* Evaluate the final model on the test dataset.

---

## 📁 Dataset Description

Three datasets were provided:

* `gold_recovery_train.csv`
* `gold_recovery_test.csv`
* `gold_recovery_full.csv`

The datasets contain information collected during different stages of the gold extraction process.

### Key Features

| Variable Type         | Description                            |
| --------------------- | -------------------------------------- |
| `date`                | Timestamp of data collection           |
| `rougher.*`           | Parameters from the flotation stage    |
| `primary_cleaner.*`   | Parameters from primary purification   |
| `secondary_cleaner.*` | Parameters from secondary purification |
| `final.*`             | Final process measurements             |
| `*_au`                | Gold concentration measurements        |
| `*_ag`                | Silver concentration measurements      |
| `*_pb`                | Lead concentration measurements        |

### Target Variables

| Target                    |
| ------------------------- |
| `rougher.output.recovery` |
| `final.output.recovery`   |

---

## 🧩 Project Workflow

### Step 1 — Data Preparation

* Loaded training, test, and full datasets.
* Examined dataset structure and feature availability.
* Checked data types and missing values.
* Investigated missing target variables in the test dataset.
* Performed data cleaning and preprocessing.

---

### Step 2 — Recovery Calculation Validation

To ensure data quality:

* Recalculated the recovery formula for:

```text
rougher.output.recovery
```

* Compared calculated values with the provided values.
* Computed the Mean Absolute Error (MAE).
* Confirmed the correctness of the recovery calculations.

---

### Step 3 — Feature Availability Analysis

Compared training and test datasets to identify:

* Features unavailable during real-time prediction.
* Output measurements calculated after production stages.
* Parameters that would cause data leakage if used during training.

Only features available at prediction time were retained.

---

### Step 4 — Exploratory Data Analysis

#### Metal Concentration Analysis

Studied concentration changes of:

* Gold (Au)
* Silver (Ag)
* Lead (Pb)

Across different processing stages:

* Feed
* Rougher Concentrate
* Primary Cleaning
* Final Concentrate

The analysis helped verify that purification stages behaved as expected.

---

#### Particle Size Distribution

Compared feed particle-size distributions between:

* Training dataset
* Test dataset

This ensured that both datasets originated from similar production conditions and that model evaluation would remain reliable.

---

#### Anomaly Detection

Analyzed total concentrations of all substances across processing stages.

Detected abnormal observations including:

* Near-zero concentrations
* Physically unrealistic values

Removed anomalies to improve model stability and prediction quality.

---

## 🤖 Model Development

Several regression models were evaluated, including:

* Linear Regression
* Decision Tree Regressor
* Random Forest Regressor

Model performance was assessed using cross-validation.

---

## 📊 Evaluation Metric

### sMAPE (Symmetric Mean Absolute Percentage Error)

A custom function was implemented to calculate:

```text
sMAPE
```

for both target variables:

* Rougher Recovery
* Final Recovery

The final evaluation metric was calculated using the weighted formula provided in the project instructions.

Lower sMAPE values indicate better predictive performance.

---

## 🔍 Model Selection

The workflow included:

1. Cross-validation for each candidate model.
2. Hyperparameter tuning.
3. Comparison of average validation scores.
4. Selection of the best-performing model.
5. Final testing using the provided test dataset.

The chosen model achieved the lowest overall sMAPE while maintaining consistent performance across validation folds.

---

## 💡 Business Insights

This project demonstrates how machine learning can support industrial process optimization by:

* Improving recovery rate forecasting.
* Reducing production inefficiencies.
* Detecting process anomalies.
* Supporting operational decision-making.
* Increasing profitability in mineral processing operations.

Reliable recovery predictions allow engineers to monitor plant performance and make proactive adjustments to maximize gold extraction efficiency.

---

## 🧰 Tools & Libraries

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* SciPy
* Jupyter Notebook

---

## 📚 Machine Learning Concepts Applied

* Regression Modeling
* Feature Selection
* Data Cleaning
* Missing Value Handling
* Anomaly Detection
* Cross-Validation
* Hyperparameter Tuning
* Custom Metric Implementation
* Process Optimization Analytics
* Industrial Machine Learning

---

## 👤 Author

**Jonathan Peña**

Project completed as part of **Sprint 13 — Gold Recovery Process Optimization with Machine Learning**.
