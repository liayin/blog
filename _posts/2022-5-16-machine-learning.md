---
layout: post
title: Machine Learning Algorithms
date: 2022-05-16 11:06:00 --0000
permalink: /posts/machine-learning/
---

Machine learning has been widely adopted to predict outcomes based on existing data. This blog post links to resources on the most common machine learning algorithms.

Table of Contents
* TOC
{:toc}

# Random Forest
Splitting criterion minimizes the Gini impurity (in the case of classification) and the SSE (in case of regression). ([Reference](https://bradleyboehmke.github.io/HOML/random-forest.html))

Splitting criterion optimizes for finding splits associated with group heterogeneity.

[Random Forest in Python (by Will Koehrsen)](https://towardsdatascience.com/random-forest-in-python-24d0893d51c0)

[Grid Search Cross Validation (by Will Koehrsen)](https://towardsdatascience.com/hyperparameter-tuning-the-random-forest-in-python-using-scikit-learn-28d2aa77dd74)

# Causal Random Forest

Splitting criterion optimizes for finding splits associated with treatment effect heterogeneity.

# Oblique Regression Tree

[Cattaneo, Chandak, and Klusowski (2022)](https://arxiv.org/pdf/2210.14429.pdf): Convergence Rates of Oblique Regression Trees for Flexible Function Libraries
- Splits are based on linear combinations of the covariates
- Oracle inequality allows them to be compared with projection pursuit regression and newral networks
- Under suitable conditions, oblique decision trees achieve similar predictive accuracy as neural networks for the same library of regression models - we do not need to always trade-off interpretability with accuracy
