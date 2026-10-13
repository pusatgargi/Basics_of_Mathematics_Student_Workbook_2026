# Problem 12: Finding Inverses Without Starting from Scratch

## Problem Statement
It is known that

$$A^{-1}=\begin{pmatrix}2&-1\\-3&2\end{pmatrix}.$$

Without finding $A$, compute $(3A)^{-1}$, $(A^T)^{-1}$, and $(A^2)^{-1}$. Justify each result using the appropriate property.

## Theoretical Background and Concepts
For any invertible matrix $A$ and scalar $c \neq 0$:
1. **Scalar multiple rule:** $(cA)^{-1} = \frac{1}{c} A^{-1}$.
2. **Transpose rule:** $(A^T)^{-1} = (A^{-1})^T$. Transposition exchanges rows and columns.
3. **Power rule:** $(A^2)^{-1} = (A^{-1})^2$. Squaring a matrix means multiplying it by itself: $(A^{-1})^2 = A^{-1} A^{-1}$.

## Detailed Step-by-Step Solution
Given:
$$A^{-1} = \begin{pmatrix}2 & -1 \\ -3 & 2\end{pmatrix}.$$

1. **Compute $(3A)^{-1}$:**
   Using the scalar rule with $c = 3$:
   $$(3A)^{-1} = \frac{1}{3} A^{-1} = \frac{1}{3} \begin{pmatrix}2 & -1 \\ -3 & 2\end{pmatrix} = \begin{pmatrix}\frac{2}{3} & -\frac{1}{3} \\ -1 & \frac{2}{3}\end{pmatrix}.$$

2. **Compute $(A^T)^{-1}$:**
   Using the transpose property $(A^T)^{-1} = (A^{-1})^T$, we exchange the rows and columns of $A^{-1}$:
   $$(A^T)^{-1} = \begin{pmatrix}2 & -1 \\ -3 & 2\end{pmatrix}^T = \begin{pmatrix}2 & -3 \\ -1 & 2\end{pmatrix}.$$

3. **Compute $(A^2)^{-1}$:**
   Squaring $A^{-1}$ means multiplying it by itself:
   $$(A^2)^{-1} = (A^{-1})^2 = \begin{pmatrix}2 & -1 \\ -3 & 2\end{pmatrix}\begin{pmatrix}2 & -1 \\ -3 & 2\end{pmatrix}.$$
   Calculating the row-column products:
   - Row 1, Column 1: $2(2) + (-1)(-3) = 4 + 3 = 7$
   - Row 1, Column 2: $2(-1) + (-1)(2) = -2 - 2 = -4$
   - Row 2, Column 1: $(-3)(2) + 2(-3) = -6 - 6 = -12$
   - Row 2, Column 2: $(-3)(-1) + 2(2) = 3 + 4 = 7$

   Therefore:
   $$(A^2)^{-1} = \begin{pmatrix}7 & -4 \\ -12 & 7\end{pmatrix}.$$

## Verification and Consistency Checks
- For $(3A)^{-1}$: $3A \cdot \frac{1}{3}A^{-1} = (3 \cdot \frac{1}{3})(A A^{-1}) = 1 \cdot I = I$.
- For $(A^T)^{-1}$: $A^T (A^{-1})^T = (A^{-1} A)^T = I^T = I$.
- For $(A^2)^{-1}$: $A^2 (A^{-1})^2 = A(A A^{-1})A^{-1} = A I A^{-1} = A A^{-1} = I$.
All properties and computed values are verified.
