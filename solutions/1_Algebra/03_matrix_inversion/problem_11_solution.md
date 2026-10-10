# Problem 11: Parameter and Invertibility

## Detailed Step-by-Step Solution
For $A(t)=\begin{pmatrix}1&t\\t&1\end{pmatrix}$,

$$\det A(t)=1-t^2.$$

It is invertible exactly when $t\ne1$ and $t\ne-1$. In those cases,

$$
A(t)^{-1}=\frac{1}{1-t^2}
\begin{pmatrix}1&-t\\-t&1\end{pmatrix}.
$$

At $t=1$ or $t=-1$, the denominator is zero and the rows are dependent, so the matrix has no inverse; the formula is not defined there.

## Verification
Multiplication by $A(t)$ gives $I$ for every $t$ with $1-t^2\ne0$.