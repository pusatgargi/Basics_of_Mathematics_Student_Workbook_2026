# Problem 7: Using Properties Instead of Recomputing

## Problem Statement
Suppose that for a $3\times3$ matrix, $\det A=-4$. Compute

$$\det(2A),\qquad \det(A^T),\qquad \det(A^2),\qquad \det(-A).$$

Justify each answer using the appropriate property.

## Theoretical Background and Concepts
For any $n\times n$ square matrix $A$ (here $n=3$) and scalar $c \in \mathbb{R}$:
1. **Scalar multiplication:** $\det(cA) = c^n \det A$, because factoring a scalar out of an $n\times n$ matrix scales each of the $n$ rows by $c$.
2. **Transposition:** $\det(A^T) = \det A$, because transposition swaps rows and columns without altering the determinant value.
3. **Multiplicativity:** $\det(AB) = \det A \cdot \det B$, which implies $\det(A^k) = (\det A)^k$ for any positive integer $k$.
4. **Negation:** As a special case of scalar scaling with $c = -1$, $\det(-A) = (-1)^n \det A$.

## Detailed Step-by-Step Solution
Given $n = 3$ and $\det A = -4$:

1. **Compute $\det(2A)$:**
   Using the scalar multiplication property with $c = 2$ and $n = 3$:
   $$\det(2A) = 2^3 \cdot \det A = 8 \cdot (-4) = -32.$$

2. **Compute $\det(A^T)$:**
   Using the transposition property:
   $$\det(A^T) = \det A = -4.$$

3. **Compute $\det(A^2)$:**
   Using the multiplicative property:
   $$\det(A^2) = (\det A)^2 = (-4)^2 = 16.$$

4. **Compute $\det(-A)$:**
   Using the scalar multiplication property with $c = -1$ and $n = 3$:
   $$\det(-A) = (-1)^3 \cdot \det A = (-1) \cdot (-4) = 4.$$

## Verification and Consistency Checks
- $\det(-A) = (-1)^3 \det A = -(\det A) = -(-4) = 4$. If $n$ had been even, the sign would not have changed, but for $n=3$ odd, $\det(-A) = -\det A$.
- $\det(A^2) = 16 \ge 0$, which is consistent with the determinant of any real squared matrix being non-negative.
- $\det(2A) = 8 \det A = -32$, consistent with all 3 dimensions scaling by 2 (volume scales by $2^3 = 8$).
