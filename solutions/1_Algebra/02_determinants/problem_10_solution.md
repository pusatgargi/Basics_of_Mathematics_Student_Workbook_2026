# Problem 10: Detecting Dependence

## Problem Statement
Without carrying out a full determinant calculation, explain why

$$\det\begin{pmatrix}1&2&3\\2&4&6\\0&1&5\end{pmatrix}=0.$$

Identify a specific dependence between the rows and connect it with noninvertibility of the matrix.

## Theoretical Background and Concepts
A fundamental criterion of linear algebra states that a square matrix has determinant zero if and only if its rows (or columns) are linearly dependent.
If one row of a matrix is an exact scalar multiple of another row ($R_i = c R_j$), the rows are linearly dependent, which immediately forces the determinant to be zero without needing a full expansion. A matrix with determinant zero is singular (noninvertible).

## Detailed Step-by-Step Solution
Let the rows of the matrix be:
$$R_1 = (1, 2, 3),\qquad R_2 = (2, 4, 6),\qquad R_3 = (0, 1, 5).$$

1. **Identify the specific dependence:**
   Comparing $R_1$ and $R_2$:
   $$R_2 = 2 \cdot R_1 = 2(1, 2, 3) = (2, 4, 6).$$
   The second row is an exact scalar multiple of the first row ($R_2 - 2R_1 = 0$).

2. **Connect to determinant zero:**
   Because row 2 is linearly dependent on row 1, the matrix does not have full row rank. By the standard linear dependence criterion for determinants, any matrix with proportional rows has determinant zero:
   $$\det\begin{pmatrix}1&2&3\\2&4&6\\0&1&5\end{pmatrix} = 0.$$

3. **Connect to noninvertibility:**
   Because the rows are linearly dependent, the matrix has rank at most 2, which is strictly less than 3. By the Invertible Matrix Theorem, a square matrix is invertible if and only if its determinant is nonzero (or equivalently, if its rows are linearly independent). Therefore, this matrix is **noninvertible** (it has no inverse).

## Verification and Consistency Checks
Subtracting $2R_1$ from $R_2$ produces an entire row of zeros $(0, 0, 0)$. Expanding along a zero row trivially yields $0$, confirming that $R_2 = 2R_1$ guarantees $\det = 0$ and noninvertibility.
