---
tags:
  - pandas
  - library
  - python
  - data-manipulation
created: 2026-04-16
---

> Part of the [[00_Index/Data Science]] workflow.

pandas is a Python library that enables data to be handled as numeric tables.

It uses unique data structures that enable processing of various types of data.

> **In short:**
> You can handle data as if you were using Excel

|                                  Strengths                                   |       Weaknesses        |
| :--------------------------------------------------------------------------: | :---------------------: |
| Has methods for processing numerical data, time-series and character strings | Slow calculation speed  |
|          Strong in statistical processing such as data aggregation           | High Memory consumption |
|         Read and writes multiple file formats: csv, excel, json, etc         |  Steep learning curve   |
# Data Structures

Common data structures used in pandas are Series and Data Frames

## Series
Series are 1D arrays (also called vectors).

|     | Row name  |
| :-- | --------- |
| 1   | 123412312 |
| 2   | 2352123   |
| 3   | 3456234   |
| 4   | 213123    |
| 5   | 546342    |
These can be represented by a Numpy 1D array.

In pandas, a series is defined using `pandas.Series`

```python
from pandas import Series

series = Series([1,1,4,6,7,8])
print(series)

# Output
0 1
1 1
2 4
3 6
4 7
5 8

```

A `Series` object has both indices and elements. Indices can be defined using the `index` parameter.

```python
series = Series([1, 1, 2, 3, 5, 8],
                index=["a", "b", "c", "d", "e", "f"])

print(series)

# Output

a 1
b 1 
c 2 
d 3 
e 5 
f 8
```

Indexes and Values can also be retrieved separately:

```python
indexes = series.index
values = series.values
```
## Data Frames
Data Frames are 2D matrices (also called just matrices), separated in rows and columns.

|     | Column 1 | Column 2 | Column 3 |
| --- | -------- | -------- | -------- |
| 1   | 21342134 | Tokyo    | 1990     |
| 2   | 8723423  | Osaka    | 1989     |
| 3   | 23746212 | Kyoto    | 1951     |
| 4   | 21380947 | Tokyo    | 2001     |
These can be represented by a Numpy 2D array with row and column labels. Row labels are called **index** and Column labels are called **columns**. 

In pandas, a Data Frame is defined using `pandas.DataFrame`

```python
from pandas import DataFrame

data = {
'ID':['100', '101', '102', '103', '104'],
'City':['Tokyo', 'Osaka', 'Kyoto', 'Hokkaido', 'Tokyo'],
'Birth_year':[1990, 1989, 1992, 1997, 1982],
'Name':['Hiroshi', 'Akiko', 'Yuki', 'Satoru', 'Steve']
}

df = DataFrame(data)

print(df)

# Output
  ID  City     Birth_year Name 
0 100 Tokyo    1990       Hiroshi 
1 101 Osaka    1989       Akiko 
2 102 Kyoto    1992       Yuki 
3 103 Hokkaido 1997       Satoru 
4 104 Tokyo    1982       Steve

```

You can use the `.head()` method to print the 5 first rows.

See [[02_Data_Processing/DataFrame Basics]]

## How to read Data

To read data with pandas, you use one of the following pandas functions:
- `pd.read_csv()` → CSV
- `pd.read_table()` → delimited text (TSV, etc.)
- `pd.read_fwf()` → fixed-width text
- `pd.read_excel()` → Excel (.xls, .xlsx)
- `pd.read_json()` → JSON
- `pd.read_xml()` → XML
- `pd.read_html()` → HTML tables
- `pd.read_sql()` → SQL query/table
- `pd.read_sql_query()` → SQL query
- `pd.read_sql_table()` → SQL table
- `pd.read_parquet()` → Parquet
- `pd.read_feather()` → Feather
- `pd.read_orc()` → ORC
- `pd.read_pickle()` → Pickle
- `pd.read_hdf()` → HDF5
- `pd.read_sas()` → SAS
- `pd.read_spss()` → SPSS
- `pd.read_stata()` → Stata

```python
import pandas as pd

my_data = pd.read_csv('route/to/your/csv.csv')
```

Now, to visualize said data:

```python
my_data.head()
```

Let's take an example using [Hernan4444's Anime List Database](https://github.com/Hernan4444/MyAnimeList-Database):

```python
anime_data = pd.read_csv("MyAnimeList-Database-master/data/anime.csv")

anime_data.head()

# Output

# Output is too big, do it yourself
```

> Be aware that the `head()` method can take an optional integer parameter, which sets how many rows should be displayed. Eg: `anime_data.head(10)` displays the first 10 rows.

## Basic Data Evaluation
To get some basic information about our data, we can use the `.info()` method.

```python
anime_data.info()

# Output

<class 'pandas.core.frame.DataFrame'>
RangeIndex: 17562 entries, 0 to 17561

Data columns (total 35 columns):
 #   Column         Non-Null Count  Dtype
---  ------         --------------  -----
 0   MAL_ID         17562 non-null  int64
 1   Name           17562 non-null  object
 2   Score          17562 non-null  object
 3   Genres         17562 non-null  object
 4   English name   17562 non-null  object
 5   Japanese name  17562 non-null  object
 6   Type           17562 non-null  object
 7   Episodes       17562 non-null  object
 8   Aired          17562 non-null  object
 9   Premiered      17562 non-null  object
10   Producers      17562 non-null  object
11   Licensors      17562 non-null  object
12   Studios        17562 non-null  object
13   Source         17562 non-null  object
14   Duration       17562 non-null  object
15   Rating         17562 non-null  object
16   Ranked         17562 non-null  object
17   Popularity     17562 non-null  int64
18   Members        17562 non-null  int64
19   Favorites      17562 non-null  int64
...
33   Score-2        17562 non-null  object
34   Score-1        17562 non-null  object

dtypes: int64(9), object(26)
memory usage: 4.7+ MB
```

This allows us to see the data type of each column, how many rows there are, how many missing values, etc.

You can also use the `.describe()` method to calculate basic statistics about quantitative data.

```python
anime_data.describe()

# Output

# Once again, output is too big
```
