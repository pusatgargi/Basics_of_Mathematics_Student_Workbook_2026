# Problem 5: A 3x3 Matrix

## Detailed Step-by-Step Solution
For
$$A=\begin{pmatrix}1&1&0\\0&1&1\\1&0&1\end{pmatrix},$$
Gauss-Jordan elimination on $[A\mid I]$ gives

$$
\left[\begin{array}{ccc|ccc}
1&0&0&\frac12&-\frac12&\frac12\\
0&1&0&\frac12&\frac12&-\frac12\\
0&0&1&-\frac12&\frac12&\frac12
\end{array}\right].
$$

Therefore
$$
A^{-1}=\frac12\begin{pmatrix}1&-1&1\\1&1&-1\\-1&1&1\end{pmatrix}.
$$

## Verification
$$
AA^{-1}
=\frac12\begin{pmatrix}1&1&0\\0&1&1\\1&0&1\end{pmatrix}
\begin{pmatrix}1&-1&1\\1&1&-1\\-1&1&1\end{pmatrix}
=\frac12\begin{pmatrix}2&0&0\\0&2&0\\0&0&2\end{pmatrix}
=I.
$$