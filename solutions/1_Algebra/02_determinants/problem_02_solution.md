# Problem 2: Determinant of a 3x3 Matrix

## Problem Statement
For

$$A=\begin{pmatrix}1&2&-1\\0&3&4\\2&1&5\end{pmatrix}$$

compute $\det A$ using Sarrus' rule. Then perform one simple check using a chosen property of the determinant.

## Theoretical Background and Concepts
Sarrus' rule is a method for computing the determinant of a $3\times3$ matrix. By writing the first two columns to the right of the matrix:

$$\begin{matrix}
a_{11} & a_{12} & a_{13} & a_{11} & a_{12} \\
a_{21} & a_{22} & a_{23} & a_{21} & a_{22} \\
a_{31} & a_{32} & a_{33} & a_{31} & a_{32}
\end{matrix}$$

Sarrus selects the three downward diagonal products and adds them, then selects the three upward diagonal products and subtracts them:

$$\det A = (a_{11}a_{22}a_{33} + a_{12}a_{23}a_{31} + a_{13}a_{21}a_{32}) - (a_{13}a_{22}a_{31} + a_{11}a_{23}a_{32} + a_{12}a_{21}a_{33}).$$

The standard row-replacement property states that adding a multiple of one row to another row leaves the determinant unchanged ($\det A' = \det A$).

## Detailed Step-by-Step Solution
1. **Computation using Sarrus' rule:**
   - Downward diagonal products:
     $$(1)(3)(5) = 15,$$
     $$(2)(4)(2) = 16,$$
     $$(-1)(0)(1) = 0.$$
     Sum of downward products $= 15 + 16 + 0 = 31$.

   - Upward diagonal products:
     $$(-1)(3)(2) = -6,$$
     $$(1)(4)(1) = 4,$$
     $$(2)(0)(5) = 0.$$
     Sum of upward products $= -6 + 4 + 0 = -2$.

   - Determinant:
     $$\det A = 31 - (-2) = 31 + 2 = 33.$$

2. **Simple check using the row-replacement property:**
   Instead of carrying out a second full expansion, we perform one elementary row operation to create a zero in the first column:
   $$R_3 \leftarrow R_3 - 2R_1.$$
   By the standard row-replacement property, this operation preserves the determinant.
   Computing the new row 3:
   $$R_3 = (2 - 2(1),\; 1 - 2(2),\; 5 - 2(-1)) = (0, -3, 7).$$
   The resulting matrix is:
   $$\begin{pmatrix}1&2&-1\\0&3&4\\0&-3&7\end{pmatrix}.$$
   The first column is now $(1, 0, 0)^T$. Expanding along this first column, only the top entry contributes:
   $$\det A = 1 \cdot \det\begin{pmatrix}3&4\\-3&7\end{pmatrix} = 1 \cdot [(3)(7) - (4)(-3)] = 21 - (-12) = 33.$$

## Verification and Consistency Checks
Both the Sarrus diagonal calculation and the single row-replacement property check give $\det A = 33$, verifying the result without requiring two full redundant expansions.
