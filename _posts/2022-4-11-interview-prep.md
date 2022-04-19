---
layout: post
title: Interview Prep
date: 2022-4-11 9:00:01 --0000
permalink: /posts/interview-prep/
---

### <ins>Causal Inference</ins>


#### <ins>RD</ins>
Assumptions:
- Continuity: probability of treatment is constant

Effects:
- LATE

Procedure:
- Center variable at 0
- Regress
    - regression with variable that denotes cutoff
    - Local linear nonparametric regression ()
    - Regress with kernel

- Fuzzy RD
    - Two-stage least squares regression

#### <ins>AB Testing</ins>
Comparing two samples
<!-- $$
\hat{p}_{pool} = \frac{X_{cont} + X_{exp}}{N_{cont} + N_{exp}} \\
$$ --> 

<div align="center"><img style="background: white;" src="https://render.githubusercontent.com/render/math?math=%5Chat%7Bp%7D_%7Bpool%7D%20%3D%20%5Cfrac%7BX_%7Bcont%7D%20%2B%20X_%7Bexp%7D%7D%7BN_%7Bcont%7D%20%2B%20N_%7Bexp%7D%7D%20%5C%5C%0D"></div>


<!-- $$
SE_{pool} = \sqrt{\hat{p}_{pool} * (1 - \hat{p}_{pool}) * (\frac{1}{N_{cont}} + \frac{1}{N_{exp}})}
$$ --> 

<div align="center"><img style="background: white;" src="https://render.githubusercontent.com/render/math?math=SE_%7Bpool%7D%20%3D%20%5Csqrt%7B%5Chat%7Bp%7D_%7Bpool%7D%20*%20(1%20-%20%5Chat%7Bp%7D_%7Bpool%7D)%20*%20(%5Cfrac%7B1%7D%7BN_%7Bcont%7D%7D%20%2B%20%5Cfrac%7B1%7D%7BN_%7Bexp%7D%7D)%7D%0D"></div>

<!-- $$
\hat{d} = \hat{p}_{exp} - \hat{p}_{cont}
$$ --> 

<div align="center"><img style="background: white;" src="https://render.githubusercontent.com/render/math?math=%5Chat%7Bd%7D%20%3D%20%5Chat%7Bp%7D_%7Bexp%7D%20-%20%5Chat%7Bp%7D_%7Bcont%7D%0D"></div>

<!-- $$
H_{0}: d = 0
$$ --> 

<div align="center"><img style="background: white;" src="https://render.githubusercontent.com/render/math?math=H_%7B0%7D%3A%20d%20%3D%200%0D"></div>

<!-- $$
\hat{d} \sim \mathcal{N} (0, SE_{pool})
$$ --> 

<div align="center"><img style="background: white;" src="https://render.githubusercontent.com/render/math?math=%5Chat%7Bd%7D%20%5Csim%20%5Cmathcal%7BN%7D%20(0%2C%20SE_%7Bpool%7D)%0D"></div>

<!-- $$
\hat{d} > 1.96*SE_{pool}
$$ --> 

<div align="center"><img style="background: white;" src="https://render.githubusercontent.com/render/math?math=%5Chat%7Bd%7D%20%3E%201.96*SE_%7Bpool%7D%0D"></div>

or 

<!-- $$
\hat{d} < -1.96*SE_{pool}
$$ --> 

<div align="center"><img style="background: white;" src="https://render.githubusercontent.com/render/math?math=%5Chat%7Bd%7D%20%3C%20-1.96*SE_%7Bpool%7D%0D"></div>

reject null.

### <ins>Other</ins>
#### <ins>Chi-squared test:</ins>
- Usage:
    - Test for correlation between categorical variables
    - Test for variance

#### <ins>Binomial</ins>
- Assumptions:
    - iid
