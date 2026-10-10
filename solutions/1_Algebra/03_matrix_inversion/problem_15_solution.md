# Problem 15: Two Methods for Solving the Same System

## Detailed Step-by-Step Solution
For $A=\begin{pmatrix}2&1\\1&3\end{pmatrix}$, $\det A=5$, so
$$A^{-1}=\frac15\begin{pmatrix}3&-1\\-1&2\end{pmatrix}.$$

Therefore
$$
x=A^{-1}b
=\frac15\begin{pmatrix}3&-1\\-1&2\end{pmatrix}
\begin{pmatrix}7\\8\end{pmatrix}
=\begin{pmatrix}\frac{13}{5}\\\frac95\end{pmatrix}.
$$

For elimination, the augmented matrix is
$$
\left[\begin{array}{cc|c}2&1&7\\1&3&8\end{array}\right]
\longrightarrow
\left[\begin{array}{cc|c}1&3&8\\0&-5&-9\end{array}\right].
$$
Thus $y=\frac95$ and $x=8-3y=\frac{13}{5}$.

## Verification
Both methods give $x=(13/5,\,9/5)^T$, and substitution gives $Ax=(7,8)^T$. For this single system, elimination is simpler because it avoids computing an entire inverse.