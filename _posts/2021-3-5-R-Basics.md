---
layout: post
title: R Basics
date: 2021-03-05 12:45:00 --0000
---

## General Maintenance
```r
install.packages("plotly")
```
```r
update.packages(ask=False)
```

`pacman` installs and loads packages, which is much easier than the standard R routine
```r
pacman::p_load(pacman, dplyr, GGally, ggplot2, ggthemes, ggvis, 
    httr, lubridate, plotly, rio, rmarkdown, shiny, stringr, tidyr)
```

To unload packages, type
```r
p_unload(all)
```

To check current directory
```r
getwd()
```

To set working directory
```r
setwd("/path/to/my/directory")
```

## Simple Plotting
### Boxplot
```r
plot(iris$Species, iris$Petal.Width)
```

The resulting figure is


## Data Frame Manipulation
### Read in data
Recode empty cells as missing value during data import
```r
df_midline <- import("midline_04032021.csv", na.strings="")
```

### Rows
Remove rows with NaN values
```r
df_midline <- df_midline[!is.na(df_midline$prop_camp), ]
```

Check number of rows in data frame
```r
nrow(dataset)
```

Select rows with certain conditions
```r
df[df$unique_id=="157-00045552",]
```

### Columns

Change column type from character to numeric
```r
df_midline <- transform(df_midline, 
                        employment_woman = as.numeric(employment_woman))
```

Rename columns
```r
my_data %>% 
  rename(
    sepal_length = Sepal.Length,
    sepal_width = Sepal.Width
    )
```

Reorder columns
```r
df[,c(1,2,3,4)]
```

### Data frames
Combine two cross sectional data sets into a panel data set
```r
library(dplyr)
data1 %>%
  bind_rows(data2) %>%
  arrange(ID, Yr)
```
Copy data from one cross sectional data variable to another one (time-fixed variables)
```r
df <- df %>%
  group_by(unique_id) %>%
  mutate(cookstove_assigned2 
         = ifelse(n()==2, cookstove_assigned2[!is.na(cookstove_assigned2)],
                  cookstove_assigned2)) %>%
  ungroup
```

### Model-building
```r
x <- as.matrix(data[-12])
y <- data[, 12]
```

Logit panel regression
```r
result_1 <- clogit(resp_stovetype_n ~ indep_var + strata(unique_id), data = df)
```