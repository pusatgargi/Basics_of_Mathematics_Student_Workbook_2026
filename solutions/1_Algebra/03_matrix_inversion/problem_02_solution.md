# Problem 2: Formula for a 2x2 Matrix

## Problem Statement
Find the inverse of

$$A=\begin{pmatrix}3&2\\5&4\end{pmatrix}$$

using the formula for a $2\times2$ matrix. At the end, check the result by computing one product with $A$.

## Theoretical Background and Concepts
For an arbitrary $2\times2$ matrix $M = \begin{pmatrix}a&b\\c&d\end{pmatrix}$, its inverse exists if and only if $\det M = ad - bc \neq 0$.
The explicit formula for the inverse is:

$$M^{-1} = \frac{1}{\det M} \begin{pmatrix}d & -b \\ -c & a\end{pmatrix} = \frac{1}{ad - bc} \begin{pmatrix}d & -b \\ -c & a\end{pmatrix}.$$

This formula swaps the main diagonal elements ($a$ and $d$) and negates the off-diagonal elements ($b$ and $c$), scaled by the reciprocal of the determinant.

## Detailed Step-by-Step Solution
Given matrix:
$$A = \begin{pmatrix}3&2\\5&4\end{pmatrix}.$$

1. **Step 1: Compute the determinant of $A$:**
   $$\det A = ad - bc = (3)(4) - (2)(5) = 12 - 10 = 2.$$
   Since $\det A = 2 \neq 0$, the inverse exists.

2. **Step 2: Apply the $2\times2$ inverse formula:**
   Here $a = 3$, $b = 2$, $c = 5$, and $d = 4$.
   $$A^{-1} = \frac{1}{2} \begin{pmatrix}4 & -2 \\ -5 & 3\end{pmatrix} = \begin{pmatrix}2 & -1 \\ -\frac{5}{2} & \frac{3}{2}\end{pmatrix}.$$

3. **Step 3: Verification by computing $AA^{-1}$:**
   $$AA^{-1} = \begin{pmatrix}3&2\\5&4\end{pmatrix} \begin{pmatrix}2 & -1 \\ -\frac{5}{2} & \frac{3}{2}\end{pmatrix}$$
   Computing entries:
   - Row 1, Column 1: $3(2) + 2\left(-\frac{5}{2}\right) = 6 - 5 = 1$
   - Row 1, Column 2: $3(-1) + 2\left(\frac{3}{2}\right) = -3 + 3 = 0$
   - Row 2, Column 1: $5(2) + 4\left(-\frac{5}{2}\right) = 10 - 10 = 0$
   - Row 2, Column 2: $5(-1) + 4\left(\frac{3}{2}\right) = -5 + 6 = 1$

   Therefore:
   $$AA^{-1} = \begin{pmatrix}1&0\\0&1\end{pmatrix} = I.$$

## Verification and Consistency Checks
- Product check: $AA^{-1} = I$ is verified.
- Reverse product check:
  $$A^{-1}A = \frac{1}{2}\begin{pmatrix}4&-2\\-5&3\end{pmatrix}\begin{pmatrix}3&2\\5&4\end{pmatrix} = \frac{1}{2}\begin{pmatrix}12-10 & 8-8 \\ -15+15 & -10+12\end{pmatrix} = \frac{1}{2}\begin{pmatrix}2&0\\0&2\end{pmatrix} = \begin{pmatrix}1&0\\0&1\end{pmatrix} = I.$$
- Determinant check: $\det(A^{-1}) = (2)(3/2) - (-1)(-5/2) = 3 - 5/2 = 1/2 = 1/\det A$.
The computed inverse is accurate.
