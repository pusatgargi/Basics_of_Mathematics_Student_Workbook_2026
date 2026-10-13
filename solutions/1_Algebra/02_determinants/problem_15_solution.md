# Problem 15: Combining Determinant Properties

## Problem Statement
Let $A$ and $B$ be invertible $2\times2$ matrices with

$$\det A=-2,\qquad \det B=3.$$

Without finding the entries of the matrices, compute

$$\det\left(B^{-1}A^TB\right).$$

State the determinant properties you use in order and explain why the factors involving $B$ eventually cancel.

## Theoretical Background and Concepts
- **Inverse matrix:** $B^{-1}$ is the inverse of $B$, satisfying $B B^{-1} = I$.
- **Transpose matrix:** $A^T$ is the transpose matrix obtained by exchanging rows and columns of $A$.
- **Determinant rules used:**
  1. *Product rule:* $\det(MN) = \det M \cdot \det N$.
  2. *Inverse determinant rule:* $\det(B^{-1}) = \frac{1}{\det B}$, which follows from $\det(B B^{-1}) = \det I = 1$.
  3. *Transpose determinant rule:* $\det(A^T) = \det A$, since exchanging rows and columns does not alter the determinant.

## Detailed Step-by-Step Solution
1. **Apply the product rule:**
   Factor the determinant of the product:
   $$\det(B^{-1} A^T B) = \det(B^{-1}) \cdot \det(A^T) \cdot \det B.$$

2. **Apply the inverse and transpose determinant rules:**
   - By the inverse determinant rule:
     $$\det(B^{-1}) = \frac{1}{\det B} = \frac{1}{3}.$$
   - By the transpose determinant rule:
     $$\det(A^T) = \det A = -2.$$

3. **Group the scalar factors and evaluate:**
   $$\det(B^{-1} A^T B) = \left(\frac{1}{\det B}\right) \cdot (\det A) \cdot (\det B) = [\det(B^{-1}) \cdot \det B] \cdot \det A.$$
   Because determinants are scalar numbers, their multiplication is associative and commutative:
   $$\det(B^{-1}) \cdot \det B = \frac{1}{3} \cdot 3 = 1.$$
   Therefore, these scalar factors cancel out:
   $$\det(B^{-1} A^T B) = 1 \cdot \det A = \det A = -2.$$

4. **Explanation of the cancellation:**
   The cancellation occurs because $\det(B^{-1}) \cdot \det B = \frac{1}{\det B} \cdot \det B = 1$. It is these **scalar numerical factors** that cancel in the real numbers; no rearrangement or commutativity of the original non-commutative matrix factors ($B^{-1}, A^T, B$) is being assumed.

## Verification and Consistency Checks
- In general, for any invertible matrix $P$, the matrix $P^{-1} M P$ is similar to $M$ and shares the exact same determinant: $\det(P^{-1} M P) = \det M$.
- Here with $M = A^T$, $\det(B^{-1} A^T B) = \det(A^T) = \det A = -2$. The result is completely verified.
