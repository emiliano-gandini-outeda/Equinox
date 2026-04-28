---
tags:
  - numpy
  - arrays
created: 2026-04-28
---

# Numpy Arrays

Numpy provides efficient array operations.

Basic array creation:
```python
arr = np.array([1, 2, 3, 4, 5, 6])
matrix = np.array([[1, 2, 3], [4, 5, 6]])

arr.shape    # (6,)
matrix.shape  # (2, 3)
```

# Attributes

## T
View of the transposed array.
```python
arr.T          # transposed view
```

## data
Python buffer object pointing to start of array's data.
```python
arr.data      # memory buffer
```

## dtype
Data-type of array elements.
```python
arr.dtype     # float64, int32, etc.
```

## flags
Information about memory layout.
```python
arr.flags    # C_CONTIGUOUS, etc.
```

## flat
1-D iterator over the array.
```python
arr.flat     # iterate over all elements
for x in arr.flat:
    print(x)
```

## imag
The imaginary part of the array.
```python
arr.imag     # imaginary components
```

## real
The real part of the array.
```python
arr.real     # real components
```

## size
Number of elements in the array.
```python
arr.size     # total elements
```

## itemsize
Length of one element in bytes.
```python
arr.itemsize  # bytes per element (e.g., 8 for float64)
```

## nbytes
Total bytes consumed by elements.
```python
arr.nbytes   # total memory bytes
```

## ndim
Number of array dimensions.
```python
arr.ndim     # 1, 2, 3, etc.
```

## shape
Tuple of array dimensions.
```python
arr.shape    # (rows, cols, ...)
```

## strides
Tuple of bytes to step in each dimension.
```python
arr.strides  # bytes per dimension
```

## ctypes
Object to simplify ctypes interaction.
```python
arr.ctypes   # ctypes object
```

## base
Base object if memory is from another object.
```python
arr.base    # underlying array (None if own data)
```

Statistics:
```python
np.max(arr)
np.min(arr)
np.sum(arr)
np.mean(arr)
np.std(arr)  # standard deviation
```

Logarithms:
```python
np.log(x)      # natural log
np.exp(x)       # exponential
np.log1p(x)     # log(1+x), for small x
np.expm1(x)     # exp(x)-1, for small x
```

# ndarray Methods

## Reduction Methods

### all(axis, out, keepdims, where)
Returns True if all elements evaluate to True.

```python
arr.all()                    # True if all elements are truthy
arr.all(axis=0)             # along axis
arr.all(keepdims=True)       # keep dimensions
```

### any(axis, out, keepdims, where)
Returns True if any element evaluates to True.

```python
arr.any()                   # True if any element is truthy
arr.any(axis=1)            # along axis
```

### max(axis, out, keepdims, initial, where)
Return the maximum along a given axis.

```python
arr.max()                  # maximum value
arr.max(axis=0)             # maximum along axis
arr.max(initial=0)          # starting value
```

### min(axis, out, keepdims, initial, where)
Return the minimum along a given axis.

```python
arr.min()                  # minimum value
arr.min(axis=0)             # minimum along axis
```

### mean(axis, dtype, out, keepdims, where)
Returns the average of the array elements.

```python
arr.mean()                 # average of all elements
arr.mean(axis=0)            # average along axis
```

### sum(axis, dtype, out, keepdims, initial, where)
Return the sum of array elements.

```python
arr.sum()                  # sum of all elements
arr.sum(axis=0)             # sum along axis
arr.sum(initial=0)          # starting value
```

### prod(axis, dtype, out, keepdims, initial, where)
Return the product of array elements.

```python
arr.prod()                 # product of all elements
arr.prod(axis=0)           # product along axis
```

### std(axis, dtype, out, ddof, keepdims, where)
Returns the standard deviation.

```python
arr.std()                  # population std
arr.std(ddof=1)           # sample std (ddof=delta degrees of freedom)
```

### var(axis, dtype, out, ddof, keepdims, where)
Returns the variance.

```python
arr.var()                  # population variance
arr.var(ddof=1)           # sample variance
```

## Index Methods

### argmax(axis, out, keepdims)
Return indices of maximum values.

```python
arr.argmax()               # index of max value
arr.argmax(axis=0)        # indices along axis
```

### argmin(axis, out, keepdims)
Return indices of minimum values.

```python
arr.argmin()              # index of min value
arr.argmin(axis=0)         # indices along axis
```

### argpartition(kth, axis, kind, order)
Returns indices that would partition the array.

```python
arr.argpartition(3)        # indices for elements in partition 3
```

### argsort(axis, kind, order, stable)
Returns indices that would sort the array.

```python
arr.argsort()              # indices that sort the array
arr.argsort(axis=0)        # along axis
```

### nonzero()
Return indices of non-zero elements.

```python
arr.nonzero()              # indices of non-zero elements
```

### where(condition, x, y)
Return elements chosen from x or y depending on condition.

```python
np.where(arr > 0, arr, 0)  # arr where positive, else 0
```

## Sorting Methods

### sort(axis, kind, order, stable)
Sort array in-place.

```python
arr.sort()                 # sort in-place
arr.sort(axis=0)          # sort along axis
```

### partition(kth, axis, kind, order)
Partially sort array in-place.

```python
arr.partition(3)           # partition so k-th element is in sorted position
```

## Shape Methods

### reshape(newshape, order)
Returns array with new shape.

```python
arr.reshape((2, 3))         # reshape to 2x3
arr.reshape(-1)                # flatten to compatible shape
```

### resize(new_shape)
Change shape and size in-place.

```python
arr.resize((2, 3))           # change shape in-place
```

### flatten(order)
Return copy collapsed into one dimension.

```python
arr.flatten()              # 1D copy
arr.flatten(order='F')      # Fortran order
```

### ravel(order)
Return flattened view or copy.

```python
arr.ravel()                # flattened (view if possible)
```

### squeeze(axis)
Remove axes of length one.

```python
arr.squeeze()              # remove all length-1 axes
arr.squeeze(axis=0)        # remove specific axis
```

### transpose(*axes)
Return view with axes transposed.

```python
arr.transpose()            # transpose
arr.transpose(1, 0, 2)   # reorder axes
```

### swapaxes(axis1, axis2)
Return view with axes interchanged.

```python
arr.swapaxes(0, 1)        # swap first two axes
```

### flatten(order)
Return copy collapsed into 1D.

See `reshape`.

## Copy Methods

### copy(order)
Return a copy of the array.

```python
arr.copy()                 # copy
arr.copy(order='F')        # Fortran order
```

### astype(dtype, order, casting, subok, copy)
Copy cast to specified type.

```python
arr.astype(float)           # cast to float
arr.astype(np.float32)      # cast to float32
```

### view(dtype, type)
New view with same data.

```python
arr.view()                # same dtype view
arr.view(np.float64)      # as float64 view
```

## Element-wise Methods

### clip(min, max, out)
Limit values to range.

```python
arr.clip(0, 10)          # values between 0 and 10
arr.clip(min=0)           # minimum only
```

### round(decimals, out)
Round each element.

```python
arr.round()               # round to integer
arr.round(2)             # round to 2 decimals
```

### conj()
Complex-conjugate all elements.

```python
arr.conj()               # in-place conjugate
```

### conjugate()
Return complex conjugate.

```python
arr.conjugate()           # new array with conjugates
```

### byteswap(inplace)
Swap bytes of elements.

```python
arr.byteswap()            # swap bytes
arr.byteswap(True)       # in-place
```

### repeat(repeats, axis)
Repeat elements.

```python
arr.repeat(3)           # repeat each element 3 times
arr.repeat(2, axis=0)     # repeat along axis
```

### choose(choices, out, mode)
Construct new array from choices.

```python
arr.choose([choice0, choice1, choice2])
```

### compress(condition, axis, out)
Return selected slices along axis.

```python
arr.compress(arr > 0)    # only positive elements
```

## Aggregation Methods

### cumprod(axis, dtype, out)
Cumulative product.

```python
arr.cumprod()              # cumulative product
arr.cumprod(axis=0)        # along axis
```

### cumsum(axis, dtype, out)
Cumulative sum.

```python
arr.cumsum()              # cumulative sum
arr.cumsum(axis=0)        # along axis
```

### trace(offset, axis1, axis2, dtype, out)
Sum along diagonals.

```python
arr.trace()               # main diagonal sum
```

### diagonal(offset, axis1, axis2)
Return specified diagonals.

```python
arr.diagonal()            # main diagonal
arr.diagonal(offset=1)   # offset diagonal
```

## Access Methods

### item(*args)
Copy element to Python scalar.

```python
arr.item(0)              # element at index 0
arr.item(1, 2)           # element at (1, 2)
```

### take(indices, axis, out, mode)
Return elements at indices.

```python
arr.take([0, 2, 4])      # elements at these indices
arr.take([0, 1], axis=1)   # along axis
```

### put(indices, values, mode)
Set array elements at indices.

```python
arr.put([0, 1], [10, 20])  # set values at indices
```

## File I/O Methods

### tobytes(order)
Construct bytes containing data.

```python
arr.tobytes()            # raw bytes
arr.tobytes('C')         # C order
```

### tofile(fid, sep, format)
Write to file as text/binary.

```python
arr.tofile('data.bin')    # binary
arr.tofile('data.txt', sep=',')  # text
```

### dump(file)
Pickle array to file.

```python
arr.dump('array.pkl')     # pickle to file
```

### dumps()
Return pickle as string.

```python
arr.dumps()              # pickle string
```

### tolist()
Return as nested Python list.

```python
arr.tolist()             # Python list
```

### to_device(device, stream)
For Array API compatibility.

```python
arr.to_device(device)    # Array API
```

## Field Methods

### getfield(dtype, offset)
Return field as specified type.

```python
arr.getfield(np.float64)   # as float64 field
```

### setfield(val, dtype, offset)
Set field value.

```python
arr.setfield(5.0, np.float64, offset=0)
```

### setflags(write, align, uic)
Set array flags.

```python
arr.setflags(write=False)  # make read-only
```

## Search Methods

### searchsorted(v, side, sorter)
Find insertion indices.

```python
arr.searchsorted(value)    # where to insert to maintain order
arr.searchsorted([v1, v2])  # multiple values
```

### fill(value)
Fill array with scalar.

```python
arr.fill(0)              # fill with 0
```