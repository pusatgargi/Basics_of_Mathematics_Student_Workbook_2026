# Problem 3: When Does the Inverse Not Exist?

## Problem Statement
For

$$A=\begin{pmatrix}2&4\\1&2\end{pmatrix}$$

explain in two ways why $A^{-1}$ does not exist: using the determinant and using dependence between the rows.

## Theoretical Background and Concepts
An $n\times n$ square matrix fails to be invertible (is singular) under several equivalent conditions established by the Invertible Matrix Theorem:
1. **Determinant condition:** A matrix is invertible if and only if $\det A \neq 0$. If $\det A = 0$, dividing by $\det A$ in the inversion formula produces division by zero, meaning no inverse matrix can satisfy $A A^{-1} = I$.
2. **Linear dependence condition:** A matrix is invertible if and only if its rows (and columns) are linearly independent. If the rows are linearly dependent, the transformation collapses $\mathbb{R}^n$ onto a lower-dimensional subspace (the rank is strictly less than $n$), making the transformation non-injective and non-surjective, hence non-invertible.

## Detailed Step-by-Step Solution
1. **Explanation 1: Using the Determinant:**
   Calculate the determinant of $A$:
   $$\det A = ad - bc = (2)(2) - (4)(1) = 4 - 4 = 0.$$
   Because $\det A = 0$, if an inverse $A^{-1}$ were to exist, we would have:
   $$\det(A A^{-1}) = \det A \cdot \det(A^{-1}) = 0 \cdot \det(A^{-1}) = 0.$$
   However, $A A^{-1} = I$, and $\det I = 1$. This would imply $0 = 1$, which is a contradiction.
   Therefore, no inverse matrix $A^{-1}$ can exist.

2. **Explanation 2: Using Dependence Between the Rows:**
   Let $R_1 = (2, 4)$ and $R_2 = (1, 2)$ be the row vectors of $A$.
   Observe that:
   $$R_1 = 2 \cdot R_2 = 2 \cdot (1, 2) = (2, 4).$$
   Equivalently, $R_1 - 2R_2 = (0, 0)$, which is a non-trivial linear combination equaling the zero vector.
   This proves that the rows of $A$ are linearly dependent.
   Geometrically, the rows lie on the same line through the origin in $\mathbb{R}^2$. The row space has dimension $\text{rank}(A) = 1 < 2$.
   Because the rank is less than 2, the image of the linear map $x \mapsto Ax$ is only a 1-dimensional line in $\mathbb{R}^2$, meaning it cannot be inverted to cover all of $\mathbb{R}^2$.

## Verification and Consistency Checks
- Column dependence check:
  Notice that column 2 is twice column 1:
  $$\begin{pmatrix}4\\2\end{pmatrix} = 2 \begin{pmatrix}2\\1\end{pmatrix}.$$
  Thus $A \begin{pmatrix}2\\-1\end{pmatrix} = \begin{pmatrix}0\\0\end{pmatrix}$. Since $A$ maps a non-zero vector to zero, it has a non-trivial null space, which confirms $A$ is not invertible.
- Both explanations (determinant zero and row dependence) independently and consistently show why $A^{-1}$ does not exist.
