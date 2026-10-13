# Problem 6: Solving a System Using the Inverse

## Problem Statement
Solve

$$Ax=b,$$

where

$$A=\begin{pmatrix}2&1\\1&3\end{pmatrix},\qquad b=\begin{pmatrix}5\\7\end{pmatrix},$$

using $x=A^{-1}b$. Then substitute the resulting vector back into the equation and check the result.

## Theoretical Background and Concepts
For a linear system $Ax = b$ where $A$ is an $n\times n$ invertible matrix:
Multiplying both sides on the left by $A^{-1}$:

$$A^{-1}(Ax) = A^{-1}b \implies (A^{-1}A)x = A^{-1}b \implies Ix = A^{-1}b \implies x = A^{-1}b.$$

This establishes the fundamental connection between matrix inversion and solving systems of linear equations.

## Detailed Step-by-Step Solution
1. **Find $A^{-1}$:**
   For $A = \begin{pmatrix}2&1\\1&3\end{pmatrix}$:
   $$\det A = (2)(3) - (1)(1) = 6 - 1 = 5.$$
   Since $\det A = 5 \neq 0$, the inverse exists:
   $$A^{-1} = \frac{1}{5}\begin{pmatrix}3 & -1 \\ -1 & 2\end{pmatrix}.$$

2. **Compute the solution vector $x = A^{-1}b$:**
   $$x = \frac{1}{5}\begin{pmatrix}3 & -1 \\ -1 & 2\end{pmatrix}\begin{pmatrix}5\\7\end{pmatrix}$$
   Computing the matrix-vector product:
   $$x_1 = \frac{1}{5}[(3)(5) + (-1)(7)] = \frac{1}{5}[15 - 7] = \frac{8}{5}.$$
   $$x_2 = \frac{1}{5}[(-1)(5) + (2)(7)] = \frac{1}{5}[-5 + 14] = \frac{9}{5}.$$

   Therefore:
   $$x = \begin{pmatrix}\frac{8}{5} \\ \frac{9}{5}\end{pmatrix}.$$

3. **Check by substituting back into $Ax = b$:**
   $$Ax = \begin{pmatrix}2&1\\1&3\end{pmatrix}\begin{pmatrix}\frac{8}{5}\\\frac{9}{5}\end{pmatrix}$$
   - Row 1: $2\left(\frac{8}{5}\right) + 1\left(\frac{9}{5}\right) = \frac{16 + 9}{5} = \frac{25}{5} = 5$
   - Row 2: $1\left(\frac{8}{5}\right) + 3\left(\frac{9}{5}\right) = \frac{8 + 27}{5} = \frac{35}{5} = 7$

   $$Ax = \begin{pmatrix}5\\7\end{pmatrix} = b.$$

## Verification and Consistency Checks
- The substitution $Ax = b$ produces exactly the vector $b = \begin{pmatrix}5\\7\end{pmatrix}$.
- Direct elimination check on the system:
  $$\begin{cases}2x_1 + x_2 = 5 \\ x_1 + 3x_2 = 7\end{cases}$$
  Subtracting $2 \times$ (eq 2) from (eq 1): $(2x_1 + x_2) - (2x_1 + 6x_2) = 5 - 14 \implies -5x_2 = -9 \implies x_2 = 9/5$.
  Then $x_1 = 7 - 3(9/5) = 35/5 - 27/5 = 8/5$.
  Both methods produce the identical unique solution.
