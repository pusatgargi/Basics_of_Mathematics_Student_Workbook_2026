# Problem 3: When Does the Inverse Not Exist?

## Problem Statement
For

$$A=\begin{pmatrix}2&4\\1&2\end{pmatrix}$$

explain in two ways why $A^{-1}$ does not exist: using the determinant and using dependence between the rows.

## Theoretical Background and Concepts
An $n\times n$ square matrix fails to be invertible (is singular) under several standard equivalent criteria:
1. **Determinant criterion:** A matrix is invertible if and only if $\det A \neq 0$. If $\det A = 0$, no inverse matrix can exist.
2. **Row dependence criterion:** A matrix is invertible if and only if its row vectors are linearly independent. If the rows are linearly dependent, the matrix fails to have full rank, meaning its corresponding linear map collapses dimension and cannot be inverted.

## Detailed Step-by-Step Solution
1. **Explanation 1: Using the determinant:**
   Compute the determinant of $A = \begin{pmatrix}2&4\\1&2\end{pmatrix}$:
   $$\det A = ad - bc = 2 \cdot 2 - 4 \cdot 1 = 4 - 4 = 0.$$
   By the standard determinant criterion, an inverse exists if and only if $\det A \neq 0$. Because $\det A = 0$, the matrix $A$ is singular and $A^{-1}$ does not exist.

2. **Explanation 2: Using dependence between the rows:**
   Let the row vectors of $A$ be $R_1 = (2, 4)$ and $R_2 = (1, 2)$.
   Notice that:
   $$R_1 = 2 \cdot R_2 = 2(1, 2) = (2, 4).$$
   Because the first row is an exact scalar multiple of the second row, the rows are linearly dependent.
   Linearly dependent rows span a 1-dimensional subspace rather than the full 2-dimensional space $\mathbb{R}^2$. Because the transformation collapses $\mathbb{R}^2$ onto a single line, it is not one-to-one or onto, so no inverse transformation exists.

## Verification and Consistency Checks
Both standard criteria independently confirm non-invertibility:
- Determinant: $\det A = 4 - 4 = 0$.
- Row dependence: $R_1 - 2R_2 = (0, 0)$.
The two arguments are completely consistent.
