# Problem 4: Gauss-Jordan

## Detailed Step-by-Step Solution
Begin with the augmented matrix:

$$
\left[\begin{array}{cc|cc}1&2&1&0\\3&5&0&1\end{array}\right].
$$

Apply $R_2\leftarrow R_2-3R_1$, then multiply $R_2$ by $-1$:

$$
\left[\begin{array}{cc|cc}1&2&1&0\\0&1&3&-1\end{array}\right].
$$

Apply $R_1\leftarrow R_1-2R_2$:

$$
\left[\begin{array}{cc|cc}1&0&-5&2\\0&1&3&-1\end{array}\right].
$$

Thus
$$A^{-1}=\begin{pmatrix}-5&2\\3&-1\end{pmatrix}.$$
The same row operations applied to $[A\mid I]$ transform it to $[I\mid A^{-1}]$, because each row operation is multiplication on the left by an invertible elementary matrix.

## Verification
$$
AA^{-1}
=\begin{pmatrix}1&2\\3&5\end{pmatrix}
\begin{pmatrix}-5&2\\3&-1\end{pmatrix}
=\begin{pmatrix}1&0\\0&1\end{pmatrix}.
$$