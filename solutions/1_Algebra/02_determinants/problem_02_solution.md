# Problem 2: Determinant of a 3x3 Matrix

## Problem Statement
For

$$A=\begin{pmatrix}1&2&-1\\0&3&4\\2&1&5\end{pmatrix}$$

compute $\det A$ using Sarrus' rule. Then perform one simple check using a chosen property of the determinant.

## Theoretical Background and Concepts
Sarrus' rule is a computational method specific to $3\times3$ matrices. Writing the first two columns to the right of the matrix:

$$\begin{matrix}
a_{11} & a_{12} & a_{13} & a_{11} & a_{12} \\
a_{21} & a_{22} & a_{23} & a_{21} & a_{22} \\
a_{31} & a_{32} & a_{33} & a_{31} & a_{32}
\end{matrix}$$

The determinant is the sum of the products along the three main downward diagonals minus the sum of the products along the three upward diagonals:

$$\det A = (a_{11}a_{22}a_{33} + a_{12}a_{23}a_{31} + a_{13}a_{21}a_{32}) - (a_{13}a_{22}a_{31} + a_{11}a_{23}a_{32} + a_{12}a_{21}a_{33}).$$

Alternatively, Laplace cofactor expansion along any row or column yields the exact same determinant value.

## Detailed Step-by-Step Solution
1. **Computation via Sarrus' rule:**
   - Downward diagonal products:
     $$(1)(3)(5) = 15$$
     $$(2)(4)(2) = 16$$
     $$(-1)(0)(1) = 0$$
     Sum of downward diagonals $= 15 + 16 + 0 = 31$.

   - Upward diagonal products:
     $$(-1)(3)(2) = -6$$
     $$(1)(4)(1) = 4$$
     $$(2)(0)(5) = 0$$
     Sum of upward diagonals $= -6 + 4 + 0 = -2$.

   - Determinant:
     $$\det A = 31 - (-2) = 31 + 2 = 33.$$

2. **Check using Laplace cofactor expansion along Column 1:**
   Column 1 is convenient because it contains a zero entry:

   $$\det A = a_{11} C_{11} + a_{21} C_{21} + a_{31} C_{31}$$
   $$\det A = 1 \cdot \det\begin{pmatrix}3&4\\1&5\end{pmatrix} - 0 \cdot \det\begin{pmatrix}2&-1\\1&5\end{pmatrix} + 2 \cdot \det\begin{pmatrix}2&-1\\3&4\end{pmatrix}.$$

   Computing the $2\times2$ minors:
   $$\det\begin{pmatrix}3&4\\1&5\end{pmatrix} = (3)(5) - (4)(1) = 15 - 4 = 11.$$
   $$\det\begin{pmatrix}2&-1\\3&4\end{pmatrix} = (2)(4) - (-1)(3) = 8 + 3 = 11.$$

   Substituting back:
   $$\det A = 1(11) - 0 + 2(11) = 11 + 22 = 33.$$

## Verification and Consistency Checks
Both methods (Sarrus' rule and Laplace expansion along the first column) yield the identical result $\det A = 33$. Since the determinant is non-zero, the matrix $A$ is invertible.
