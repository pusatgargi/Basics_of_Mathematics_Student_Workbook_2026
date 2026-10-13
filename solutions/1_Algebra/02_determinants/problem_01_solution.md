# Problem 1: Determinant of a 2x2 Matrix

## Problem Statement
Compute

$$\det\begin{pmatrix}3&-2\\5&4\end{pmatrix},\qquad \det\begin{pmatrix}1&7\\2&14\end{pmatrix}.$$

Which matrix is invertible? Justify your answer.

## Theoretical Background and Concepts
For any $2\times2$ matrix $M=\begin{pmatrix}a&b\\c&d\end{pmatrix}$, its determinant is computed by the formula:

$$\det M = ad - bc.$$

A square matrix is invertible (non-singular) if and only if its determinant is non-zero, that is, $\det M \neq 0$. If $\det M = 0$, the matrix is singular and does not possess a multiplicative inverse.

## Detailed Step-by-Step Solution
1. **First matrix:**
   Let $A = \begin{pmatrix}3&-2\\5&4\end{pmatrix}$. Applying the determinant formula:

   $$\det A = (3)(4) - (-2)(5) = 12 - (-10) = 12 + 10 = 22.$$

   Since $\det A = 22 \neq 0$, the matrix $A$ is invertible.

2. **Second matrix:**
   Let $B = \begin{pmatrix}1&7\\2&14\end{pmatrix}$. Applying the determinant formula:

   $$\det B = (1)(14) - (7)(2) = 14 - 14 = 0.$$

   Since $\det B = 0$, the matrix $B$ is not invertible.

## Verification and Consistency Checks
- For matrix $B$, notice that row 2 is an exact scalar multiple of row 1:
  $$(2, 14) = 2 \cdot (1, 7).$$
  Linearly dependent rows always result in a zero determinant, confirming that $B$ cannot be inverted.
- For matrix $A$, row 1 and row 2 are linearly independent since no scalar $c$ satisfies $(5, 4) = c(3, -2)$. This confirms that $\det A \neq 0$ and $A$ is invertible.
