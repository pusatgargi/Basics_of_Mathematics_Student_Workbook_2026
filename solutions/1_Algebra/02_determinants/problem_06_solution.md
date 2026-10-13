# Problem 6: Parameter and Invertibility

## Problem Statement
For

$$A(t)=\begin{pmatrix}t&1\\2&t\end{pmatrix}$$

find all values of $t$ for which the matrix is not invertible. Explain how your answer is related to the determinant being zero.

## Theoretical Background and Concepts
A square matrix $A$ is invertible if and only if its determinant is non-zero ($\det A \neq 0$). When $\det A = 0$, the matrix is singular, meaning its rows (and columns) are linearly dependent, its kernel contains non-zero vectors, and no multiplicative inverse exists.

## Detailed Step-by-Step Solution
1. **Compute the determinant of $A(t)$:**
   Using the standard $2\times2$ determinant formula:

   $$\det A(t) = (t)(t) - (1)(2) = t^2 - 2.$$

2. **Find values of $t$ where the matrix is not invertible:**
   The matrix fails to be invertible when $\det A(t) = 0$:

   $$t^2 - 2 = 0 \implies t^2 = 2 \implies t = \pm\sqrt{2}.$$

   Therefore, $A(t)$ is not invertible for:
   $$t = \sqrt{2}\qquad \text{and}\qquad t = -\sqrt{2}.$$

3. **Invertibility condition:**
   For any $t \in \mathbb{R} \setminus \{-\sqrt{2}, \sqrt{2}\}$, $\det A(t) \neq 0$, and the matrix is invertible with inverse:
   $$A(t)^{-1} = \frac{1}{t^2 - 2}\begin{pmatrix}t & -1 \\ -2 & t\end{pmatrix}.$$

## Verification and Consistency Checks
- Substitute $t = \sqrt{2}$:
  $$A(\sqrt{2}) = \begin{pmatrix}\sqrt{2}&1\\2&\sqrt{2}\end{pmatrix}.$$
  Row 2 is $\sqrt{2}$ times Row 1:
  $$\sqrt{2}(\sqrt{2}, 1) = (2, \sqrt{2}).$$
  Since the rows are proportional, the matrix has rank 1, confirming $\det = 0$ and non-invertibility.
- Substitute $t = -\sqrt{2}$:
  $$A(-\sqrt{2}) = \begin{pmatrix}-\sqrt{2}&1\\2&-\sqrt{2}\end{pmatrix}.$$
  Row 2 is $-\sqrt{2}$ times Row 1:
  $$-\sqrt{2}(-\sqrt{2}, 1) = (2, -\sqrt{2}).$$
  The rows are again proportional, confirming non-invertibility.
