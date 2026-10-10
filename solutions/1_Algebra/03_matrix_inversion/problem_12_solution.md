# Problem 12: Finding Inverses Without Starting from Scratch

## Detailed Step-by-Step Solution
Given $A^{-1}=\begin{pmatrix}2&-1\\-3&2\end{pmatrix}$:

$$
(3A)^{-1}=\frac13A^{-1}
=\begin{pmatrix}\frac23&-\frac13\\-1&\frac23\end{pmatrix}.
$$

Using $(A^T)^{-1}=(A^{-1})^T$,

$$
(A^T)^{-1}=\begin{pmatrix}2&-3\\-1&2\end{pmatrix}.
$$

Using $(A^2)^{-1}=(A^{-1})^2$,

$$
(A^2)^{-1}
=\begin{pmatrix}2&-1\\-3&2\end{pmatrix}^2
=\begin{pmatrix}7&-4\\-12&7\end{pmatrix}.
$$

## Verification
Each identity follows from the inverse rules for a nonzero scalar multiple, transpose, and product.