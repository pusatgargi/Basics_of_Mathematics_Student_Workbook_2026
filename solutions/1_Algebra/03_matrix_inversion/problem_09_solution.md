# Problem 9: Matrix Equation

## Detailed Step-by-Step Solution
From $AX=B$, multiply on the left by $A^{-1}$, giving $X=A^{-1}B$.
Here
$$A^{-1}=\begin{pmatrix}1&-2\\0&1\end{pmatrix},$$
so

$$
X=\begin{pmatrix}1&-2\\0&1\end{pmatrix}
\begin{pmatrix}3&1\\2&4\end{pmatrix}
=\begin{pmatrix}-1&-7\\2&4\end{pmatrix}.
$$

## Verification
$$
AX=\begin{pmatrix}1&2\\0&1\end{pmatrix}
\begin{pmatrix}-1&-7\\2&4\end{pmatrix}
=\begin{pmatrix}3&1\\2&4\end{pmatrix}=B.
$$