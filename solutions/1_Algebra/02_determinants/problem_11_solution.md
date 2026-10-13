# Problem 11: Shortening the Calculation with Row Operations

## Problem Statement
Compute

$$\det\begin{pmatrix}1&2&3\\1&3&4\\1&4&6\end{pmatrix}$$

by first performing row operations that create as many zeros as possible. State which operations do not change the determinant.

## Theoretical Background and Concepts
The elementary row replacement operation:
$$R_i \leftarrow R_i + cR_j\quad (i \neq j)$$
adds a scalar multiple of row $j$ to row $i$. This operation **preserves the determinant exactly**:
$$\det(E_{i,j}(c) A) = \det(E_{i,j}(c)) \cdot \det A = 1 \cdot \det A = \det A.$$
By using a pivot row to create zeros in a column, the calculation of the determinant can be drastically simplified into computing a smaller minor or reading off the diagonal product of an upper triangular matrix.

## Detailed Step-by-Step Solution
Given matrix:
$$A = \begin{pmatrix}1&2&3\\1&3&4\\1&4&6\end{pmatrix}.$$

1. **Step 1: Create zeros in the first column below $a_{11}$:**
   Use Row 1 as the pivot:
   - Operation 1: $R_2 \leftarrow R_2 - R_1$.
     This operation does not change the determinant.
     $$R_2 = (1 - 1,\; 3 - 2,\; 4 - 3) = (0, 1, 1).$$
   - Operation 2: $R_3 \leftarrow R_3 - R_1$.
     This operation does not change the determinant.
     $$R_3 = (1 - 1,\; 4 - 2,\; 6 - 3) = (0, 2, 3).$$

   The matrix becomes:
   $$A_1 = \begin{pmatrix}1&2&3\\0&1&1\\0&2&3\end{pmatrix},\qquad \det A = \det A_1.$$

2. **Step 2: Create a zero in the second column below $a_{22}$:**
   Use Row 2 as the pivot:
   - Operation 3: $R_3 \leftarrow R_3 - 2R_2$.
     This operation does not change the determinant.
     $$R_3 = (0 - 2(0),\; 2 - 2(1),\; 3 - 2(1)) = (0, 0, 1).$$

   The matrix is now in upper triangular form:
   $$U = \begin{pmatrix}1&2&3\\0&1&1\\0&0&1\end{pmatrix},\qquad \det A = \det U.$$

3. **Step 3: Evaluate the determinant:**
   Since $U$ is upper triangular, its determinant is the product of its diagonal elements:
   $$\det U = u_{11} \cdot u_{22} \cdot u_{33} = 1 \cdot 1 \cdot 1 = 1.$$
   Therefore:
   $$\det A = 1.$$

## Verification and Consistency Checks
- Verification using Laplace expansion along column 1 of $A_1$:
  $$\det A_1 = 1 \cdot \det\begin{pmatrix}1&1\\2&3\end{pmatrix} = 1 \cdot (1 \cdot 3 - 1 \cdot 2) = 1 \cdot (3 - 2) = 1.$$
- Direct calculation using Sarrus' rule on original $A$:
  - Downward diagonals:
    $$(1)(3)(6) + (2)(4)(1) + (3)(1)(4) = 18 + 8 + 12 = 38.$$
  - Upward diagonals:
    $$(3)(3)(1) + (1)(4)(4) + (2)(1)(6) = 9 + 16 + 12 = 37.$$
  - Determinant:
    $$\det A = 38 - 37 = 1.$$
Both methods confirm that $\det A = 1$.
