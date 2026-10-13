# Problem 1: Definition of the Inverse

## Problem Statement
For

$$A=\begin{pmatrix}2&1\\1&1\end{pmatrix},\qquad B=\begin{pmatrix}1&-1\\-1&2\end{pmatrix}$$

check, without using a formula, whether $B=A^{-1}$. Compute $AB$ and $BA$ and relate the result to the definition of the inverse.

## Theoretical Background and Concepts
By definition, a square matrix $B$ is the multiplicative inverse of an $n\times n$ matrix $A$ (denoted $B = A^{-1}$) if and only if both products yield the identity matrix:

$$AB = I \qquad \text{and} \qquad BA = I,$$

where $I = \begin{pmatrix}1&0\\0&1\end{pmatrix}$ is the $2\times2$ identity matrix. The identity matrix acts as the neutral element of matrix multiplication ($AI = IA = A$).
Matrix multiplication is computed using the row-by-column rule: entry $(i, j)$ of the product is the dot product of row $i$ of the first matrix and column $j$ of the second matrix.

## Detailed Step-by-Step Solution
1. **Compute $AB$ using the row-by-column rule:**
   $$AB = \begin{pmatrix}2&1\\1&1\end{pmatrix}\begin{pmatrix}1&-1\\-1&2\end{pmatrix}$$
   Computing the individual entries:
   - Row 1, Column 1: $2(1) + 1(-1) = 2 - 1 = 1$
   - Row 1, Column 2: $2(-1) + 1(2) = -2 + 2 = 0$
   - Row 2, Column 1: $1(1) + 1(-1) = 1 - 1 = 0$
   - Row 2, Column 2: $1(-1) + 1(2) = -1 + 2 = 1$

   Assembling the product matrix:
   $$AB = \begin{pmatrix}1&0\\0&1\end{pmatrix} = I.$$

2. **Compute $BA$ using the row-by-column rule:**
   $$BA = \begin{pmatrix}1&-1\\-1&2\end{pmatrix}\begin{pmatrix}2&1\\1&1\end{pmatrix}$$
   Computing the individual entries:
   - Row 1, Column 1: $1(2) + (-1)(1) = 2 - 1 = 1$
   - Row 1, Column 2: $1(1) + (-1)(1) = 1 - 1 = 0$
   - Row 2, Column 1: $(-1)(2) + 2(1) = -2 + 2 = 0$
   - Row 2, Column 2: $(-1)(1) + 2(1) = -1 + 2 = 1$

   Assembling the product matrix:
   $$BA = \begin{pmatrix}1&0\\0&1\end{pmatrix} = I.$$

3. **Connect to the definition of the inverse:**
   Because multiplying $A$ and $B$ in both orders yields the identity matrix $I$:
   $$AB = I \qquad \text{and} \qquad BA = I,$$
   matrix $B$ satisfies the fundamental definition of the matrix inverse. Therefore, $B = A^{-1}$.

## Verification and Consistency Checks
Both explicit row-by-column multiplications produce the identity matrix $\begin{pmatrix}1&0\\0&1\end{pmatrix}$. Since the check is satisfied in both directions without assuming commutativity in advance, $B$ is verified to be the inverse of $A$.
