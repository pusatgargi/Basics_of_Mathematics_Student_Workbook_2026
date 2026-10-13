# Problem 12: A Parameter Revealed by a Row Operation

## Problem Statement
For

$$A(t)=\begin{pmatrix}1&2&3\\2&4&t\\0&1&1\end{pmatrix}$$

find the values of $t$ for which the matrix is not invertible.

Before computing the determinant, perform the operation

$$R_2\leftarrow R_2-2R_1$$

and use the resulting structure. At the end, explain what special thing happens to the rows for the value of the parameter you found.

## Theoretical Background and Concepts
- Row replacement $R_i \leftarrow R_i + cR_j$ ($i \neq j$) does not change the determinant.
- A square matrix has no inverse exactly when its determinant is zero ($\det A(t) = 0$).
- When a column has entries with zeros, Laplace expansion along that column is particularly simple because only the non-zero entry contributes.

## Detailed Step-by-Step Solution
1. **Perform the operation $R_2 \leftarrow R_2 - 2R_1$:**
   Apply to row 2:
   $$R_2 = (2 - 2(1),\; 4 - 2(2),\; t - 2(3)) = (0, 0, t - 6).$$
   The resulting matrix is:
   $$B(t) = \begin{pmatrix}1&2&3\\0&0&t-6\\0&1&1\end{pmatrix}.$$
   Since this row operation preserves the determinant:
   $$\det A(t) = \det B(t).$$

2. **Use the structure of the first column:**
   The first column of $B(t)$ is $(1, 0, 0)^T$.
   Expanding along column 1, only the top entry $b_{11} = 1$ contributes, with positive sign $+1$.
   Deleting row 1 and column 1 gives the $2\times2$ minor:
   $$\begin{pmatrix}0&t-6\\1&1\end{pmatrix}.$$
   Applying the $ad - bc$ rule:
   $$\det B(t) = 1 \cdot [0 \cdot 1 - (t - 6) \cdot 1] = -(t - 6) = 6 - t.$$
   Therefore,
   $$\det A(t) = 6 - t.$$

3. **Find the parameter value for noninvertibility:**
   A square matrix has no inverse exactly when its determinant is zero:
   $$6 - t = 0 \implies t = 6.$$
   Thus, the matrix is not invertible for $t = 6$.

4. **Special behavior of the rows at $t = 6$:**
   When $t = 6$, the second row of the original matrix $A(6)$ is:
   $$R_2 = (2, 4, 6).$$
   Notice that:
   $$2 R_1 = 2(1, 2, 3) = (2, 4, 6) = R_2.$$
   At $t = 6$, the original second row is an **exact double of the first row** ($R_2 = 2R_1$).
   Because row 2 and row 1 are linearly dependent, the rows do not span $\mathbb{R}^3$, which explains why the determinant is zero and the matrix has no inverse.

## Verification and Consistency Checks
Substituting $t = 6$ directly into the row operation yields $R_2 - 2R_1 = (0, 0, 0)$, producing a row of zeros and verifying that $\det A(6) = 0$.
