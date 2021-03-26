---
layout: post
title: R Basics
date: 2021-03-05 12:45:00 --0000
permalink: /posts/r-basics/
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
## Data Types
### Convert character variable to numeric
```r
dataset$prop_camp <- as.numeric(dataset$prop_camp)
```

### Converting Character Variable to Factor
```r
dataset$cookstove_assigned2 <- factor(dataset$cookstove_assigned2, 
                                      levels = c("Already users", 
                                                 "Intervention group",
                                                 "Waitlisted controls"),
                                      ordered=TRUE)
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

Change column type from integer to categorical
```r
mydata$COR <- as.factor(mydata$COR)
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

Drop columns
```r
df = subset(mydata, select = -c(x,z) )
```

### Data frames
[Examine a Data Frame in R with 7 Basic Functions](https://rveryday.wordpress.com/2016/11/29/examine-a-data-frame-in-r-with-7-basic-functions/):
1. `dim()`: shows the dimensions of the data frame by row and column
2. `str()`: shows the structure of the data frame
3. `summary()`: provides summary statistics on the columns of the data frame
4. `colnames()`: shows the name of each column in the data frame
5. `head()`: shows the first 6 rows of the data frame
6. `tail()`: shows the last 6 rows of the data frame
7. `View()`: shows a spreadsheet-like display of the entire data frame

Check for missing values in a dataframe:
```r
sapply(airquality, function(x) sum(is.na(x)))
```

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

#### Logit panel regression

See [here](https://data.princeton.edu/wws509/r/fixedRandom3) for a reference.
```r
result_1 <- clogit(resp_stovetype_n ~ indep_var + strata(unique_id), data = df)
```
If you think some of the variations are due to overall time trends or other time series patterns ([reference here](https://www.statalist.org/forums/forum/general-stata-discussion/general/228950-time-fixed-effects)), then you should add time dummies in the data. Just be aware that the log-likelihood may not converge if time dummies are added.
```r
result_1 <- clogit(resp_stovetype_n ~ indep_var + strata(unique_id) 
    + strata(time_period), data = df)
```

[This version](https://stats.idre.ucla.edu/r/dae/mixed-effects-logistic-regression/) and [this version](https://uc-r.github.io/logistic_regression) can handle factor variables.