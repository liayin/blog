---
layout: post
title: Panel data modeling for the Stand Your Ground Law project
---

The baseline specification is very straightforward. Note that both states and years are binary variables.

![Baseline specification](/images/baseline.jpg "Baseline specification")

Then we added region-by-year fixed effects to control for region-specific linear trends. Regions are binary variables. We would like to see how different the time trends are between the baseline trend and each other region's.

![Regional trends](/images/region.jpg "Regional trends")

Here is the structure of the regional data:

![Regional data](/images/region_data.jpg "Regional data")

Then we controlled for time-varying factors:

![Time-varying Factors](/images/time_varying.jpg "Time-varying Factors")

Then we controlled for Ashenfelter's dip. Namely, if there is an increased amount of murder two years prior to the law passing, the prelaw dummy would be able to capture this effect.

![Controlling for Ashenfelter's Dip](/images/prelaw.jpg "Controlling for Ashenfelter's Dip")

The structure of the prelaw dummy is:

![Controlling for Ashenfelter's Dip - Data](/images/prelaw_data.jpg "Controlling for Ashenfelter's Dip - Data")

Then we controlled for state-specific trends:

![Controlling for state-specific trends](/images/state_trend.jpg "Controlling for state-specific trends")

Data related to the state-specific trends. Note that it is the product of a discrete random variable (year) and a binary variable (state_i)

![Controlling for state-specific trends - Data](/images/state_trend_data.jpg "Controlling for state-specific trends - Data")
