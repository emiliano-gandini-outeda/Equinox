---
tags:
  - pandas
  - dataframe
  - data-manipulation
  - transposing
created: 2026-04-16
---

**How to handle DataFrame objects**

> Part of the [[pandas]] ecosystem. See [[pandas]] for an overview.

### Transposition

Like in a matrix, rows swap with columns. Done with the `.T` method.

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

