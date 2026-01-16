## TITLE:  
Bayesian Exam Score Predictor (PyMC)

## Description:
A simple Bayesian regression model built using PyMC to predict exam scores based on study hours and midterm performance.

## Motivation
This project was built as a learning exercise to understand Bayesian modeling workflows in PyMC, including prior specification, posterior inference using NUTS, and posterior predictive checks. The goal was to move beyond running examples and fully understand how a Bayesian model is constructed and interpreted end-to-end.

## Model Overview
The model is a Bayesian linear regression where the final exam score is modeled as a function of:
- Hours studied
- Midterm exam score

## Priors
- Intercept: Normal(50, 20)
- Study hours coefficient: Normal(1, 1)
- Midterm score coefficient: Normal(0.5, 0.5)
- Observation noise: HalfNormal(10)

These priors reflect reasonable expectations about exam scores while remaining weakly informative.

## Posterior & Predictive Analysis
Posterior samples are obtained using `pm.sample`. Posterior predictive samples are generated using `pm.sample_posterior_predictive` to assess how well the model reproduces observed exam scores. The predictive distribution is summarized using posterior means and 95% credible intervals.

## Data
The dataset used in this project is synthetically generated for demonstration purposes and consists of 100 observations. Final exam scores are generated as a linear combination of study hours and midterm scores with added Gaussian noise.

## How to Run
The easiest way to run this project is via Google Colab:

[Open in Colab](https://colab.research.google.com/drive/1Zh_YJl1_QipkttsYNFZYDWB2ba4S9EBh?usp=sharing)

Alternatively, the notebook can be run locally after installing dependencies:
pymc arviz pandas numpy

## Key Learnings
- How to specify and reason about priors in a Bayesian regression
- How NUTS performs posterior inference in PyMC
- How to generate and interpret posterior predictive distributions
- The importance of model checking and uncertainty quantification



