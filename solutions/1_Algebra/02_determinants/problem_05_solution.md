# Problem 5: Row Operations

## Detailed Step-by-Step Solution
Start with
$$A=\begin{pmatrix}1&2&3\\2&1&0\\-1&4&2\end{pmatrix}.$$
Replace $R_2$ by $R_2-2R_1$ and $R_3$ by $R_3+R_1$. These row replacements do not change the determinant:

$$
\begin{pmatrix}1&2&3\\0&-3&-6\\0&6&5\end{pmatrix}.
$$

Now replace $R_3$ by $R_3+2R_2$, again without changing the determinant:

$$
\begin{pmatrix}1&2&3\\0&-3&-6\\0&0&-7\end{pmatrix}.
$$

The result is upper triangular, so $\det A=1\cdot(-3)\cdot(-7)=21$.

## Verification
All operations used were row replacements, which preserve the determinant.