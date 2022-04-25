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

[de Chaisemartin & D'Haultfoeuille (2020)](https://arxiv.org/pdf/1803.08807.pdf): heterogeneous treatment effects
[Stata package](https://www.openicpsr.org/openicpsr/project/118363/version/V2/view?flag=follow&pageSelected=0&pageSize=10&sortOrder=(?title)&sortAsc=true)
[R package](https://cran.r-project.org/web/packages/TwoWayFEWeights/TwoWayFEWeights.pdf)

#### Group-time treatment effect

Reference: [Callaway & Sant'Anna (2020)](https://arxiv.org/abs/1803.09015)

> <img src="https://render.githubusercontent.com/render/math?math=ATT(g,t) = \mathbf{E}_{g}[Y_t(g) - Y_t(0)|G_g=1]">

To put the above equation into English, it means that for group *g* at time *t*, the average treatment effect on the treated is the difference in outcome for this group when they are treated compared to when they are not (the counterfactual outcome).  

> <img src="https://render.githubusercontent.com/render/math?math=Y = \alpha^{g,t}_1 %2B \alpha^{g,t}_2 \cdot G_g %2B \alpha^{g,t}_3 \cdot 1\{T = t\} %2B \beta^{g,t} \cdot (G_g \times 1\{T = t\}) %2B \gamma \cdot X %2B \epsilon^{g,t}">

The above equation applies to time period *t* for a group that went through treatment in time period *g*. The coefficient <img src="https://render.githubusercontent.com/render/math?math=\beta^{g,t}"> captures the *ATT(g, t)*.

> <img src="https://render.githubusercontent.com/render/math?math=Y_{i,t} = \alpha_t %2B \alpha_g %2B \sum^{-2}_{e=-K} \delta^{anticip}_{e} \cdot D^e_{i,t} %2B \sum_{e=0}^{L} \beta_e \cdot D^{e}_{i,t} %2B \nu_{i,t}">

The above equation is the event study formula for each group. the <img src="https://render.githubusercontent.com/render/math?math=\delta"> are the anticipation effects, and the <img src="https://render.githubusercontent.com/render/math?math=\beta"> are the treatment effects.

The aggregation is done by <img src="https://render.githubusercontent.com/render/math?math=\theta^O_{sel} = \sum_{g \in \mathcal{G}} \theta_{sel}(g) P(G = g|G \leq \Tau)">

where <img src="https://render.githubusercontent.com/render/math?math=\theta_{sel}(g) = \frac{1}{\Tau - g %2B 1} \sum_{t=g}^{\Tau} ATT(g,t)">

It first averages across all time periods for each group, and then averages across groups.

[Callaway & Sant'Anna (2020) R package](https://bcallaway11.github.io/did/)


## Post-estimation
There are a lot of post estimation that can be carried out. For example, for `xtlogit` in stata, postestimation commands can be found [here](https://www.stata.com/manuals/xtxtlogitpostestimation.pdf).
