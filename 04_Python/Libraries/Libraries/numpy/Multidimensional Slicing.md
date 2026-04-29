For **numpy arrays** with more than 1D, we need **Multidimensional Slicing**.

For each dimension, you add a "layer" to the slicing:

- for a 2D array: arr\[x:y:z, a:b:c]
- for a 3D array: arr\[x:y:z, a:b:c, e:f:g]
- for a nD array: arr\[x:y:z, a:b:c, ...,]

This works up to ~32 arrays, where memory starts being a limitation.

So, for a 2D array, we have `start:end:step, start:end:step`.

```python
mtrx 
```