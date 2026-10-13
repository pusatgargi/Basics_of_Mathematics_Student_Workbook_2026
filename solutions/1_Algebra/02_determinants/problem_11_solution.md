# Problem 11: Shortening the Calculation with Row Operations

## Problem Statement
Compute

$$\det\begin{pmatrix}1&2&3\\1&3&4\\1&4&6\end{pmatrix}$$

by first performing row operations that create as many zeros as possible. State which operations do not change the determinant.

## Theoretical Background and Concepts
Elementary row replacement operations of the form $R_i \leftarrow R_i + cR_j$ ($i \neq j$) preserve the determinant (they do not change its value).
The plan is:
1. Subtract $R_1$ from the two rows below it to clear the first column.
2. Subtract twice the current $R_2$ from $R_3$ to clear the entry below the second pivot.
The resulting zeros below the main diagonal make the matrix upper triangular, so its determinant is simply the product of the diagonal entries.

## Detailed Step-by-Step Solution
Start with:
$$A = \begin{pmatrix}1&2&3\\1&3&4\\1&4&6\end{pmatrix}.$$

1. **Step 1: Clear the first column below $a_{11} = 1$:**
   Subtract $R_1$ from rows 2 and 3:
   - $R_2 \leftarrow R_2 - R_1$:
     $$R_2 = (1 - 1,\; 3 - 2,\; 4 - 3) = (0, 1, 1).$$
     *(This operation preserves the determinant).*
   - $R_3 \leftarrow R_3 - R_1$:
     $$R_3 = (1 - 1,\; 4 - 2,\; 6 - 3) = (0, 2, 3).$$
     *(This operation preserves the determinant).*

   The matrix becomes:
   $$A_1 = \begin{pmatrix}1&2&3\\0&1&1\\0&2&3\end{pmatrix},\qquad \det A = \det A_1.$$

2. **Step 2: Clear the entry below the second pivot $a_{22} = 1$:**
   Subtract twice the current $R_2$ from $R_3$:
   - $R_3 \leftarrow R_3 - 2R_2$:
     $$R_3 = (0 - 2(0),\; 2 - 2(1),\; 3 - 2(1)) = (0, 0, 1).$$
     *(This operation preserves the determinant).*

   The matrix is now upper triangular:
   $$U = \begin{pmatrix}1&2&3\\0&1&1\\0&0&1\end{pmatrix},\qquad \det A = \det U.$$

3. **Step 3: Read off the diagonal product:**
   Because all operations preserved the determinant and $U$ is upper triangular:
   $$\det A = \det U = 1 \cdot 1 \cdot 1 = 1.$$

## Verification and Consistency Checks
Every operation used was a row replacement ($R_i \leftarrow R_i - cR_j$), which does not change the determinant. The diagonal entries of the resulting upper-triangular matrix are all $1$, confirming that $\det A = 1$.
