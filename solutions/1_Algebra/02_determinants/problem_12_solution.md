# Problem 12: A Parameter Revealed by a Row Operation

## Problem Statement
For

$$A(t)=\begin{pmatrix}1&2&3\\2&4&t\\0&1&1\end{pmatrix}$$

find the values of $t$ for which the matrix is not invertible.

Before computing the determinant, perform the operation

$$R_2\leftarrow R_2-2R_1$$

and use the resulting structure. At the end, explain what special thing happens to the rows for the value of the parameter you found.

## Theoretical Background and Concepts
A square matrix is not invertible if and only if its determinant is zero.
Performing a row replacement operation $R_i \leftarrow R_i + cR_j$ ($i \neq j$) does not change the determinant of the matrix. When a row operation produces an almost-zero row, Laplace cofactor expansion along that row is extremely straightforward.

## Detailed Step-by-Step Solution
1. **Perform the row operation $R_2 \leftarrow R_2 - 2R_1$:**
   Applying the operation to $R_2$:
   $$R_2 - 2R_1 = (2 - 2(1),\; 4 - 2(2),\; t - 2(3)) = (0, 0, t-6).$$
   The transformed matrix is:
   $$B(t) = \begin{pmatrix}1&2&3\\0&0&t-6\\0&1&1\end{pmatrix}.$$
   Since row replacements preserve the determinant:
   $$\det A(t) = \det B(t).$$

2. **Compute the determinant of $B(t)$:**
   Expand along Row 2 of $B(t)$, where the only potentially nonzero entry is in column 3:
   $$\det B(t) = (-1)^{2+3} (t-6) \cdot \det\begin{pmatrix}1&2\\0&1\end{pmatrix}$$
   $$\det B(t) = -(t-6) \cdot (1 \cdot 1 - 2 \cdot 0) = -(t-6)(1) = 6 - t.$$
   Therefore:
   $$\det A(t) = 6 - t.$$

3. **Determine the values of $t$ for non-invertibility:**
   The matrix is not invertible if and only if:
   $$\det A(t) = 0 \implies 6 - t = 0 \implies t = 6.$$

4. **Explanation of the special behavior of the rows:**
   When $t = 6$:
   The second row of the original matrix is $R_2 = (2, 4, 6)$.
   Notice that $2 \cdot R_1 = 2 \cdot (1, 2, 3) = (2, 4, 6) = R_2$.
   Thus, for $t = 6$, the second row is an **exact scalar multiple of the first row** ($R_2 = 2R_1$).
   The rows are linearly dependent, so the matrix fails to have full rank and is not invertible.

## Verification and Consistency Checks
- Directly computing $\det A(t)$ using Laplace expansion along column 1 of original $A(t)$:
  $$\det A(t) = 1 \cdot \det\begin{pmatrix}4&t\\1&1\end{pmatrix} - 2 \cdot \det\begin{pmatrix}2&3\\1&1\end{pmatrix} + 0$$
  $$\det A(t) = (4 - t) - 2(2 - 3) = (4 - t) - 2(-1) = 4 - t + 2 = 6 - t.$$
  Setting $6 - t = 0$ yields $t = 6$.
  The result is fully verified.
