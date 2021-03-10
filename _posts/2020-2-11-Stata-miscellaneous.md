---
layout: post
title: Stata Miscellaneous Commands
date: 2020-02-11 17:05:00 --0000
---
In order to list variables, the command is ```ds```. In order to drop variables, the command is ```drop```. See the following example:

![StataVariables](/images/stata-variables.jpg "Stata Variables")

### Line Breaks
Normally the way to break a line is `///`, but when I would like to break in the middle of a string, I will use
```
#delimit ;
label var x "This is a long label
     with more text on second line" ;
#delimit cr
desc x
```