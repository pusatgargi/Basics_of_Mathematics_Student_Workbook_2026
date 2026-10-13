# Problem 5: Row Operations

## Problem Statement
For

$$A=\begin{pmatrix}1&2&3\\2&1&0\\-1&4&2\end{pmatrix}$$

find $\det A$ by simplifying the matrix with row operations. At each step, indicate whether and how the determinant changes.

## Theoretical Background and Concepts
Elementary row operations affect determinants as follows:
1. **Row addition ($R_i \leftarrow R_i + cR_j$, $i \neq j$):** Leaves the determinant unchanged ($\det A' = \det A$).
2. **Row swap ($R_i \leftrightarrow R_j$):** Multiplies the determinant by $-1$ ($\det A' = -\det A$).
3. **Row scaling ($R_i \leftarrow cR_i$, $c \neq 0$):** Multiplies the determinant by $c$ ($\det A' = c\det A$).

By applying type 1 operations, we can reduce a matrix to upper triangular form without changing the determinant. Once in triangular form, the determinant is the product of the diagonal entries.

## Detailed Step-by-Step Solution
Start with matrix $A$:

$$A = \begin{pmatrix}1&2&3\\2&1&0\\-1&4&2\end{pmatrix}.$$

1. **Step 1: Eliminate entries below $a_{11}$ in Column 1:**
   - Operation 1: $R_2 \leftarrow R_2 - 2R_1$.
     $$\det(\text{matrix}) \text{ is unchanged.}$$
     $$R_2 = (2 - 2(1), 1 - 2(2), 0 - 2(3)) = (0, -3, -6).$$
   - Operation 2: $R_3 \leftarrow R_3 + R_1$.
     $$\det(\text{matrix}) \text{ is unchanged.}$$
     $$R_3 = (-1 + 1, 4 + 2, 2 + 3) = (0, 6, 5).$$

   Matrix after Step 1:
   $$A_1 = \begin{pmatrix}1&2&3\\0&-3&-6\\0&6&5\end{pmatrix},\qquad \det A = \det A_1.$$

2. **Step 2: Eliminate entry below $a_{22}$ in Column 2:**
   - Operation 3: $R_3 \leftarrow R_3 + 2R_2$.
     $$\det(\text{matrix}) \text{ is unchanged.}$$
     $$R_3 = (0 + 2(0), 6 + 2(-3), 5 + 2(-6)) = (0, 0, -7).$$

   Matrix after Step 2:
   $$U = \begin{pmatrix}1&2&3\\0&-3&-6\\0&0&-7\end{pmatrix},\qquad \det A = \det U.$$

3. **Step 3: Compute determinant of upper triangular matrix $U$:**
   $$\det U = 1 \cdot (-3) \cdot (-7) = 21.$$

   Since no operation changed the value of the determinant:
   $$\det A = 21.$$

## Verification and Consistency Checks
Check using Sarrus' rule on the original matrix $A$:
- Downward diagonals:
  $$(1)(1)(2) + (2)(0)(-1) + (3)(2)(4) = 2 + 0 + 24 = 26.$$
- Upward diagonals:
  $$(3)(1)(-1) + (1)(0)(4) + (2)(2)(2) = -3 + 0 + 8 = 5.$$
- Determinant:
  $$\det A = 26 - 5 = 21.$$
Both methods agree, verifying that $\det A = 21$.
