---
tags:
  - pandas
  - dataframe
  - data-manipulation
  - transposing
created: 2026-04-16
---

**How to handle DataFrame objects**

> Part of the [[04_Python/pandas]] ecosystem. See [[04_Python/pandas]] for an overview.

### Transposition

Like in a matrix, rows swap with columns. Done with the `.T` attribute.

```python
anime_data.head().T

# Output

| | 0 | 1 | 2 |  
|----------------|---|---|---|  
| MAL_ID | 1 | 5 | 6 |  
| Name | Cowboy Bebop | Cowboy Bebop: Tengoku no Tobira | Trigun |  
| Score | 8.78 | 8.39 | 8.24 |  
| Genres | Action, Adventure, Comedy, Drama, Sci-Fi, Space | Action |  
| English name | Cowboy Bebop | Cowboy Bebop:The Movie | Trigun |  
| ... | ... | ... | ... |  
| Score-5 | 8904.0 | 1877.0 | 5838.0 |  
| Score-4 | 3184.0 | 577.0 | 1965.0 |  
| Score-3 | 1357.0 | 221.0 | 664.0 |  
| Score-2 | 741.0 | 109.0 | 316.0 |  
| Score-1 | 1580.0 | 379.0 | 533.0 |
```

### Data Selection

#### Columns

##### Single Columns

To select a single column, we can treat the DataFrame as a Dictionary.

```python
anime_data["Score"].head()

# Output

|   |Score|
|---|---|
|0|8.78|
|1|8.39|
|2|8.24|
|3|7.27|
|4|6.98|
```

It can also be treated a Class.

```python
anime_data.Score.head()

# Output is the same
```

##### Multiple Columns

To select multiple columns, pass a list of column names.

```python
anime_data[["Name", "Score", "Genres"]].head()

# Output

|   | Name         | Score | Genres |
|---|--------------|-------|--------|
| 0 | Cowboy Bebop | 8.78  | Action, Adventure, Comedy, Drama, Sci-Fi, Space |
| 1 | Cowboy Bebop: Tengoku no Tobira | 8.39 | Action |
| 2 | Trigun       | 8.24  | Action, Sci-Fi, Adventure, Comedy, Drama |
| 3 | Witch Hunter Robin | 7.27 | Action, Mystery, Police, Supernatural, Drama, Magic |
| 4 | Bouken Ou Beet | 6.98 | Adventure, Fantasy, Shounen, Supernatural |
```

You can't  select multiple columns using the class-like method.

#### Rows

To easily select rows, we use [[04_Python/Concepts/List Comprehensions]], a Python utility that allows us to efficiently select  specific rows from an array.

```python
cols_to_use = [
'MAL_ID', 'Name', 'Score', 'Genres', 'Type', 'Aired', 'Studios', 'Source'
]

anime_data_extracted = anime_data[cols_to_use]

anime_data_extracted[0:3]
```

It also works with letters as indexes.

```python
df = pd.DataFrame({
'ID': [100, 101, 102, 103],
'City': ['Tokyo', 'Osaka', 'Kyoto', 'Nagoya'],
'Birth_year': [1990, 1989, 1992, 1995],
'Name': ['Hiroshi', 'Akiko', 'Yuki', 'Satoru']
index=['a', 'b', 'c', 'd']
})

df['a':'c']

# Output

ID City Birth_year Name
a 100 Tokyo 1990 Hiroshi
b 101 Osaka 1989 Akiko
c 102 Kyoto 1992 Yuki
```

#### df.loc

`df.loc[]` allows you to select a specific column or row by specifying the index or column name.