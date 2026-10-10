# Problem 2: Formula for a 2x2 Matrix

## Detailed Step-by-Step Solution
For $A=\begin{pmatrix}3&2\\5&4\end{pmatrix}$, the determinant is $12-10=2$. Hence

$$
A^{-1}=\frac12\begin{pmatrix}4&-2\\-5&3\end{pmatrix}
=\begin{pmatrix}2&-1\\-\frac52&\frac32\end{pmatrix}.
$$

Check by multiplying:

$$
AA^{-1}
=\frac12\begin{pmatrix}3&2\\5&4\end{pmatrix}
\begin{pmatrix}4&-2\\-5&3\end{pmatrix}
=\frac12\begin{pmatrix}2&0\\0&2\end{pmatrix}=I.
$$

## Verification
The product is the identity, as required for an inverse.