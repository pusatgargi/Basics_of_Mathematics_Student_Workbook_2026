# Problem 11: Shortening the Calculation with Row Operations

## Detailed Step-by-Step Solution
Start with
$$A=\begin{pmatrix}1&2&3\\1&3&4\\1&4&6\end{pmatrix}.$$
Apply $R_2\leftarrow R_2-R_1$ and $R_3\leftarrow R_3-R_1$. Row replacements preserve the determinant:

$$
\begin{pmatrix}1&2&3\\0&1&1\\0&2&3\end{pmatrix}.
$$

Then apply $R_3\leftarrow R_3-2R_2$, which also preserves the determinant:

$$
\begin{pmatrix}1&2&3\\0&1&1\\0&0&1\end{pmatrix}.
$$

Thus $\det A=1\cdot1\cdot1=1$.

## Verification
The operations were all row replacements and did not change the determinant.