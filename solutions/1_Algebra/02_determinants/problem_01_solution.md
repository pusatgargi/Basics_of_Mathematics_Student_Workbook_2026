# Problem 1: Determinant of a 2x2 Matrix

## Problem Statement
Compute

$$\det\begin{pmatrix}3&-2\\5&4\end{pmatrix},\qquad \det\begin{pmatrix}1&7\\2&14\end{pmatrix}.$$

Which matrix is invertible? Justify your answer.

## Theoretical Background and Concepts
For any $2\times2$ matrix $M = \begin{pmatrix}a&b\\c&d\end{pmatrix}$, its determinant is given by the formula:

$$\det M = ad - bc.$$

An invertible matrix is defined as one that possesses a multiplicative inverse matrix that undoes its action ($M M^{-1} = M^{-1}M = I$). Under the standard nonzero-determinant criterion, a square matrix is invertible if and only if its determinant is non-zero ($\det M \neq 0$). If $\det M = 0$, the matrix is singular and has no inverse.

## Detailed Step-by-Step Solution
1. **First matrix:**
   Let $A = \begin{pmatrix}3&-2\\5&4\end{pmatrix}$. Applying the determinant formula:

   $$\det A = (3)(4) - (-2)(5) = 12 - (-10) = 12 + 10 = 22.$$

   Using the nonzero-determinant criterion: since $\det A = 22 \neq 0$, matrix $A$ is **invertible** (it has an inverse that undoes its action).

2. **Second matrix:**
   Let $B = \begin{pmatrix}1&7\\2&14\end{pmatrix}$. Applying the determinant formula:

   $$\det B = (1)(14) - (7)(2) = 14 - 14 = 0.$$

   Using the nonzero-determinant criterion: since $\det B = 0$, matrix $B$ is **not invertible** (no inverse exists to undo its action).

## Verification and Consistency Checks
- For matrix $B$, notice that row 2 is an exact scalar multiple of row 1: $(2, 14) = 2(1, 7)$. Linearly dependent rows always result in a zero determinant, confirming that $B$ is not invertible.
- For matrix $A$, row 1 and row 2 are not multiples of each other, confirming that its determinant is nonzero and that $A$ is invertible.
