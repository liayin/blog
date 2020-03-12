---
layout: post
title: Counting in Stata
---

Counting the number of offenses for each ori in each month and recording the results:
```
bysort year month ori: egen crimes = count(offense)
```

