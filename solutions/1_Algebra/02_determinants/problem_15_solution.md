# Problem 15: Combining Determinant Properties

## Problem Statement
Let $A$ and $B$ be invertible $2\times2$ matrices with

$$\det A=-2,\qquad \det B=3.$$

Without finding the entries of the matrices, compute

$$\det\left(B^{-1}A^TB\right).$$

State the determinant properties you use in order and explain why the factors involving $B$ eventually cancel.

## Theoretical Background and Concepts
For any square $n\times n$ invertible matrices $M$ and $N$:
1. **Multiplicative property:** $\det(MN) = \det M \cdot \det N$.
2. **Inverse property:** $\det(M^{-1}) = \frac{1}{\det M}$ (since $\det(M M^{-1}) = \det(I) = 1$).
3. **Transpose property:** $\det(M^T) = \det M$.
4. **Commutativity of scalar multiplication:** Determinants are real numbers, and multiplication of real numbers satisfies $xy = yx$.
5. **Similarity invariance:** If two matrices are similar ($P^{-1} M P$), they represent the same linear transformation in different bases and share the same determinant: $\det(P^{-1} M P) = \det M$.

## Detailed Step-by-Step Solution
1. **Apply the multiplicative property:**
   Express the determinant of the product as the product of determinants:
   $$\det(B^{-1} A^T B) = \det(B^{-1}) \cdot \det(A^T) \cdot \det(B).$$

2. **Apply the inverse property to $B^{-1}$:**
   Since $B$ is invertible and $\det B = 3$:
   $$\det(B^{-1}) = \frac{1}{\det B} = \frac{1}{3}.$$

3. **Apply the transpose property to $A^T$:**
   $$\det(A^T) = \det A = -2.$$

4. **Substitute and evaluate:**
   $$\det(B^{-1} A^T B) = \left(\frac{1}{\det B}\right) \cdot (\det A) \cdot (\det B).$$
   Using commutativity and associativity of scalar multiplication in $\mathbb{R}$:
   $$\det(B^{-1} A^T B) = \left(\frac{1}{\det B} \cdot \det B\right) \cdot \det A = 1 \cdot \det A = \det A.$$
   Substituting $\det A = -2$:
   $$\det(B^{-1} A^T B) = -2.$$

5. **Explanation of the cancellation:**
   The factors involving $B$ cancel because matrix $B^{-1} A^T B$ is a similarity transformation of $A^T$. The determinant reflects the factor by which volume is scaled: $B$ changes the coordinate basis scaling volume by $\det B = 3$, and $B^{-1}$ undoes this scaling by $\det(B^{-1}) = 1/3$. Consequently, the net geometric effect of $B$ and $B^{-1}$ on the determinant is $(1/3) \times 3 = 1$, leaving only the determinant of $A^T$, which equals $\det A$.

## Verification and Consistency Checks
- Algebraic check:
  $$\det(B^{-1} A^T B) = \frac{1}{3} \cdot (-2) \cdot 3 = -2.$$
- General theory: For any invertible matrix $P$ and any square matrix $M$, $\det(P^{-1} M P) = \det M$. Here $M = A^T$, so $\det(B^{-1} A^T B) = \det(A^T) = \det A = -2$. The result is completely verified.
