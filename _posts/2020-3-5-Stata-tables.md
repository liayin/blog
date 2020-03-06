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

The end result of which is:

![Reporting Agencies](/images/agencies.jpg "Reporting Agencies in Michigan")

We had to make some adjustments, but the adjustments are syntactical.

See the following link for more information:
http://www.ianwatson.com.au/stata/tabout_tutorial.pdf
