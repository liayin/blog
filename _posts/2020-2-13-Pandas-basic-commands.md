---
layout: post
title: Pandas Basic Commands
---

Read csv file:
```Python
all = pd.read_csv(
    "export-2020-02-13-T-13-58-18.csv",
    skiprows=8, # skip the first 8 rows
    nrows=16, # read the next 16 rows
)
```

Read Stata file:
```Python
rate = pd.read_stata('rate.dta')
```

[Click here for other basics](https://medium.com/@kasiarachuta/exploring-your-pandas-dataframe-ee09e9a63ea8)

In order to see all the column names, we could do the trick below:
```Python
cols = y1988.columns.tolist()
cols
```

In Jupyter notebook, the following is displayed:

![All Columns](/images/cols.jpg "All Columns in Pandas")

Merge two dataframes by a certain column:
```Python
pd.merge(df1, df2, on='company')
```

Display a slice of the data
```Python
all.head()
```

Find rows that contain certain values:
```Python
df[df.values == 'banana']
```

Find column index:
```Python
df.columns.get_loc("pear")
```

Rename column from "Unnamed: 0" to "State" for the data set called "all":
```
all = all.rename(columns={"Unnamed: 0": "State"})
```

Concatenate columns:
```
shr['nameyear'] = shr['name'] + shr['year'].map(str)
```

Remove columns:
```
data = data.drop(["Y2001", "Y2002", "Y2003"], axis=1)
```

Remove all columns between column index 1 to 3:
```
df.drop(df.iloc[:, 1:3], inplace = True, axis = 1)
```

Reshape data from wide to long:
```
all = pd.wide_to_long(all, stubnames="", i="State", j="Year")
```

Change multilevel index to single level:
```
all = all.reset_index()
```

Check data type:
```
all.dtypes
```

Check the shape of data, namely how many rows and how many columns they have:
```
all.shape
```

Change data type. Note that NaN can only be changed into float but not into integer.
```
all['ER Visits'] = all['ER Visits'].astype(float)
```

Sort values:
```
avg.sort_values("perc_gun", inplace = True, ascending=False)
```

Replace values:
```
all.replace(0, 5)
```

Drop values:
```
df = df[df.line_race != 0]
```
