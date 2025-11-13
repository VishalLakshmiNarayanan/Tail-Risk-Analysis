<h1><b>Tail Risk Management</b></h1>
<h3>A Risk-Aware Ensemble Framework for Catastrophic Insurance Severity Modeling</h3>

<p>
Predicting average losses is easy — it’s the <b>catastrophic</b> ones that threaten solvency.<br>
Tail Risk Management introduces a modern, risk-sensitive modeling pipeline that goes beyond MSE to focus on heavy-tailed claim behavior using <b>Loss-at-Risk (LaR)</b>, <b>CVaR</b>, and a <b>Tail-Aware Hybrid Meta-Ensemble</b>.
</p>

<p>
  <img src="https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Python-3.10+-skyblue?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/Jupyter-Notebooks-orange?style=for-the-badge&logo=jupyter"/>
  <img src="https://img.shields.io/badge/License-MIT-blue?style=for-the-badge"/>
</p>



## Overview

Tail Risk Management answers a crucial actuarial question:

> **“Why do standard ML models fail on catastrophic losses — and how do we fix it?”**

Using a filtered subset (~69K claim-positive records) from the Mendeley automobile insurance dataset, this project:

- Diagnoses tail-risk failure modes in standard ML models  
- Builds custom <b>risk-aware loss functions</b>  
- Evaluates predictive stability in the <b>top 1% catastrophic tail</b>  
- Constructs <b>Tail-Focused Meta-Features</b>  
- Trains <b>Quantile</b>, <b>CVaR-Optimized</b>, and <b>LaR</b> meta-learners  
- Produces a final <b>Hybrid TailRisk Model</b>  

This project is **fully reproducible**, **statistically rigorous**, and aligned with real-world actuarial practice.

---

## Key Features

| Category               | Description                                                     |
| ---------------------- | --------------------------------------------------------------- |
| **Baseline Modeling**  | Linear Regression, RF, GBM, XGBoost                             |
| **Tail-Aware Losses**  | Loss-at-Risk (LaR), CVaR residual analysis, tail weighting      |
| **Ensemble Methods**   | Voting, Stacking, CVaR-Weighted Ensemble                        |
| **Meta-Learning**      | OOF meta-features, Quantile Regression, LaR Meta-Model          |
| **Hybrid Model**       | λ-blended Quantile + LaR Meta-Learner (Final TailRisk Model)    |
| **Evaluation Metrics** | MSE, RMSE, CVaR Loss, Extreme-Tail MSE (Top 1%), TCR, Detection |

---

## Dataset

<p>
<a href="https://data.mendeley.com/datasets/5cxyb5fp4f/2">
  <img src="https://img.shields.io/badge/Mendeley%20Dataset-Automobile%20Insurance-blue?style=for-the-badge&logo=databricks" />
</a>
</p>

- **69,000+ policy-year records**  
- Policy, demographic, vehicle, and claims history features  
- Only non-zero claim histories retained  
- Target variable: **Cost of Claims in Year**

---

## Modeling Pipeline

<table>
<tr>
<td width="50%" valign="top">

### **1. Baseline Models**
- Linear Regression (MSE)
- Random Forest  
- Gradient Boosting  
- XGBoost  

</td>
<td width="50%" valign="top">

### **2. Tail-Aware Losses**
- Loss-at-Risk (LaR) Weighted Regression  
- CVaR residual modeling  
- α-weighted tail emphasis  

</td>
</tr>

<tr>
<td width="50%" valign="top">

### **3. Ensemble Methods**
- Simple Voting  
- Stacking  
- CVaR–Weighted Ensemble  

</td>
<td width="50%" valign="top">

### **4. Tail-Aware Meta-Learners**
- Out-of-Fold Meta-Feature Matrix (4-D)  
- 95th Percentile Quantile Regression  
- LaR Meta-Model (Convex Weight Optimization)  
- λ-Blended Hybrid Model (Final)  

</td>
</tr>
</table>

---

## Final Results

### 🔥 **Catastrophic Prediction Performance (Final Hybrid Model — λ = 0.25)**

| Metric | Baseline LR | TailRisk Hybrid | Improvement |
|--------|-------------|-----------------|-------------|
| **Extreme-Tail MSE (99%+)** | 260.9M | **252.5M** | +3.21% |
| **CVaR(95%) Residuals** | 3146 | **2823** | +10.25% |
| **Detection @ 90%** | 3.08% | **6.09%** | +3.01 pp |
| **Detection @ 95%** | 0.83% | **2.47%** | +1.64 pp |
| **TCR @ 95%** | 0.165 | **0.306** | +0.141 |
| **TCR @ 99%** | 0.058 | **0.102** | +0.044 |

> 📌 **Interpretation:**  
> The Hybrid TailRisk Model achieves higher catastrophic sensitivity, improved tail coverage, and lower expected shortfall — exactly the behavior required for actuarial risk management.

---

## Performance Summary (All Models)

| Model                    | Overall MSE | Extreme Tail MSE | CVaR(95%) |
|-------------------------|-------------|------------------|-----------|
| Linear Regression (MSE) | 2.81M       | 260.9M           | 54.35M    |
| LaR Regression          | 2.81M       | 259.1M           | 53.86M    |
| Random Forest           | High        | High             | High      |
| Gradient Boosting       | Moderate    | High             | High      |
| XGBoost                 | Moderate    | High             | Moderate  |
| Voting Ensemble         | 3.08M       | 261.3M           | 54.44M    |
| Stacking Ensemble       | 2.86M       | 266.6M           | 55.98M    |
| **Quantile Meta (95%)** | 5.12M       | **235.1M**       | **47.72M** |
| **LaR Meta**            | **2.81M**   | 259.1M           | 53.85M    |
| **Hybrid (Final)**      | 2.97M       | **252.5M**       | 52.04M    |

---

## Tech Stack
<p>
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" height="45" /> 
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/jupyter/jupyter-original.svg" height="45" />

<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/numpy/numpy-original.svg" height="45" />
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/pandas/pandas-original.svg" height="45" />
<img src="https://upload.wikimedia.org/wikipedia/commons/0/05/Scikit_learn_logo_small.svg" height="45" />
<img src="https://upload.wikimedia.org/wikipedia/commons/8/84/Matplotlib_icon.svg" height="45" />
<img src="https://seaborn.pydata.org/_static/logo-wide-lightbg.svg" height="45" />

<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/git/git-original.svg" height="45" />
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/github/github-original.svg" height="45" />
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/vscode/vscode-original.svg" height="45" />
</p>

## Research Directions

- Tail-focused Gradient Boosting (Quantile / Asymmetric Loss)  
- Neural networks trained directly on CVaR and LaR objectives  
- Extreme Value Theory (EVT) integration  
- Meta-feature engineering for catastrophe detection  
- Solvency-II aligned risk modeling  
- Distributional regression for full-loss density modeling  

---

## Acknowledgements

Dataset:  
**Mendeley Data — Automobile Insurance Claims (Version 2)**  
Research inspired by actuarial science, financial tail-risk modeling, and solvency analytics.

---
