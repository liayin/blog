---
layout: post
title: Econometrics Literature
date: 2021-10-4 9:00:00 --0000
permalink: /posts/lit-metrics/
---

#### Causal Inference
[Pischke (2021)](https://voxeu.org/article/natural-experimenters-nobel-laureates-david-card-joshua-angrist-and-guido-imbens): Natural experiments in labour economics and beyond: The 2021 Nobel laureates David Card, Joshua Angrist, and Guido Imbens

#### Regression Discontinuity
[Cattaneo, Keele & Titiunik (2021)](https://arxiv.org/pdf/2110.08410.pdf): Covariate Adjustment in Regression Discontinuity Designs

#### Peer Effects Model
[Solvsten (2021)]: Estimation and Inference in a Peer Effects Model with Heteroskedasticity

#### Clustering
- [Abadie, Athey, Imbens & Wooldridge (2021)](https://economics.mit.edu/faculty/abadie/papers): Clustering Adjustments to Standard Errors
    - Liang-Zeger (cluster) vs Eiker-Huber-White (heterogeneity-robust) variances - can be inaccurate
    - proposed estimator is more accurate
        - In cross-sectional settings where there are many clusters
    - Takeaway: should think about sampling and assignment mechanism

#### Misc
- [Graham, Hirano, Imbens (2021)](https://doi.org/10.1017/S0266466621000372): the ET Interview: Professor Gary Chamberlain
    - Econometric Theory
    - Summary: multivariable regression resulted from the siblings work, probably inspired the individual fixed effects.

#### Mixture Models
- [Kwon & Mbakop (2021)](https://wpsites.ucalgary.ca/eric-mbakop/wp-content/uploads/sites/32/2020/06/Revision.pdf): Estimation of the Number of Components of Non-parametric Multivariate Finite Mixture Models
    - Published in: Annals of Statistics
    - Propose a novel estimator for the number of mixture components (denoted by M) in a non-parametric finite mixture model
    - Setting: The analyst has repeated observations of K >= 2 variables that are conditionally independent given a finitely supported latent variable with M support points
    - Condition: an integral operator T that is identified from the data has rank equal to M (under a mild assumption on the joint distribution of the observed and latent variables)
    - Propose: an estimator of M which consists of a thresholding rule that counts the number of singular values of a consistent estimator of T that are greater than a data-driven threshold.
    - Prove: 
        - Their estimator of M is consistent
        - Establish non-asymptotic results which provide finite sample performance guarantees for their estimators
    - Monte Carlo study which shows that their estimator performs well for samples of moderate size

#### Machine Learning
- [Montiel Olea, Ke, and Nesbit (2021)](http://www.joseluismontielolea.com/papers.html): Robust Machine Learning Algorithms for Text Analysis
    - Standard text analysis methods have flat regions
    - Use Bayesian methods to remove the problem

#### Policy evaluation
- [Arkhangelsky & Korovkin (2021)](https://arxiv.org/pdf/1905.13660.pdf): On Policy Evaluation with Aggregate Time-Series Shocks
    - New algorithm for estimating treatment effects
        - When exogenous variation comes from aggregate time-series shocks
    - Estimator combines data-driven unit-level weights with a time-series model
    - Use the unit weights to control for unobserved aggregate confounders
    - Use the time-series model to extract the quasi-random variation from the observed shock