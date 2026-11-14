# Wasserstein Distributionally Robust Regression

An implementation of Wasserstein distributionally robust optimization (DRO) for one-dimensional linear regression, formulated as a second-order cone program (SOCP) and solved in Julia.

This project investigates whether distributional robustness can improve out-of-sample predictive performance when training data is limited.

## Overview

Conventional empirical risk minimization (ERM) optimizes a model against the observed training distribution. With small datasets, this can lead to unstable estimates and poor generalization.

Wasserstein DRO addresses this problem by optimizing against a family of probability distributions within a specified Wasserstein distance of the empirical distribution.

This project compares Wasserstein DRO against standard empirical risk minimization through repeated numerical experiments. Here, this project uses sample average approximation (SAA) as the baseline model.

## Implementation

- **Language:** Julia
- **Optimization:** JuMP and conic optimization
- **Model:** One-dimensional linear regression
- **Evaluation:** Monte Carlo simulation and out-of-sample error analysis

The DRO formulation is implemented as a second-order conic program.

## Results

In a 400-trial Monte Carlo experiment with six training observations per trial, the DRO estimator achieved approximately 32% lower variance in out-of-sample error than the empirical risk minimization baseline.

The experiment illustrates the potential of distributional robustness to improve the stability of predictive performance in small-sample settings.



## Technical Report

For the mathematical formulation, derivations, experimental methodology, and detailed analysis, see the full technical report.

## Code

The Julia implementation and simulation experiments are available in **wasserstein_dro.ipynb**.

## References
1. Dimitris Bertsimas, Vishal Gupta, and Nathan Kallus. Robust sample average approximation. Mathematical Programming, 171(1–2):217–282, 2018.
2. Ruidi Chen and Ioannis Ch. Paschalidis. A robust learning approach for regression models based on distributionally robust optimization. Journal of Machine Learning Research, 19(1):517–564, 2018.
3. Daniel Kuhn, Saeed Shafiee, and Wolfram Wiesemann. Distributionally robust optimization. Acta Numerica, 34:579–804, 2025.
4. Peyman Mohajerin Esfahani and Daniel Kuhn. Data-driven distributionally robust optimization using the wasserstein metric: performance guarantees and tractable reformulations. Mathematical Programming, 171(1–2):115–166, 2018.
5. Min-Cheng Yue, Daniel Kuhn, and Wolfram Wiesemann. On linear optimization over wasserstein balls. Mathematical Programming, 195(1–2):1107–1122, 2022.
