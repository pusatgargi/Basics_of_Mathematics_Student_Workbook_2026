# Problem 10: Detecting Dependence

## Problem Statement
Without carrying out a full determinant calculation, explain why

$$\det\begin{pmatrix}1&2&3\\2&4&6\\0&1&5\end{pmatrix}=0.$$

Identify a specific dependence between the rows and connect it with noninvertibility of the matrix.

## Theoretical Background and Concepts
A fundamental property of determinants is that if the rows (or columns) of a square matrix are linearly dependent, its determinant is zero.
Specifically, if one row is a scalar multiple of another row ($R_i = c R_j$), or more generally if a nontrivial linear combination of rows equals zero, then:
1. The rank of the matrix is strictly less than $n$ (the matrix does not have full rank).
2. The determinant is zero: $\det A = 0$.
3. The matrix is singular (not invertible).

## Detailed Step-by-Step Solution
Let the rows of the matrix be:
$$R_1 = (1, 2, 3),\qquad R_2 = (2, 4, 6),\qquad R_3 = (0, 1, 5).$$

1. **Identify the dependence:**
   Comparing $R_1$ and $R_2$:
   $$R_2 = 2 \cdot R_1 = (2 \cdot 1, 2 \cdot 2, 2 \cdot 3) = (2, 4, 6).$$
   The second row is an exact scalar multiple of the first row ($R_2 - 2R_1 = 0$).

2. **Connect to the determinant:**
   Performing the elementary row operation $R_2 \leftarrow R_2 - 2R_1$ does not change the determinant:
   $$\det\begin{pmatrix}1&2&3\\2&4&6\\0&1&5\end{pmatrix} = \det\begin{pmatrix}1&2&3\\0&0&0\\0&1&5\end{pmatrix}.$$
   Since the resulting matrix contains an entire row of zeros, expanding along that row immediately gives:
   $$\det A = 0.$$

3. **Connection to noninvertibility:**
   Because row 2 provides no independent direction, the rows span at most a 2-dimensional subspace of $\mathbb{R}^3$. The rank of the matrix is at most 2, which is less than 3. By the Invertible Matrix Theorem, a square matrix is invertible if and only if it has full rank (rank equal to its dimension). Therefore, the matrix cannot be inverted.

## Verification and Consistency Checks
Verifying with Laplace expansion along column 1:
$$\det A = 1 \cdot \det\begin{pmatrix}4&6\\1&5\end{pmatrix} - 2 \cdot \det\begin{pmatrix}2&3\\1&5\end{pmatrix} + 0$$
$$\det A = 1(20 - 6) - 2(10 - 3) = 14 - 2(7) = 14 - 14 = 0.$$
The result is confirmed: the determinant is indeed 0.
