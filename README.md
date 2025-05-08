# 🔬 Analyzing Deterministic Mathematical Model of Diabetes Mellitus


## 🧠 Project Overview

This research project aims to model and analyze **Type 2 Diabetes Mellitus (T2DM)** using a **deterministic system of ordinary differential equations (ODEs)**, statistical learning, and health analytics. It explores how glucose, insulin, cholesterol (HDL/LDL), and BMI influence diabetes progression and diagnosis.

---

## 🔍 Objectives

- Develop a mathematical model simulating the physiological interaction of diabetes-related metrics  
- Apply linear and multinomial logistic regression to evaluate predictive relationships  
- Use statistical visualization to uncover demographic and health patterns across diabetic states  

---

## 🛠 Methodology

- **ODE-Based Mathematical Modeling**:
  Models glucose, insulin, dietary intake, BMI, HDL, and LDL dynamics  
<pre> ``` dG(t)/dt = k - (k₁ - k₃)·G(t) dI(t)/dt = k₄·G(t) - k₂·I(t) dB(t)/dt = k₆·D(t) - k₇·B(t) dH(t)/dt = -k₉·D(t) - k₁₀·H(t) dL(t)/dt = -k₁₁·D(t) + k₁₂·B(t) - k₁₃·L(t) dD(t)/dt = -k₁₅·I(t) - k₁₆·D(t) ``` </pre>

- **Parameter Estimation**:
  - Optimized using `scipy.optimize.minimize`
  - Minimized Sum of Squared Errors (SSE)
- **Statistical Modeling**:
  - Multinomial logistic regression to predict class (`N`, `P`, `Y`)
  - Linear regression to quantify factor impacts
- **Model Validation**:
  - MSE, R² evaluation
  - Stability analysis using Jacobian matrix eigenvalues

---

## 📊 Key Visualizations & Insights

### 📦 Box & Violin Plot: Age Distribution vs Diabetes Class
- **Diabetic (Y)** group had **higher median age** with broader distribution
- Violin plot showed **dense clustering** around 55–65 for diabetics

### 🧬 Scatter Plot: HDL vs LDL with Cholesterol
- High **LDL** correlated with **increased total cholesterol**
- Low **HDL** with high LDL = higher cardiovascular and diabetic risk

### 📈 Age vs HbA1c
- Positive correlation between **age** and **HbA1c**
- Suggests older individuals are more likely to have elevated blood sugar levels

### 📉 Radar Plot: Health Profiles by Class (Age 30–50)
- Diabetics show **higher average HbA1c, Chol, LDL**
- Non-diabetics show **better lipid profile**

### 🧪 Observed vs Simulated Dynamics
- Simulations closely track observed data for **Glucose, Insulin, BMI, LDL, HDL**
- Confirms model robustness in predicting real-world behavior

---

## 📋 Key Findings

- **Top Predictive Features**:  
  - HbA1c, BMI, VLDL, TG → Strong diabetes indicators  
  - HDL → Protective factor  
- **Regression Accuracy**:  
  - 90.5% model accuracy  
  - High precision & recall for Class Y (Diabetic)  
- **Coefficients**:  
  - AGE & LDL (positive influence)  
  - BMI, HbA1c (negative but strong predictors)

---

## 📈 Classification Report (Excerpt)

| Class | Precision | Recall | F1-Score |
|-------|-----------|--------|----------|
| N     | 0.79      | 0.73   | 0.76     |
| P     | 0.29      | 0.10   | 0.15     |
| Y     | 0.93      | 0.98   | 0.96     |

---

## 📌 Summary

- Deterministic modeling provides a realistic simulation of diabetes progression
- **HbA1c and BMI** are consistently the most influential features
- Results support using personalized models to guide **preventive interventions**

---

## 🔮 Future Scope

- Collect more refined real-world clinical datasets
- Introduce stochasticity or uncertainty modeling in parameter estimation
- Improve model generalizability using ensemble approaches and cross-validation

---

## 💻 Tools Used

- **Python**: SciPy, NumPy, Pandas, Seaborn, Matplotlib, StatsModels
- **Visualization**: Radar plots, 3D scatter, violin/box plots, regression overlays
