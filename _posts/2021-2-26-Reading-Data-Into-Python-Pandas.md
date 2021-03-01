---
layout: post
title: Reading Data Into Python Pandas
date: 2021-02-26 16:06:00 --0000
---

The most common use of Python Pandas is to process data. However, data could have many sources: tab-delimited text data, .csv files, .json files, .dta files, etc. Below I would like to list some sources for how to import certain types of data into Python Pandas for reference:

[Fixed width](https://stackoverflow.com/questions/27416031/pandas-read-fwf-not-loading-entire-content-of-file)

The example they have is:
```python
file_name = r"/tmp/file.txt"
fwidths = [11, 11, 11, 11, 11, 11]
df = pd.read_fwf(file_name, widths = fwidths,
                 names = ['col0', 'col1', 'col2', 'col3', 'col4', 'col5'])
```

[Excel file](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.read_excel.html)

I have combined two of their examples:
```python
pd.read_excel('tmp.xlsx', index_col = 0, sheet_name = 'Sheet3')
```