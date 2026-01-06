# Hierarchical Bayesian Modeling for Student Dropout Prediction

This project implements a **Hierarchical Bayesian Logistic Regression** model to analyze and predict student dropout and academic success. By utilizing probabilistic programming, the analysis quantifies the uncertainty of socio-economic and academic factors while accounting for the structural differences across various academic courses.

## Project Overview
Predicting student attrition is a complex task where global patterns often fail to capture local nuances (e.g., the impact of age might differ between a Nursing major and a Management major). This project addresses this by implementing a hierarchical model that allows for "varying intercepts" and "varying slopes" across 17 different academic programs.

## Technical Implementation
* **Framework:** Built using **PyMC** for probabilistic programming and **ArviZ** for posterior analysis.
* **Modeling Approach:** * **Hierarchical Structure:** Course-level grouping to capture inter-program variance.
    * **Likelihood:** Bernoulli distribution for binary classification (Dropout vs. Success).
    * **Priors:** Weakly informative Normal priors for fixed effects and Half-Normal priors for group-level standard deviations.
* **Inference:** Utilized **Markov Chain Monte Carlo (MCMC)** sampling via the **NUTS (No-U-Turn Sampler)** algorithm.
* **Diagnostics:** Validated model convergence using **R-hat** metrics and effective sample size (ESS) analysis.

## Key Findings
* **Curricular Stability:** The number of approved units in the first semester emerged as the most critical predictor of long-term retention.
* **Socio-Economic Impact:** Scholarship status showed a highly significant posterior probability of reducing dropout risk.
* **Uncertainty Quantification:** Unlike standard logistic regression, this model provides credible intervals for every coefficient, offering a more reliable basis for institutional decision-making.

## Tech Stack
* **Language:** Python
* **Probabilistic Programming:** PyMC
* **Visualization/Diagnostics:** ArviZ, Matplotlib, Seaborn
* **Data Processing:** Pandas, Scikit-learn
