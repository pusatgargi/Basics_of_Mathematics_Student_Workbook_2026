# Problem 7: Using Properties Instead of Recomputing

## Problem Statement
Suppose that for a $3\times3$ matrix, $\det A=-4$. Compute

$$\det(2A),\qquad \det(A^T),\qquad \det(A^2),\qquad \det(-A).$$

Justify each answer using the appropriate property.

## Theoretical Background and Concepts
For any $3\times3$ matrix $A$ and scalars:
1. **Transpose property:** $A^T$ is the matrix with rows and columns exchanged. Transposition preserves the determinant: $\det(A^T) = \det A$.
2. **Power property:** $A^2 = AA$. By the multiplicative property of determinants, $\det(A^2) = \det(AA) = \det A \cdot \det A = (\det A)^2$.
3. **Scalar scaling property:** Multiplying an entire $3\times3$ matrix by a scalar $c$ scales each of its three rows by $c$. Factoring $c$ out of each row contributes three factors of $c$, giving $c^3$:
   $$\det(cA) = c^3 \det A.$$
4. **Negation property:** $-A$ corresponds to scaling by $c = -1$, which gives $\det(-A) = (-1)^3 \det A = -\det A$.

## Detailed Step-by-Step Solution
Given that $A$ is $3\times3$ and $\det A = -4$:

1. **Compute $\det(2A)$:**
   Scaling every row of the $3\times3$ matrix by $2$ contributes three factors of $2$ ($2^3$):
   $$\det(2A) = 2^3 \cdot \det A = 8 \cdot (-4) = -32.$$

2. **Compute $\det(A^T)$:**
   Since $A^T$ exchanges rows and columns without changing the determinant:
   $$\det(A^T) = \det A = -4.$$

3. **Compute $\det(A^2)$:**
   Since $A^2 = AA$:
   $$\det(A^2) = \det A \cdot \det A = (-4) \cdot (-4) = 16.$$

4. **Compute $\det(-A)$:**
   Since $-A = (-1)A$ for a $3\times3$ matrix:
   $$\det(-A) = (-1)^3 \cdot \det A = (-1) \cdot (-4) = 4.$$

## Verification and Consistency Checks
- Notice that $\det(A^2) = 16 > 0$, as expected for the square of any real matrix determinant.
- For $n=3$ odd, $\det(-A) = -\det A = -(-4) = 4$, consistent with scaling all 3 dimensions by $-1$.
- Scaling all three dimensions by $2$ scales volume by $2^3 = 8$, so $\det(2A) = 8(-4) = -32$.
