# 🚴 Poisson Regression Case Study – Bike Sharing Data

This project demonstrates a **Bayesian Poisson regression model** applied to a bike-sharing dataset. The goal is to predict the number of bikes rented (`count`) based on temporal and environmental features. The model is implemented in **R** using `rjags` for Bayesian inference.

---

## 📌 Project Overview

* **Dataset**: `bike-train.csv` (subset of bike sharing rental data).
* **Model**: Poisson regression with Jeffreys prior approximations.
* **Bayesian Inference**: Implemented via **JAGS** and sampled with MCMC.
* **Goal**: Evaluate model convergence, prediction accuracy, and residual distribution.

---

## ⚙️ Steps

1. **Exploratory Data Analysis**

   * Inspected structure, missing values, and duplicates.
   * Sampled 1000 rows to reduce computation time.

2. **Model Definition**

   * Poisson likelihood with log link.
   * Priors:

     * Intercept: `Normal(0, 1e-6)`
     * Coefficients: `Normal(0, 1e-6)`

3. **MCMC Sampling**

   * 5 chains with random initial values.
   * Burn-in of 1000 iterations, followed by 10,000 draws.

4. **Model Diagnostics**

   * Geweke, Gelman-Rubin, Raftery, and effective sample size checks.
   * Identified convergence issues in some chains.

5. **Posterior Predictive Checks (PPC)**

   * Generated predicted bike counts.
   * Compared density of true vs. predicted values.
   * Analyzed residual distribution.

---

## 📊 Results

* **Convergence**: Most chains converged (Gelman-Rubin ≈ 1.01).
* **Prediction**: Model reasonably captured the distribution of counts.
* **Residuals**: Mostly centered, but some variation persists.

Visualizations include:

* Density plots comparing true vs. predicted values.
* Residual distribution plots.

---

## 📦 Dependencies

This project was built in **R** with the following packages:

```r
library(rjags)
library(ggplot2)
library(loo)
```

---

## 🚀 How to Run

1. Clone the repo:

   ```bash
   git clone https://github.com/yourusername/poisson-bike-sharing.git
   cd poisson-bike-sharing
   ```
2. Open the RMarkdown file (`poisson_bike.Rmd`) or run the script in R.
3. Ensure `bike-train.csv` is in the same directory.

---

## 🔍 Key Learnings

* Bayesian inference provides flexibility in estimating uncertainty.
* Jeffreys prior (approximated) ensures non-informative parameter estimation.
* MCMC diagnostics are crucial to ensure valid posterior samples.

---

## 📖 Author

👤 **Gervasius Russell**

* 🎓 Data Science Student, BINUS University
* 🌐 [GitHub Profile](https://github.com/yourusername)
* 💼 Aspiring Data Scientist | Bayesian Modeling | Machine Learning
