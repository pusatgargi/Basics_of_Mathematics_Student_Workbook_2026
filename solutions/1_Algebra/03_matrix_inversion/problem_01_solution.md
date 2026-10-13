# Problem 1: Definition of the Inverse

## Problem Statement
For

$$A=\begin{pmatrix}2&1\\1&1\end{pmatrix},\qquad B=\begin{pmatrix}1&-1\\-1&2\end{pmatrix}$$

check, without using a formula, whether $B=A^{-1}$. Compute $AB$ and $BA$ and relate the result to the definition of the inverse.

## Theoretical Background and Concepts
By definition, a square matrix $B$ of size $n\times n$ is the inverse of an $n\times n$ matrix $A$ (denoted $A^{-1}$) if and only if:

$$AB = I_n \qquad \text{and} \qquad BA = I_n,$$

where $I_n$ is the $n\times n$ identity matrix. For square matrices, if either $AB = I$ or $BA = I$ holds, the other equality is automatically satisfied; however, checking both products explicitly verifies two-sided invertibility from first principles.

## Detailed Step-by-Step Solution
1. **Compute $AB$:**
   $$AB = \begin{pmatrix}2&1\\1&1\end{pmatrix}\begin{pmatrix}1&-1\\-1&2\end{pmatrix}$$
   Entries of $AB$:
   - Row 1, Column 1: $(2)(1) + (1)(-1) = 2 - 1 = 1$
   - Row 1, Column 2: $(2)(-1) + (1)(2) = -2 + 2 = 0$
   - Row 2, Column 1: $(1)(1) + (1)(-1) = 1 - 1 = 0$
   - Row 2, Column 2: $(1)(-1) + (1)(2) = -1 + 2 = 1$

   Therefore:
   $$AB = \begin{pmatrix}1&0\\0&1\end{pmatrix} = I.$$

2. **Compute $BA$:**
   $$BA = \begin{pmatrix}1&-1\\-1&2\end{pmatrix}\begin{pmatrix}2&1\\1&1\end{pmatrix}$$
   Entries of $BA$:
   - Row 1, Column 1: $(1)(2) + (-1)(1) = 2 - 1 = 1$
   - Row 1, Column 2: $(1)(1) + (-1)(1) = 1 - 1 = 0$
   - Row 2, Column 1: $(-1)(2) + (2)(1) = -2 + 2 = 0$
   - Row 2, Column 2: $(-1)(1) + (2)(1) = -1 + 2 = 1$

   Therefore:
   $$BA = \begin{pmatrix}1&0\\0&1\end{pmatrix} = I.$$

3. **Relate to the definition of the inverse:**
   Because both products yield the $2\times2$ identity matrix:
   $$AB = BA = I,$$
   it follows directly from the fundamental definition that $B$ is the unique multiplicative inverse of $A$, i.e., $B = A^{-1}$ (and likewise $A = B^{-1}$).

## Verification and Consistency Checks
- Determinant check:
  $$\det A = (2)(1) - (1)(1) = 1 \neq 0.$$
  $$\det B = (1)(2) - (-1)(-1) = 2 - 1 = 1.$$
  Notice that $\det(AB) = \det A \cdot \det B = 1 \cdot 1 = 1 = \det I$.
- The equality $AB = BA = I$ holds unconditionally, confirming that $B = A^{-1}$.
