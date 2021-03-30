---
layout: post
title: R Graphics
date: 2021-03-26 14:06:00 --0000
permalink: /posts/r-graphics/
---

Save graphs as PDF:
```r
ggsave("mp.pdf", gridExtra::marrangeGrob(grobs = pl, nrow=3, ncol=2))
```