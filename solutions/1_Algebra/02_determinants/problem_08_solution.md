# Problem 8: Determinant of a Product

## Problem Statement
Let $A,B$ be square matrices such that $\det A=3$ and $\det B=-5$. Compute $\det(AB)$, $\det(BA)$ and, if it exists, $\det(A^{-1}B)$. Explain why the first two results are equal even though usually $AB\neq BA$.

## Theoretical Background and Concepts
1. **Determinant of a product:** For any two square matrices $A$ and $B$ of the same size:
   $$\det(AB) = \det A \cdot \det B.$$
2. **Determinant of an inverse:** If $\det A \neq 0$, then $A$ is invertible, and:
   $$\det(A^{-1}) = \frac{1}{\det A}.$$
3. **Commutativity of numbers:** While matrix multiplication is non-commutative in general ($AB \neq BA$), determinants are real numbers (scalars). Multiplication of real numbers is commutative:
   $$\det A \cdot \det B = \det B \cdot \det A.$$

## Detailed Step-by-Step Solution
1. **Compute $\det(AB)$:**
   $$\det(AB) = \det A \cdot \det B = 3 \cdot (-5) = -15.$$

2. **Compute $\det(BA)$:**
   $$\det(BA) = \det B \cdot \det A = (-5) \cdot 3 = -15.$$

   **Why $\det(AB) = \det(BA)$:**
   Although the matrix products $AB$ and $BA$ are usually distinct matrices ($AB \neq BA$), their determinants are the product of the scalars $\det A$ and $\det B$. Because multiplication in $\mathbb{R}$ is commutative, $\det(AB) = \det(BA)$ always holds.

3. **Compute $\det(A^{-1}B)$:**
   Since $\det A = 3 \neq 0$, $A^{-1}$ exists and $\det(A^{-1}) = \frac{1}{\det A} = \frac{1}{3}$.
   Therefore:
   $$\det(A^{-1}B) = \det(A^{-1}) \cdot \det B = \frac{1}{3} \cdot (-5) = -\frac{5}{3}.$$

## Verification and Consistency Checks
- Since $\det(A(A^{-1}B)) = \det(B) = -5$, checking multiplicativity gives:
  $$\det A \cdot \det(A^{-1}B) = 3 \cdot \left(-\frac{5}{3}\right) = -5 = \det B.$$
  The result is completely consistent.
