# Problem 12: Finding Inverses Without Starting from Scratch

## Problem Statement
It is known that

$$A^{-1}=\begin{pmatrix}2&-1\\-3&2\end{pmatrix}.$$

Without finding $A$, compute $(3A)^{-1}$, $(A^T)^{-1}$, and $(A^2)^{-1}$. Justify each result using the appropriate property.

## Theoretical Background and Concepts
For any invertible matrix $A$ and scalar $c \neq 0$:
1. **Scalar multiple of an inverse:** $(cA)^{-1} = \frac{1}{c} A^{-1}$.
2. **Inverse of a transpose:** $(A^T)^{-1} = (A^{-1})^T$. Transposition and inversion commute.
3. **Inverse of a power:** $(A^k)^{-1} = (A^{-1})^k$ for any positive integer $k$. In particular, $(A^2)^{-1} = (A^{-1})^2 = A^{-1} A^{-1}$.

Using these algebraic properties allows us to determine the inverses directly from $A^{-1}$ without first computing $A = (A^{-1})^{-1}$.

## Detailed Step-by-Step Solution
Given:
$$A^{-1} = \begin{pmatrix}2 & -1 \\ -3 & 2\end{pmatrix}.$$

1. **Compute $(3A)^{-1}$:**
   Using the scalar property $(cA)^{-1} = \frac{1}{c} A^{-1}$ with $c = 3$:
   $$(3A)^{-1} = \frac{1}{3} A^{-1} = \frac{1}{3} \begin{pmatrix}2 & -1 \\ -3 & 2\end{pmatrix} = \begin{pmatrix}\frac{2}{3} & -\frac{1}{3} \\ -1 & \frac{2}{3}\end{pmatrix}.$$

2. **Compute $(A^T)^{-1}$:**
   Using the property $(A^T)^{-1} = (A^{-1})^T$:
   $$(A^T)^{-1} = \begin{pmatrix}2 & -1 \\ -3 & 2\end{pmatrix}^T = \begin{pmatrix}2 & -3 \\ -1 & 2\end{pmatrix}.$$

3. **Compute $(A^2)^{-1}$:**
   Using the power property $(A^2)^{-1} = (A^{-1})^2 = A^{-1} A^{-1}$:
   $$(A^2)^{-1} = \begin{pmatrix}2 & -1 \\ -3 & 2\end{pmatrix}\begin{pmatrix}2 & -1 \\ -3 & 2\end{pmatrix}.$$
   Calculating entries:
   - $(1,1)$: $(2)(2) + (-1)(-3) = 4 + 3 = 7$
   - $(1,2)$: $(2)(-1) + (-1)(2) = -2 - 2 = -4$
   - $(2,1)$: $(-3)(2) + (2)(-3) = -6 - 6 = -12$
   - $(2,2)$: $(-3)(-1) + (2)(2) = 3 + 4 = 7$

   Therefore:
   $$(A^2)^{-1} = \begin{pmatrix}7 & -4 \\ -12 & 7\end{pmatrix}.$$

## Verification and Consistency Checks
- Determinant check on $A^{-1}$:
  $$\det(A^{-1}) = (2)(2) - (-1)(-3) = 4 - 3 = 1.$$
  - For $(3A)^{-1}$: $\det((3A)^{-1}) = (1/3)^2 \det(A^{-1}) = 1/9$. From the matrix: $(2/3)(2/3) - (-1/3)(-1) = 4/9 - 3/9 = 1/9$.
  - For $(A^T)^{-1}$: $\det((A^T)^{-1}) = \det(A^{-1}) = 1$. From the matrix: $(2)(2) - (-3)(-1) = 4 - 3 = 1$.
  - For $(A^2)^{-1}$: $\det((A^2)^{-1}) = (\det A^{-1})^2 = 1^2 = 1$. From the matrix: $(7)(7) - (-4)(-12) = 49 - 48 = 1$.
All determinants and properties match seamlessly.
