# Problem 6: Solving a System Using the Inverse

## Problem Statement
Solve

$$Ax=b,$$

where

$$A=\begin{pmatrix}2&1\\1&3\end{pmatrix},\qquad b=\begin{pmatrix}5\\7\end{pmatrix},$$

using $x=A^{-1}b$. Then substitute the resulting vector back into the equation and check the result.

## Theoretical Background and Concepts
For a linear system $Ax = b$ with an invertible matrix $A$:
Multiplying both sides on the left by $A^{-1}$:
$$A^{-1}(Ax) = A^{-1}b \implies (A^{-1}A)x = A^{-1}b \implies Ix = A^{-1}b \implies x = A^{-1}b.$$
This holds because $A^{-1}A = I$.
For a $2\times2$ matrix $\begin{pmatrix}a&b\\c&d\end{pmatrix}$, the inverse formula is:
$$A^{-1} = \frac{1}{ad - bc}\begin{pmatrix}d & -b \\ -c & a\end{pmatrix}.$$

## Detailed Step-by-Step Solution
1. **Compute $A^{-1}$ using the $2\times2$ inverse formula:**
   For $A = \begin{pmatrix}2&1\\1&3\end{pmatrix}$:
   $$\det A = 2 \cdot 3 - 1 \cdot 1 = 6 - 1 = 5.$$
   Since $\det A = 5 \neq 0$, the inverse is:
   $$A^{-1} = \frac{1}{5}\begin{pmatrix}3 & -1 \\ -1 & 2\end{pmatrix}.$$

2. **Compute the solution vector $x = A^{-1}b$:**
   $$x = \frac{1}{5}\begin{pmatrix}3 & -1 \\ -1 & 2\end{pmatrix}\begin{pmatrix}5\\7\end{pmatrix}$$
   Computing the solution components:
   $$x_1 = \frac{3(5) - 1(7)}{5} = \frac{15 - 7}{5} = \frac{8}{5}.$$
   $$x_2 = \frac{-1(5) + 2(7)}{5} = \frac{-5 + 14}{5} = \frac{9}{5}.$$

   Therefore:
   $$x = \begin{pmatrix}\frac{8}{5} \\ \frac{9}{5}\end{pmatrix}.$$

3. **Check by substituting back into $Ax$:**
   Compute the product $Ax$:
   $$Ax = \begin{pmatrix}2&1\\1&3\end{pmatrix}\begin{pmatrix}\frac{8}{5}\\\frac{9}{5}\end{pmatrix}$$
   Computing both components:
   - First component: $2\left(\frac{8}{5}\right) + 1\left(\frac{9}{5}\right) = \frac{16 + 9}{5} = \frac{25}{5} = 5$.
   - Second component: $1\left(\frac{8}{5}\right) + 3\left(\frac{9}{5}\right) = \frac{8 + 27}{5} = \frac{35}{5} = 7$.

   Thus,
   $$Ax = \begin{pmatrix}5\\7\end{pmatrix} = b.$$
   Recovering the original vector $b$ verifies that the solution is correct.

## Verification and Consistency Checks
The substitution $Ax$ recovers the exact right-hand side vector $b = \begin{pmatrix}5\\7\end{pmatrix}$. This confirms the calculation and the validity of $x = A^{-1}b$.
