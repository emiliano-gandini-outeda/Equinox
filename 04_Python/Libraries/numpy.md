---
tags:
  - numpy
  - python
  - library
  - numerical-computation
created: 2026-04-20
---

# Introduction

Almost all data can (and will eventually) be represented as vectors and matrices.

[[Vectors]] are represented in numpy using 1D arrays. 
[[Matrices]] are represented in numpy using 2D arrays.

In Libraries, the [[04_Python/Concepts/Import Conventions]] is to import `numpy` as `np`.

```python
import numpy as np
```

**Numpy** is a specialized python library made for efficient numerical computation.

## Arrays

**Numpy Arrays** allow to represent different mathematical structures, like **Vectors** and **Matrices**.

```python
# Numpy Array
arr = np.array([1,2,3,4,5,6]) 

# Numpy Matrix
arr = np.array([[1,2,3],[1,2,3]])

# You can also pass variables
arr = [1,2,3,4]
nparr = np.array(arr)
```

To get the length of an array, we can use the `shape` method.

```python
array_size = nparr.shape
> (4,)
```

You can make use of basic arithmetic symbols to operate in numpy arrays.

```python
sumarr = arr1 + arr2
diffarr = arr1 - arr2
prodarr = arr1 * arr2
divarr = arr1 / arr2
```

You also have more advanced functions.

```python
np.max(arr) # max value of an array
np.min(arr) # min value of an array
np.sum(arr) # sum of array values
np.mean(arr) # average value of the array
np.std(arr) # Array's [[06_Statistical_Analysis/Standard Deviation | standard deviation]] 
```

In **numpy**, you can represent **infinity** using `np.inf` as a value.

Read [[04_Python/Libraries/numpy/Numpy Arrays | more about numpy arrays]].

## Conditional Operations

In numpy, conditional operations between arrays are evaluated element by element, not as the full array:

```python
a = np.array([1, 2, 3, 4, 5])
b = np.array([2, 2, 3, 6, 1])

print("a==a:", a==a)
> a==a: [ True  True  True  True  True]
print("a==b:", a==b)
> a==b: [False  True  True False False]
print("a>b:", a>b)
> a>b:  [False False False False  True]
```

Read [[04_Python/Libraries/numpy/Numpy Conditional Operations | more about numpy conditional operations]].

## Broadcasting

In Numpy, when performing a universal binary operation on two arrays with different lengths or dimensions, one of the arrays is automatically broadcast to match the other in terms of dimensions and length. This is called **broadcasting**.

```python
arr = np.array([1,2,3,4])
res = arr * 2
```

Due to broadcasting, that translates to:

```python
res = [1,2,3,4] * [2,2,2,2]
```

Details on how this works can be seen in [[Matrix Broadcasting]].

**Broadcasting doesn't work for all matrices**. 

Broadcasting only works when a numpy array is of length 1. If not, a `ValueError` is raised.

## Concatenation

Unlike in Python, using the `+` operator in numpy doesn't concatenate two arrays. To concatenate arrays in numpy we use the `concatenate` method.

```python
np.concatenate(arr1, arr2)
```

## Indexing

Indexes are the easiest way to retrieve data from an array.

```python
arr = np.array([1,2,3,4,5])

print(arr[0])
> 1
```

**Indexes always start at 0 unless specified otherwise.**

#### Negative Indexes

You can use **negative indexes** to retrieve data from the end of the array.

```python
print(arr[-1])
> 5
```


#### Multiple Retrieval

In **numpy**, you can specify multiple indexes to retrieve multiple values at the same time.

```python
print(arr[3, 1, -1])
> [4, 2, 5]
```

They return as an array.

#### Slicing

**Numpy slicing** works the same as [[04_Python/Concepts/Slicing | Python slicing]]. 

