# Problem 2: Formula for a 2x2 Matrix

## Problem Statement
Find the inverse of

$$A=\begin{pmatrix}3&2\\5&4\end{pmatrix}$$

using the formula for a $2\times2$ matrix. At the end, check the result by computing one product with $A$.

## Theoretical Background and Concepts
For any $2\times2$ matrix $M = \begin{pmatrix}a&b\\c&d\end{pmatrix}$, its inverse exists if and only if its determinant is non-zero:

$$ad - bc \neq 0.$$

When this condition is satisfied, the explicit formula for the inverse is:

$$M^{-1} = \frac{1}{ad - bc} \begin{pmatrix}d & -b \\ -c & a\end{pmatrix}.$$

This formula involves three steps:
1. Swapping the diagonal entries ($a$ and $d$).
2. Negating the off-diagonal entries ($b \to -b$ and $c \to -c$).
3. Dividing the resulting matrix by the scalar determinant $ad - bc$.

## Detailed Step-by-Step Solution
Given matrix:
$$A = \begin{pmatrix}3&2\\5&4\end{pmatrix}.$$

1. **Identify entries and compute determinant:**
   Here, $a = 3$, $b = 2$, $c = 5$, and $d = 4$.
   $$\det A = ad - bc = 3 \cdot 4 - 2 \cdot 5 = 12 - 10 = 2.$$
   Since $\det A = 2 \neq 0$, the inverse exists.

2. **Apply the $2\times2$ inverse formula:**
   - Swapping the diagonal entries gives $4$ at $(1,1)$ and $3$ at $(2,2)$.
   - Negating the off-diagonal entries gives $-2$ at $(1,2)$ and $-5$ at $(2,1)$.
   - Dividing by the determinant $2$:
   $$A^{-1} = \frac{1}{2} \begin{pmatrix}4 & -2 \\ -5 & 3\end{pmatrix} = \begin{pmatrix}2 & -1 \\ -\frac{5}{2} & \frac{3}{2}\end{pmatrix}.$$

3. **Check by computing the product $AA^{-1}$:**
   $$AA^{-1} = \begin{pmatrix}3&2\\5&4\end{pmatrix} \begin{pmatrix}2 & -1 \\ -\frac{5}{2} & \frac{3}{2}\end{pmatrix}$$
   Computing the row-column sums:
   - Entry $(1,1)$: $3(2) + 2\left(-\frac{5}{2}\right) = 6 - 5 = 1$
   - Entry $(1,2)$: $3(-1) + 2\left(\frac{3}{2}\right) = -3 + 3 = 0$
   - Entry $(2,1)$: $5(2) + 4\left(-\frac{5}{2}\right) = 10 - 10 = 0$
   - Entry $(2,2)$: $5(-1) + 4\left(\frac{3}{2}\right) = -5 + 6 = 1$

   Assembling the result:
   $$AA^{-1} = \begin{pmatrix}1&0\\0&1\end{pmatrix} = I.$$

## Verification and Consistency Checks
Obtaining the identity matrix $I$ is the defining verification that the computed matrix is indeed the multiplicative inverse of $A$. The row-column sums evaluate directly to $1$ on the diagonal and $0$ off the diagonal, confirming $A^{-1}$.
