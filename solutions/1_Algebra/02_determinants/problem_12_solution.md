# Problem 12: A Parameter Revealed by a Row Operation

## Detailed Step-by-Step Solution
For
$$A(t)=\begin{pmatrix}1&2&3\\2&4&t\\0&1&1\end{pmatrix},$$
apply $R_2\leftarrow R_2-2R_1$, which preserves the determinant:

$$
\begin{pmatrix}1&2&3\\0&0&t-6\\0&1&1\end{pmatrix}.
$$

Expanding along the first column, the determinant is that of
$\begin{pmatrix}0&t-6\\1&1\end{pmatrix}$, namely $-(t-6)=6-t$.
Hence the matrix is not invertible only when $t=6$.

At $t=6$, the original second row $(2,4,6)$ is twice the first row, so the rows are dependent.

## Verification
The determinant vanishes at $t=6$ and is nonzero for every other value.