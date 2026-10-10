# Problem 6: Solving a System Using the Inverse

## Detailed Step-by-Step Solution
For $A=\begin{pmatrix}2&1\\1&3\end{pmatrix}$, $\det A=5$ and

$$
A^{-1}=\frac15\begin{pmatrix}3&-1\\-1&2\end{pmatrix}.
$$

Thus

$$
x=A^{-1}b
=\frac15\begin{pmatrix}3&-1\\-1&2\end{pmatrix}
\begin{pmatrix}5\\7\end{pmatrix}
=\begin{pmatrix}\frac85\\\frac95\end{pmatrix}.
$$

## Verification
$$
A x=\begin{pmatrix}2&1\\1&3\end{pmatrix}
\begin{pmatrix}\frac85\\\frac95\end{pmatrix}
=\begin{pmatrix}5\\7\end{pmatrix}=b.
$$