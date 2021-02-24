---
layout: post
title: A header file that controls the path of all the files in Stata
date: 2020-03-06 17:06:00 --0000
---


```
global base `"C:/mydata/"'
```


```
import excel using `"${base}/myrawdata.xlsx"', clear
```
