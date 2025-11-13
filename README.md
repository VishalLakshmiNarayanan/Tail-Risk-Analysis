

<h1><b>Tail Risk Management</b></h1>
<h3>A Risk-Aware Ensemble Framework for Predicting Catastrophic Insurance Losses</h3>

<p>
Predicting average losses is easy forecasting the <b>catastrophic</b> ones is what keeps insurers up at night.  
Tail Risk Management introduces a modern, risk-sensitive modeling pipeline that goes beyond MSE to focus on heavy-tailed claim behavior using <b>Loss-at-Risk (LaR)</b>, <b>CVaR</b>, and a <b>Tail-Aware Meta-Ensemble</b>.
</p>

<p>
  <img src="https://img.shields.io/badge/Status-Active-success?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Python-3.10+-skyblue?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/Jupyter-Notebooks-orange?style=for-the-badge&logo=jupyter"/>
  <img src="https://img.shields.io/badge/License-MIT-blue?style=for-the-badge"/>
</p>

---

<!-- ============================================================= -->

<!-- 📌 PROJECT OVERVIEW -->

<!-- ============================================================= -->

<h2>Overview</h2>

Tail Risk Management is a quantitative modeling framework built to answer a crucial question in actuarial science:

> **“Why do standard ML models fail on large, catastrophic claims and how can we fix it?”**

This project uses a filtered subset (~69K records) of the Mendeley automobile insurance dataset to:

* Identify tail-risk failure modes in standard regression models
* Build custom risk-aware loss functions
* Evaluate catastrophic prediction accuracy (1%–5% tail)
* Construct a **CVaR-weighted ensemble**
* Build a final **Tail-Aware Meta-Learner** using meta-features

It is designed to be fully reproducible, explainable, and extensible.

---

<!-- ============================================================= -->

<!-- 🚀 KEY FEATURES -->

<!-- ============================================================= -->

<h2>Key Features</h2>

<div>

| Category               | Description                                                 |
| ---------------------- | ----------------------------------------------------------- |
| **Baseline Modeling**  | Linear Regression, RF, GBM, XGBoost on raw and log targets  |
| **Tail-Aware Losses**  | Custom Loss-at-Risk, CVaR residual modeling, tail weighting |
| **Ensemble Methods**   | Voting, Stacking, CVaR-weighted Ensemble                    |
| **Meta-Learning**      | Out-of-fold meta-features + Tail-Aware Meta-Model           |
| **Visual Analytics**   | Tail distributions, residual plots, quantile diagnostics    |
| **Evaluation Metrics** | MSE, RMSE, CVaR Loss, Extreme Tail MSE (top 1%)             |

</div>

---

<!-- ============================================================= -->

<!-- 📊 DATASET -->

<!-- ============================================================= -->

<h2>Dataset</h2>

<p>
<a href="https://data.mendeley.com/datasets/5cxyb5fp4f/2">
  <img src="https://img.shields.io/badge/Mendeley%20Dataset-Automobile%20Insurance-blue?style=for-the-badge&logo=databricks" />
</a>
</p>

* **69,000+ policy-year records**
* Contains policy, demographic, vehicle, and claims history variables
* Only non-zero claim histories retained for modeling tail behavior
* Target variable: `Cost_claims_year`

---

<!-- ============================================================= -->

<!-- 🧠 MODELING PIPELINE -->

<!-- ============================================================= -->

<h2>Modeling Pipeline</h2>

<div>

<table>
<tr>
<td width="50%" valign="top">

### **1. Baseline Models**

* Linear Regression
* Random Forest
* Gradient Boosting
* XGBoost

</td>
<td width="50%" valign="top">

### **2. Tail-Aware Losses**

* Loss-at-Risk (LaR)
* CVaR residual analysis
* LaR-weighted Linear Regression

</td>
</tr>

<tr>
<td width="50%" valign="top">

### **3. Ensemble Methods**

* Simple Voting
* Stacking
* CVaR-Weighted Ensemble

</td>
<td width="50%" valign="top">

### **4. Tail-Aware Meta-Learner (Final Stage)**

* Out-of-Fold meta-features
* LaR meta-feature
* Quantile Regression / CVaR-Optimized meta-model

</td>
</tr>
</table>

</div>

---

<!-- ============================================================= -->

<!-- 📈 PERFORMANCE SUMMARY -->

<!-- ============================================================= -->

<h2>Performance Summary</h2>

<div>

| Model                      | Overall MSE            | Extreme Tail MSE (99th pct) | CVaR Loss (95%) |
| -------------------------- | ---------------------- | --------------------------- | --------------- |
| Random Forest              | High                   | High                        | High            |
| Gradient Boosting          | Moderate               | High                        | High            |
| XGBoost                    | Moderate               | High                        | Moderate        |
| LaR Regression             | Slightly Worse Overall | Better Tail                 | Better CVaR     |
| **Stacking Ensemble**      | **Best Overall MSE**   | Worst Tail                  | Worst CVaR      |
| **CVaR-Weighted Ensemble** | Good Overall           | **Best Tail**               | **Best CVaR**   |

</div>

> 📌 **Insight:** The CVaR-Weighted Ensemble sacrifices a bit of average accuracy to gain stability in catastrophic scenarios—precisely what insurers want.

---

<!-- ============================================================= -->

<!-- 🛠 TECH STACK -->

<!-- ============================================================= -->
## Tech Stack

<div>

## Tech Stack

<!-- Languages -->
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" height="45" /> 
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/jupyter/jupyter-original.svg" height="45" />

<!-- Data / ML Libraries -->
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/numpy/numpy-original.svg" height="45" />
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/pandas/pandas-original.svg" height="45" />
<img src="https://upload.wikimedia.org/wikipedia/commons/0/05/Scikit_learn_logo_small.svg" height="45" />

<!-- Matplotlib (PNG, visible on dark) -->
<img src="https://upload.wikimedia.org/wikipedia/commons/8/84/Matplotlib_icon.svg" height="45" />

<!-- Seaborn (transparent -> use logo with white frame) -->
<img src="https://seaborn.pydata.org/_static/logo-wide-lightbg.svg" height="45" />


<!-- Tools -->
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/git/git-original.svg" height="45" />
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/github/github-original.svg" height="45" />
<img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/vscode/vscode-original.svg" height="45" />


</div>



<!-- ============================================================= -->

<!-- 📚 RESEARCH DIRECTIONS -->

<!-- ============================================================= -->

<h2>Ongoing Research Directions</h2>

<div>

* Tail-focused Gradient Boosting (Quantile Loss)
* Neural networks trained directly on CVaR loss
* Extreme Value Theory (EVT) integration
* Meta-feature engineering for catastrophic detection
* Solvency-II aligned risk modeling

</div>

---


<!-- ============================================================= -->

<!-- 🙌 ACKNOWLEDGEMENTS -->

<!-- ============================================================= -->

<h2>Acknowledgements</h2>

Dataset provided by
**Mendeley Data – Automobile Insurance Claims (Version 2)**
Research inspired by actuarial risk modeling and financial tail-risk literature.

---

