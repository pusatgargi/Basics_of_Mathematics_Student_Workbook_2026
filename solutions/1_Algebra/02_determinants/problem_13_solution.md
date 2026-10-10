# Problem 13: Determinant by Elimination

## Detailed Step-by-Step Solution
Start with
$$A=\begin{pmatrix}1&2&3\\2&5&7\\1&0&2\end{pmatrix}.$$
Apply $R_2\leftarrow R_2-2R_1$ and $R_3\leftarrow R_3-R_1$. Neither row replacement changes the determinant:

$$
\begin{pmatrix}1&2&3\\0&1&1\\0&-2&-1\end{pmatrix}.
$$

Apply $R_3\leftarrow R_3+2R_2$, also determinant-preserving:

$$
\begin{pmatrix}1&2&3\\0&1&1\\0&0&1\end{pmatrix}.
$$

Therefore $\det A=1\cdot1\cdot1=1$.

## Verification
The final matrix is upper triangular and all operations were determinant-preserving row replacements.