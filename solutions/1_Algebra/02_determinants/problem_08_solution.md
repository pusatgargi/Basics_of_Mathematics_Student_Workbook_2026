# Problem 8: Determinant of a Product

## Problem Statement
Let $A,B$ be square matrices such that $\det A=3$ and $\det B=-5$. Compute $\det(AB)$, $\det(BA)$ and, if it exists, $\det(A^{-1}B)$. Explain why the first two results are equal even though usually $AB\neq BA$.

## Theoretical Background and Concepts
- **Product rule:** For any square matrices of the same size, $\det(MN) = \det M \cdot \det N$.
- **Inverse matrix and reciprocal rule:** The inverse matrix $A^{-1}$ satisfies $A A^{-1} = I$. Applying the product rule gives:
  $$\det A \cdot \det(A^{-1}) = \det(A A^{-1}) = \det I = 1.$$
  Since $\det A = 3 \neq 0$, dividing by $\det A$ yields the reciprocal rule:
  $$\det(A^{-1}) = \frac{1}{\det A} = \frac{1}{3}.$$
- **Commutativity of scalars:** Determinants are real numbers. While matrix multiplication is generally non-commutative ($AB \neq BA$), multiplication of real numbers is commutative.

## Detailed Step-by-Step Solution
1. **Compute $\det(AB)$:**
   $$\det(AB) = \det A \cdot \det B = 3 \cdot (-5) = -15.$$

2. **Compute $\det(BA)$:**
   $$\det(BA) = \det B \cdot \det A = (-5) \cdot 3 = -15.$$

   **Why the two results are equal:**
   The matrix products $AB$ and $BA$ are usually distinct matrices ($AB \neq BA$). However, their determinants are the scalar products $\det A \cdot \det B$ and $\det B \cdot \det A$. Because real number multiplication is commutative, these two products are equal:
   $$\det(AB) = \det(BA) = -15.$$
   Equal determinants do **not** imply that $AB = BA$.

3. **Compute $\det(A^{-1}B)$:**
   Since $\det A = 3 \neq 0$, $A^{-1}$ exists and $\det(A^{-1}) = \frac{1}{3}$.
   Applying the product rule directly:
   $$\det(A^{-1}B) = \det(A^{-1}) \cdot \det B = \frac{1}{3} \cdot (-5) = -\frac{5}{3}.$$

## Verification and Consistency Checks
Check consistency using multiplicativity:
$$\det(A(A^{-1}B)) = \det A \cdot \det(A^{-1}B) = 3 \cdot \left(-\frac{5}{3}\right) = -5 = \det B.$$
This confirms the result $\det(A^{-1}B) = -\frac{5}{3}$.
