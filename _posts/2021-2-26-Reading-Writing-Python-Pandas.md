---
layout: post
title: How to Import to and Export from Python Pandas
date: 2021-02-26 16:06:00 --0000
permalink: /posts/pandas-imports-exports/
---

The most common use of Python Pandas is to process data. However, data could be recorded in different formats: tab-delimited text data, .csv files, .json files, .dta files, etc. Below I would like to list some sources and offer some examples of how to import certain types of data into Python Pandas and how to export them from it:

## Import

### Fixed Width

Find link [here](https://stackoverflow.com/questions/27416031/pandas-read-fwf-not-loading-entire-content-of-file). The example they have is:
```python
file_name = r"/tmp/file.txt"
fwidths = [11, 11, 11, 11, 11, 11]
df = pd.read_fwf(file_name, widths = fwidths,
                 names = ['col0', 'col1', 'col2', 'col3', 'col4', 'col5'])
```

### Excel File

Find link [here](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.read_excel.html). I have combined two of their examples:
```python
pd.read_excel('tmp.xlsx', index_col = 0, sheet_name = 'Sheet3')
```

### Stata File

Find link [here](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.read_stata.html).

The pandas method `read_stata` is not able to import value labels. In cases when we would like to import value labels, we can make use of the library `pyreadstat` ([Github repo](https://github.com/Roche/pyreadstat)). 
```python
df_circum, meta = pyreadstat.read_dta('../Data/1988/y1988.dta', apply_value_formats=True)
```

### Tab Delimited File

Find link [here](https://stackoverflow.com/questions/21546739/load-data-from-txt-with-pandas). Example given on the page:

```python
df = pd.read_csv('file_location\filename.txt', delimiter = '\t')
```

### Clipboard

```python
df = pd.read_clipboard()
```

## Export
### Stata
Official documentation [here](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.to_stata.html). One example is:

```python
df.to_stata('state_expenditures.dta', write_index=False)
```