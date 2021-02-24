---
layout: post
title: Bar Chart Races in Matplotlib
date: 2020-02-14 17:04:00 --0000
---

https://towardsdatascience.com/bar-chart-race-in-python-with-matplotlib-8e687a5c8a41

Several tricks here:
1. We don't need to change the dataframe names in the code. We could just create dataframes with the names df and dff. 
2. We don't need to change the column names of the original dataframes, we could change the column names of df and dff to match with what is in the post.
3. The best way to work with `animator.save()` is to save it as .mp4 and then use `ffmpeg -i C:\my_path\animation.mp4 C:\my_path\animation.gif` in cmd to convert the mp4 file into gif. Or we could just embed the mp4 file.
