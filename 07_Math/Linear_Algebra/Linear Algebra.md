# Introduction

The equation $A\mathbf{x} = \mathbf{b}$ uses the language of linear combinations. 

The vector $A\mathbf{x} = \mathbf{b}$ is a *combination of the  columns of A*. The equation is asking for a *combination that produces b*. The solution vector $\mathbf{x}$ comes at three levels and all are important:
- **Direct solution** to find $\mathbf{x}$ by forward elimination and back substitution.
- **Matrix solution** using the inverse matrix: $x = A^{-1}\mathbf{b}$ (If $A$ has an inverse).
- **Particular solution** (to $A\mathbf{y} = \mathbf{b}$) plus **nullspace solution** (to $A\mathbf{x} = 0$).

Direct elimination is the most frequently used algorithm in scientific computing. the matrix $A$ becomes triangular, then solutions come quickly.

