# Problem 5: Row Operations

## Problem Statement
For

$$A=\begin{pmatrix}1&2&3\\2&1&0\\-1&4&2\end{pmatrix}$$

find $\det A$ by simplifying the matrix with row operations. At each step, indicate whether and how the determinant changes.

## Theoretical Background and Concepts
The plan is to create zeros below the main diagonal so that the matrix becomes upper triangular, allowing the determinant to be read directly as the product of its diagonal entries.
We use two standard rules:
1. **Row-replacement rule:** Adding a scalar multiple of another row to a row ($R_i \leftarrow R_i + cR_j$, $i \neq j$) preserves the determinant (the determinant does not change).
2. **Triangular matrix rule:** The determinant of a triangular matrix is the product of its diagonal entries.

Here, $R_i$ denotes row $i$.

## Detailed Step-by-Step Solution
Start with:
$$A = \begin{pmatrix}1&2&3\\2&1&0\\-1&4&2\end{pmatrix}.$$

1. **Step 1: Create zeros in the first column below $a_{11} = 1$:**
   - Operation 1: $R_2 \leftarrow R_2 - 2R_1$.
     *Effect on determinant:* Preserves the determinant (unchanged).
     *Calculation:* We use $-2R_1$ to cancel the entry below $1$. The first cancellation is $2 - 2(1) = 0$.
     Full row: $(2 - 2(1),\; 1 - 2(2),\; 0 - 2(3)) = (0, -3, -6)$.
   - Operation 2: $R_3 \leftarrow R_3 + R_1$.
     *Effect on determinant:* Preserves the determinant (unchanged).
     *Calculation:* $(-1 + 1,\; 4 + 2,\; 2 + 3) = (0, 6, 5)$.

   Matrix after Step 1:
   $$A_1 = \begin{pmatrix}1&2&3\\0&-3&-6\\0&6&5\end{pmatrix},\qquad \det A = \det A_1.$$

2. **Step 2: Create a zero in the second column below $a_{22} = -3$:**
   - Operation 3: $R_3 \leftarrow R_3 + 2R_2$.
     *Effect on determinant:* Preserves the determinant (unchanged).
     *Calculation:* The update uses the current $R_2$ to cancel the $6$ below $-3$:
     $$6 + 2(-3) = 0.$$
     Full row: $(0 + 2(0),\; 6 + 2(-3),\; 5 + 2(-6)) = (0, 0, -7)$.

   Matrix after Step 2 (upper triangular):
   $$U = \begin{pmatrix}1&2&3\\0&-3&-6\\0&0&-7\end{pmatrix},\qquad \det A = \det U.$$

3. **Step 3: Evaluate the determinant as a diagonal product:**
   By the triangular matrix rule:
   $$\det A = \det U = 1 \cdot (-3) \cdot (-7) = 21.$$

## Verification and Consistency Checks
Each elementary row operation performed was a replacement of the form $R_i \leftarrow R_i + cR_j$, which leaves the determinant unchanged at every step. The final matrix is upper triangular with diagonal elements $1, -3, -7$, confirming $\det A = 21$.
