---
layout: post
title: NIBRS Data from Detroit
---

Code

We set the path and open the file
```
global base `"D:/Research/Data/NIBRS/"'
use "${base}/nibrs_1998-2014_mi.dta"
```

Then we look up Detroit's code from the crosswalk and put it into the file
```
keep if ori=="MI8234900"
```

We can optionally check when the data starts
```
tab modate
```
We can see from the data that Detroit only starts reporting from 1/2005

We count the number of cases there are in each month.
```
bysort year month ori: egen crimes = count(offense)
```

Then we keep only the relevant variables
```
keep modate crimes
duplicates drop
```

Then we plot
```
scatter crimes modate
```

The scatter plot generated is:
![NIBRS Data from Detroit](/images/Detroit.jpg "NIBRS Data from Detroit")
