---
layout: post
title: A header file that controls the path of all the files in Stata
---


```
global base `"C:/mydata/"'
```


```
import excel using `"${base}/myrawdata.xlsx"', clear
```
