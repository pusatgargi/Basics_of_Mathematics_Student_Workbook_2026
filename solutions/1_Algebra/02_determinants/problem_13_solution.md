# Problem 13: Determinant by Elimination

## Problem Statement
Compute the determinant

$$A=\begin{pmatrix}1&2&3\\2&5&7\\1&0&2\end{pmatrix}$$

using elimination. Record the effect of every row operation used on the value of the determinant.

## Theoretical Background and Concepts
Gaussian elimination aims to create zeros below the main diagonal to reduce the matrix to upper triangular form.
- Adding a multiple of one row to another ($R_i \leftarrow R_i + cR_j$) preserves the determinant (multiplies by 1).
- The determinant of an upper triangular matrix is the product of its diagonal entries.

## Detailed Step-by-Step Solution
Start with:
$$A = \begin{pmatrix}1&2&3\\2&5&7\\1&0&2\end{pmatrix}.$$

1. **Step 1: Clear below the first pivot $a_{11} = 1$:**
   - Operation 1: $R_2 \leftarrow R_2 - 2R_1$.
     *Multiplier $-2$ cancels entry $a_{21} = 2$.*
     $$R_2 = (2 - 2(1),\; 5 - 2(2),\; 7 - 2(3)) = (0, 1, 1).$$
     *Effect on determinant:* Multiplied by 1 (unchanged).
   - Operation 2: $R_3 \leftarrow R_3 - R_1$.
     *Multiplier $-1$ cancels entry $a_{31} = 1$.*
     $$R_3 = (1 - 1,\; 0 - 2,\; 2 - 3) = (0, -2, -1).$$
     *Effect on determinant:* Multiplied by 1 (unchanged).

   Current matrix:
   $$A_1 = \begin{pmatrix}1&2&3\\0&1&1\\0&-2&-1\end{pmatrix},\qquad \det A = \det A_1.$$

2. **Step 2: Clear below the second pivot $a_{22} = 1$:**
   - Operation 3: $R_3 \leftarrow R_3 + 2R_2$.
     *Multiplier $+2$ cancels entry $a_{32} = -2$ using the current row 2.*
     $$R_3 = (0 + 2(0),\; -2 + 2(1),\; -1 + 2(1)) = (0, 0, 1).$$
     *Effect on determinant:* Multiplied by 1 (unchanged).

   The matrix is now upper triangular:
   $$U = \begin{pmatrix}1&2&3\\0&1&1\\0&0&1\end{pmatrix},\qquad \det A = \det U.$$

3. **Step 3: Evaluate the determinant:**
   Connecting the upper triangular matrix to its diagonal product:
   $$\det A = \det U = 1 \cdot 1 \cdot 1 = 1.$$

## Verification and Consistency Checks
All three row operations were replacements of the form $R_i \leftarrow R_i + cR_j$, each preserving the determinant. The final upper-triangular matrix has diagonal entries $1, 1, 1$, giving $\det A = 1$.
