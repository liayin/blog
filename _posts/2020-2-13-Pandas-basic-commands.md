---
layout: post
title: Pandas Basic Commands
date: 2020-02-13 17:05:00 --0000
permalink: /posts/pandas-basic-commands/
---
This post serves as a cheat sheet for the basic commands in Pandas.

Table of Contents
* TOC
{:toc}

[Click here for other basics](https://medium.com/@kasiarachuta/exploring-your-pandas-dataframe-ee09e9a63ea8)

## Dataframe Tricks
[Make new dataframe](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.html):
```python
df2 = pd.DataFrame(np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]]),
                   columns=['a', 'b', 'c'])
```

Make a list of dataframes from names in a list:
```python
i = 0
for df_name in list_dfs:
    globals()[df_name] = df.loc[df.id == 'id-0000' + str(i)]
    i += 1
```

Merge two dataframes by a certain column:
```Python
pd.merge(df1, df2, on='company')
```

Display a slice of the data:
```Python
all.head()
```

Display all unique values in dataframe ([link](https://www.kite.com/python/answers/how-to-find-the-unique-values-in-multiple-columns-of-a-pandas-dataframe-in-python)):
```python
column_values = df[["A", "B"]].values.ravel()
unique_values =  pd.unique(column_values)
```

Append dataframes:
```python
df = df.append(df2, ignore_index=True)
```

Save dataframe as LaTeX table ([Reference](https://blog.finxter.com/pandas-dataframe-to_latex-method/)):
```python
df.to_latex('finxters.tex', index=False, caption='User Details')
```

Include hyperlinks into dataframes ([Reference](https://datascientyst.com/create-clickable-link-pandas-dataframe-jupyterlab/)):
```python
HTML(df_legislations.to_html(render_links=True, escape=False))
```

Make a dataframe that is identical to an existing dataframe ([Reference](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.copy.html)):
```python
deep = s.copy()
```

## Row Tricks

Find rows that contain certain values:
```Python
df[df.values == 'banana']
```

Repeat rows multiple times:
```python
df_law = df_law.loc[np.repeat(df_law.index.values, 15)].reset_index(drop=True)
```

Pandas forward fill:
```python
df['x'] = df.groupby(['id'])['x'].ffill()
```

## Column Tricks
In order to see all the column names, we could do the trick below:
```Python
cols = y1988.columns.tolist()
cols
```

In Jupyter notebook, the following is displayed:

![All Columns](/images/cols.jpg "All Columns in Pandas")

Find column index:
```Python
df.columns.get_loc("pear")
```

Rename column from "Unnamed: 0" to "State" for the dataframe called "all":
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

[Rearrange columns](https://stackoverflow.com/questions/13148429/how-to-change-the-order-of-dataframe-columns):
```python
df = df[['mean', 4, 3, 2, 1]]
```

Remove column name, especially after crosstab:
```python
df_murder_type.columns.name = None
```

Rounding a column:
```python
df.round(1)
df.round({'dogs': 1, 'cats': 0})
```

### Adding columns
Insert column with incremental year
```python
ar_year = df_law.groupby('State.1').cumcount()+2000
df_law.insert(1, 'Year', ar_year)
```

Convert integer to datetime and add as column
```python
df_law['Date'] = pd.to_datetime((df_law['Year']), format='%Y')
```

Add column based on conditions
```python
df_law['Around Law Year'] = np.where(
    ((df_law['Law Passing Date'].dt.year - df_law['Year'])==1) | \
    ((df_law['Law Passing Date'].dt.year - df_law['Year'])==0) | \
    ((df_law['Law Passing Date'].dt.year - df_law['Year'])==-1), 1, 0)
```

```python
conditions = [
    df_law['Year'] < df_law['Date.1'].dt.year,
    df_law['Year'] == df_law['Date.1'].dt.year,
    df_law['Year'] > df_law['Date.1'].dt.year
]
values = [
    0,
    (df_law['Date Next Year'] - df_law['Date.1']).dt.days/ \
    (df_law['Date Next Year'] - df_law['Date']).dt.days,
    1
]
df_law['Law'] = np.select(conditions, values)
```

Reshape data from wide to long:
```
all = pd.wide_to_long(all, stubnames="", i="State", j="Year")
```

Resetting index:
```python
df = df.reset_index(drop=True)
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

[Strip white spaces](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.str.strip.html)
```python
df = df['State'].str.strip(' ')
```

### Change Column Data Type
Change to numeric:
```python
# convert column "a" of a DataFrame
df["a"] = pd.to_numeric(df["a"])
```

Change from categorical to numeric:
```python
list = ['charg5', 'charg4', 'charg3', 'charg2', 'charg1']
for charges in list:
    df_circum[charges] = df_circum[charges].cat.codes
```

Change to integer:
```python
df[list("ABCD")] = df[list("ABCD")].astype(int)
```

## Data Tricks
Frequency table for a column:
```python
df_circum['charg1'].value_counts()
```

Replace a number with NaN:
```python
df_circum['charg1'] = df_circum['charg1'].replace(-1, np.NaN)
```
Replace a value based on a criterion:
```python
df.loc[df['First Season'] > 1990, 'First Season'] = 1
```

## Some Groupby Tricks
### Add new column that increments on a number
```python
ar_year = df_law.groupby('State.1').cumcount()+2000
df_law.insert(1, 'Year', ar_year)
```

Groupby single column in pandas ([Reference](https://www.datasciencemadesimple.com/group-by-mean-in-pandas-dataframe-python-2/))
```python
df1.groupby(['State'])['Sales'].mean()
```

Group by and aggregate different columns based on different rules([Reference](https://stackoverflow.com/questions/14529838/apply-multiple-functions-to-multiple-groupby-columns))
```python
df.groupby('group').agg({'a':['sum', 'max'], 
                         'b':'mean', 
                         'c':'sum', 
                         'd': lambda x: x.max() - x.min()})
```

Group by and counting the number of rows([Ref](https://www.geeksforgeeks.org/pandas-groupby-count-occurrences-in-column/))
```python
occur = data.groupby(['Section']).size()
```

## Datetime
### Series
```python
df_law['Date.1'].dt.year
```
