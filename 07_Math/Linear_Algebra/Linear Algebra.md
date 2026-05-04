# Introduction

The equation $A\mathbf{x} = \mathbf{b}$ uses the language of linear combinations. 

The vector $A\mathbf{x} = \mathbf{b}$ is a *combination of the  columns of A*. The equation is asking for a *combination that produces b*. The solution vector $\mathbf{x}$ comes at three levels and all are important:
- **Direct solution** to find $\mathbf{x}$ by forward elimination and back substitution.
- **Matrix solution** using the inverse matrix: $x = A^{-1}\mathbf{b}$ (If $A$ has an inverse).
- **Particular solution** (to $A\mathbf{y} = \mathbf{b}$) plus **nullspace solution** (to $A\mathbf{x} = 0$).

Direct elimination is the most frequently used algorithm in scientific computing. the matrix $A$ becomes triangular, then solutions come quickly.

## Introduction to Vectors

Linear algebra is based around vectors. For two vectors $v$ and $w$, if we add them, 
we get $v + w$. If we multiply them by numbers $c$ and $d$, we get $cv$ and $dw$ . 

Combining this two operations (adding $cv$ to $dw$) gives the **linear combination** $cv + dw$. 

**Example of a Linear Combination**: $c\begin{bmatrix} 1\\1\end{bmatrix} + d \begin{bmatrix}2 \\  3 \end{bmatrix} = \begin{bmatrix}c + 2d \\  c+ 3d \end{bmatrix}$

Then:

$v + w = \begin{bmatrix}1 \\  1 \end{bmatrix} + \begin{bmatrix}2 \\  3 \end{bmatrix} = \begin{bmatrix} 3 \\  4\end{bmatrix}$ is the combination with $c = d = 1$.

### Vectors and Linear Combinations

1. $3v + 5v$ is a typical **linear combination** $cv + dw$ of the vectors $v$ and $w$.
2. For $v = \begin{bmatrix} 1 \\  1\end{bmatrix}$ and $w = \begin{bmatrix} 2 \\ 3\end{bmatrix}$ that combination is $3 \begin{bmatrix} 1 \\  1 \\  \end{bmatrix} + 5 \begin{bmatrix} 2 \\  3\end{bmatrix} = \begin{bmatrix}3 + 10 \\  3 + 15 \end{bmatrix} = \begin{bmatrix} 13  \\  18\end{bmatrix}$
3. The vector $\begin{bmatrix} 2 \\  3  \end{bmatrix} = \begin{bmatrix} 2 \\   0\end{bmatrix} + \begin{bmatrix}0 \\  3\end{bmatrix}$ goes across to $x=2$ and up to $y =  3$ in the $xy$ plane.
4. The combinations $c \begin{bmatrix}1 \\  1\end{bmatrix} + d \begin{bmatrix}2 \\  3\end{bmatrix}$ fill the whole $xy$ plane. they produce every $\begin{bmatrix}x \\  y\end{bmatrix}$.
5. The combinations $c \begin{bmatrix}1 \\  1 \\  1\end{bmatrix} + d \begin{bmatrix}2 \\  3 \\  4\end{bmatrix}$ fill a **plane** in $xyz$ space. Same plane for $\begin{bmatrix}1 \\  1 \\  1\end{bmatrix} · \begin{bmatrix}3 \\  4 \\  5\end{bmatrix}$
6. But $\begin{matrix}c + 2d = 1 \\  c+3d = 0 \\  c+4d=0\end{matrix}$ has no solution because its right side $\begin{bmatrix}1 \\  0 \\  0\end{bmatrix}$ is not on that plane.

**Two separate numbers** $v_{1}$ and $v_{2}$ produce a **two-dimensional vector** $v$.

#### Vector Addition
$v = \begin{bmatrix}v_{1} \\  v_{2}\end{bmatrix}$ and $w=\begin{bmatrix}w_{1} \\  w_{2}\end{bmatrix}$ add to $v + w = \begin{bmatrix}v_{1} + w_{1} \\  v_{2}+w_{2}\end{bmatrix}$
