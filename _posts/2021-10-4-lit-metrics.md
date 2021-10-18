---
layout: post
title: Econometrics Literature
date: 2021-10-4 9:00:00 --0000
permalink: /posts/lit-metrics/
---

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