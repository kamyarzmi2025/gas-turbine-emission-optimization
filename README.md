# Gas Turbine Emission Optimization  
Industrial Machine Learning Project (Process Engineering × Data Science)

---

## 📌 Project Overview

This project develops an end-to-end machine learning framework for predicting and optimizing NOx emissions in industrial gas turbines.

Using the UCI Gas Turbine CO & NOx dataset (36,726 records after cleaning), the objective was to:

- Build predictive models for NOx emissions
- Compare linear and non-linear approaches
- Interpret model behavior using explainable AI
- Identify operating conditions minimizing emissions
- Maintain energy output (TEY) during optimization

This work bridges combustion engineering and industrial machine learning.

---

## 🏭 Engineering Motivation

NOx formation in gas turbines is highly temperature-dependent and influenced by:

- Ambient conditions
- Combustion temperature
- Pressure dynamics

Understanding and optimizing these relationships enables:

- Emission-aware operation
- Improved environmental compliance
- Intelligent decision-support systems

---

## 📊 Dataset

Source: UCI Machine Learning Repository  
Dataset: Gas Turbine CO and NOx Emission Data  

- Samples: 36,726
- Features: 9 operational & ambient parameters
- Target: NOx (log-transformed)

Key variables include:
- AT (Ambient Temperature)
- TIT (Turbine Inlet Temperature)
- GTEP (Gas Turbine Exhaust Pressure)
- TEY (Turbine Energy Yield)

---

## 🔍 Data Preprocessing

- Removed duplicate records
- Verified missing values
- Applied log-transformation to NOx  
  (Skew reduced from 1.03 → 0.38)

Reason:
Linear models assume near-normal residual behavior.  
Reducing skew improves model stability.

---

## 🤖 Modeling Approach

### 1️⃣ Baseline – Linear Regression
Purpose:
- Establish reference performance
- Evaluate linear behavior

Result:
R² ≈ 0.53

Insight:
System dynamics are not purely linear.

---

### 2️⃣ Random Forest (Best Model)
Reason:
- Captures non-linear combustion behavior
- Handles interaction effects
- Robust to feature scaling

Result:
R² ≈ 0.87

Conclusion:
NOx formation exhibits strong non-linear relationships.

---

### 3️⃣ XGBoost
Result:
R² ≈ 0.83

Random Forest performed better for this dataset.

---

## 🔎 Model Interpretability

### SHAP Analysis

Used to:
- Identify dominant drivers
- Understand feature impact direction
- Align ML results with physical understanding

Key drivers:
- Ambient Temperature (AT)
- Turbine Inlet Temperature (TIT)

Findings are consistent with combustion thermodynamics.

---

## 📈 Sensitivity Analysis

Partial Dependence Plots confirmed:

- Increasing TIT → increases NOx
- Ambient temperature significantly affects emissions

---

## 🎯 Optimization Strategy

### Single-objective Optimization
Minimize predicted NOx

→ Achieved ≈ 42 mg/m³  
→ TEY ≈ 160 MWh

---

### Multi-objective (Pareto-style Filtering)

Goal:
Minimize NOx while maintaining high energy output

Result:
→ NOx ≈ 42.8 mg/m³  
→ TEY ≈ 148.9 MWh  
→ Above plant average (133.5 MWh)

---

## 🧠 Key Engineering Insights

- Emission dynamics are strongly non-linear
- ML results align with combustion physics
- Data-driven optimization can support industrial decision-making
- Trade-offs between emission reduction and energy output can be quantified

---

## 🛠 Methods Used

- Exploratory Data Analysis (EDA)
- Skewness Correction
- 5-Fold Cross Validation
- Linear Regression
- Random Forest
- XGBoost
- SHAP Explainability
- Partial Dependence Analysis
- Monte Carlo-style Optimization
- Pareto Filtering

---

## 🚀 Industrial Impact

This framework demonstrates how machine learning can function as:

- An emission-aware decision-support system
- A combustion optimization assistant
- A tool for energy-emission trade-off analysis

---

## 👤 Author

Chemical Engineer transitioning into Industrial Machine Learning  
Focused on energy systems and process optimization.
