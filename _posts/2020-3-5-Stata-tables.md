---
layout: post
title: Making Tables in Stata
---

This way of making summary tables turns out very nice results
```
generate dummy = 1
label var dummy "Number of Reporting Agencies"
tabout dummy using agencies.txt, ///
c(mean nvals min nvals max nvals ) f(0) sum ///
h3(nil) ///
rep ///
style(tex) ///
ptotal(none)
```

After wrapping some code around it, the tex table is:
```

```

The end result of which is:

![Reporting Agencies](/images/agencies.jpg "Reporting Agencies in Michigan")

We had to make some adjustments, but the adjustments are syntactical.

See the following link for more information:
http://www.ianwatson.com.au/stata/tabout_tutorial.pdf



In order to generate output tables for multiple regressions, we need to save the result from each regression and then combine them.

```
global crimes l_murder l_mur_shr_r l_mur_p_r l_mur_up_r
```

```
foreach crime in $crimes {
	qui xtreg `crime' law i.year [aweight=popwt],fe vce(cluster state)
	eststo `crime'1

	qui xtreg `crime' law i.year $region [aweight=popwt], fe vce(cluster state)
	eststo `crime'2

	qui xtreg `crime' law i.year $region $xvar [aweight=popwt],fe vce(cluster state)
	eststo `crime'3

* last three columns - option 1: adding in prelaw dummy
	qui xtreg `crime' law i.year $region $xvar prelaw [aweight=popwt], ///
		fe vce(cluster state)
	eststo `crime'4

	qui xtreg `crime' law i.year $region $xvar prelaw $lintrend [aweight=popwt], ///
		fe vce(cluster state)
	eststo `crime'5

	qui xtreg `crime' law i.year $region $xvar prelaw $lintrend $cum_law ///
		[aweight=popwt], fe vce(cluster state) // control for long-term effects of the law
	eststo `crime'6

	esttab `crime'1 `crime'2 `crime'3 `crime'4 `crime'5 `crime'6 using ///
		table_`crime'.tex, starlevels(* 0.1 ** 0.05 *** 0.01) ///
		cells(b(star fmt(%9.3f)) se(par)) scalars(F r2) replace
}
```
