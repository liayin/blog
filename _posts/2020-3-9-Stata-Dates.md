---
layout: post
title: Dates in Stata
---

Change annual data into monthly:

```
use population.dta
keep if statename=="Michigan"
expand 12
by year, sort: gen month = _n
gen monthly_date = mofd(mdy(month, 1, year))
format monthly_date %tm
* Each year's population is recorded for month 7
replace population = . if inlist(month, 1, 2, 3, 4, 5, 6, 8, 9, 10, 11, 12)
* Interpolate/extrapolate
ipolate population monthly_date, epolate generate(population_ep)
```
