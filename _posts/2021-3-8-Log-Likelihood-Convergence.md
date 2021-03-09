---
layout: post
title: Convergence in Log Likelihood
date: 2021-03-08 22:45:00 --0000
---

In R, when I used `clogit`, I encountered the error `Warning message:
In fitter(X, Y, istrat, offset, init, control, weights = weights,  :
  Ran out of iterations and did not converge`

Upon some "Google fu", I found [this page](http://www.talkstats.com/threads/one-for-the-pros-conditional-logistic-regression-discrepancy.6195/), which says "Without checking it out thoroughly, my guess is you have Complete Separation (or close to it). What that would mean is that there aren't enough retr=0 that match up with case=1 (or some other combination). R can't calculate the odds of success if there are no successes in one of your conditions. The odds become infinite."