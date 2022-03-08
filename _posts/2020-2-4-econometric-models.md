---
layout: post
title: Econometric Models
date: 2020-02-04 17:03:00 --0000
permalink: /posts/metrics-models
---

#### IV
- [IV overview](http://web.uvic.ca/~hschuetz/econ499/iv.pdf)

- IV vs OLS (Reference [here](https://donskerclass.github.io/EconometricsII/MoreIV.html))
![measurement-error bias](/images/measurement-error bias.png "Measurement error bias")



#### ARIMA
ARIMA: Auto Regressive Integrated Moving Average. It explains a given time series based on its own past values (its own lags and the lagged forecast errors), so that equation can be used to forecast future values.

[Regression kink design](https://blogs.worldbank.org/impactevaluations/tools-trade-regression-kink-design)

## DiD
[Callaway & Sant'Anna (2020) R package](https://bcallaway11.github.io/did/)

[de Chaisemartin & D'Haultfoeuille (2020)](https://arxiv.org/pdf/1803.08807.pdf): heterogeneous treatment effects
[Stata package](https://www.openicpsr.org/openicpsr/project/118363/version/V2/view?flag=follow&pageSelected=0&pageSize=10&sortOrder=(?title)&sortAsc=true)
[R package](https://cran.r-project.org/web/packages/TwoWayFEWeights/TwoWayFEWeights.pdf)


## Post-estimation
There are a lot of post estimation that can be carried out. For example, for `xtlogit` in stata, postestimation commands can be found [here](https://www.stata.com/manuals/xtxtlogitpostestimation.pdf).
