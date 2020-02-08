---
layout: post
title: Stata Labels
---
It is possible to assign the same label for multiple variables. Check out the following example:

Initially these variables don't have labels.

![Charges](/images/charges.jpg "Charges")

We can make a label:
```
label define charge 0 "capital murder" 1 "first degree murder" ///
	2 "second degree murder" 3 "third degree murder" ///
	4 "voluntary manslaughter/non-negligent - manslaughter 1st" ///
	5 "accessory to murder" 6 "accessory after the fact" ///
	7 "conspiracy to murder (includes solicitation to murder)" ///
	8 "attempted murder" ///
	9 "use of firearm (includes felony f/a, possession of f/a)" ///
	10 "aggravated battery (includes assault with a weapon)" ///
	11 "sexual assault" 12 "robbery" 13 "burglary" 14 "arson" ///
	15 "kidnapping" 16 "prostitution" ///
	17 "other felony (includes escape and evidence tampering)" ///
	18 "misdemeanor" 19 "career criminal enhancement" ///
	20 "felony drug" ///
	21 "use of a dangerous weapon (other than a firearm)" ///
	22 "involuntary manslaughter/negligent - manslaughter 2nd" ///
	23 "reckless driving (hit and run)" ///
	24 "driving under the influence" ///
	25 "vehicular manslaughter" 26 "child abuse" ///
	27 "child abuse with death (Albuquerque only)" ///
	28 "larceny/grand theft (includes auto theft)" ///
	29 "old age enhancement" 30 "careless use of a firearm" ///
	31 "reckless endangerment of another person" ///
	32 "attempted manslaughter" 33 "misd. drug" 34 "unknown" ///
	35 "armed violence (Chicago)"
```
And then assign it to the variables:
```
label values charg* charge
```
So that all the variables that start with charg will have this variable label.

![Charges2](/images/charges2.jpg "Charges 2")
