---
layout: post
title: Regression Discontinuity
---
Regression discontinuity tries to discern if there is a break and a slope change at a certain point. Let's look at an example:

![Michigan](/images/michigan.jpg "Crime Incidences in Parts of Michigan")

We would like to see if there is a jump or a slope change at the point when the law was passed. We use three variables, where instances is the number of crime instances in Michigan, syg is an indicator variable for whether the law exists in the specific month, and time increases by one each month:

![Variables](/images/variables.jpg "Three Variables")

In the regression we include three terms, syg, time, and a term that is syg\*time. Since time is on the x-axis, syg would be the term that changes the intercept and the slope of the regression line.

![Equation](/images/equation.jpg "Equation for Regression Line")

The regression results are as follows:

![Regression](/images/regression.jpg "Regression Results")
