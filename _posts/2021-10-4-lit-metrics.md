---
layout: post
title: Econometrics Literature
date: 2021-10-4 9:00:00 --0000
permalink: /posts/lit-metrics/
---

#### Causal Inference
[Pischke (2021)](https://voxeu.org/article/natural-experimenters-nobel-laureates-david-card-joshua-angrist-and-guido-imbens): Natural experiments in labour economics and beyond: The 2021 Nobel laureates David Card, Joshua Angrist, and Guido Imbens

[Mogstad, Torgovitsky & Walters (2021)](https://pubs.aeaweb.org/doi/pdfplus/10.1257/aer.20190221): The Causal Interpretation of Two-Stage Least Squares with Multiple Instrumental Variables
- Empirical researchers often combine multiple instrumental variables (IVs) for a single treatment using two-stage least squares (2SLS). When treatment effects are heterogeneous, a common justification for including multiple IVs is that the 2SLS estimand can be given a causal interpretation as a positively weighted average of local average treatment effects (LATE). This justification requires the well-known monotonicity condition.
- They show that with more than one instrument, this condition can only be satisfied if choice behavior is effectively homogeneous.
- Based on this finding, they consider the use of multiple IVs under a weaker, partial monotonicity condition. They characterize empirically verifiable sufficient and necessary conditions for the 2SLS estimand to be a positively weighted average of LATEs under partial monotonicity.
- They apply these results to an empirical analysis of the returns to college with multiple instruments. They show that the standard monotonicity condition is at odds with the data. Nevertheless, their empirical checks reveal that the 2SLS estimate retains a causal interpretation as a positively weighted average of the effects of college attendance among complier groups.

[Broderick, Giordano & Meager (2021)](https://arxiv.org/pdf/2011.14999.pdf): An Automatic Finite-Sample Robustness Metric: Can Dropping a Little Data Change Conclusions?
- They found a way to assess the robustness of regression results by removing a small number of observations
    - They invented a framework for selecting observations to remove such that they have the largest impact on the regression result
        - This method is called Approximate Maximum Influence Perturbation
- For the observations selected, the metric records the lower bound of the difference between the original estimator and the new estimator. Therefore, as long as the metric indicates a violation of robustness, the original estimator should be re-examined

[Liu, Poirier & Shiu (2021)](https://arxiv.org/abs/2105.12891): Identification and Estimation of Average Partial Effects in Semiparametric Binary Response Panel Models
- The paper point-identify APE in binary response panel models under an index sufficiency assumption on the unobserved heterogeneity
- Three-step semiparametric estimator:
    - Estimate the common parameters
    - Estimate the conditional expectation of the outcomes given the indices and a generated regressor that depends on first-step estimates
    - Avg derivatives of this conditional expectation to obtain a partial mean that estimates the APE

[Feng (2021)](https://drive.google.com/file/d/1Kddkh705vk-1uhq0y5xYXWNdTabmclcN/view): Causal Inference in Possibly Nonlinear Factor Models
- Treatment effects models with noisily measured confounders
    - Noisy measurements are associated with the underlying latent confounders through an unknown, possibily nonlinear factor structure
        - The main building block is a local principal subspace approximation procedure that combines K-nearest neighbors matching and principal component analysis

#### Regression Discontinuity
[Cattaneo, Keele & Titiunik (2021)](https://arxiv.org/pdf/2110.08410.pdf): Covariate Adjustment in Regression Discontinuity Designs

#### Peer Effects Model
Solvsten (2021): Estimation and Inference in a Peer Effects Model with Heteroskedasticity

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

#### Partial Identification
[Cattaneo, Cheung, Ma & Masatlioglu (2021)](https://arxiv.org/pdf/2110.10650.pdf): Attention Overload
- They introduce an Attention Overload Model that captures the idea that alternatives compete for the decision marker's attention, and hence the attention frequency each alternative receives decreases as the choice problem becomes larger.
- Using this nonparametric restriction on the random attention formation, they show that a fruitful revealed preference theory can be developed, and provide testable implications on the observed choice behavior that can be used to partially identify the decision maker's preference.
- They also provide novel partial identification results on the underlying attention frequency, thereby offering the first nonparametric identification result of (a feature of) the random attention formation mechanism in the literature.
- Building on their partial identification results, for both preferences and attention frequency, they develop econometric methods for estimation and inference.
    - The procedures remain valid even in settings with large number of alternatives and choice problems.
- They also provide a software package in R implementing their empirical methods, and illustrate them in a simulation study.