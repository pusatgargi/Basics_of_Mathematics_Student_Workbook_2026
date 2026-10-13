# Problem 4: Triangular Matrix

## Problem Statement
Without expanding the determinant, compute

$$\det\begin{pmatrix}2&4&1\\0&-3&5\\0&0&7\end{pmatrix}.$$

State the rule for an arbitrary triangular matrix and explain it using this example.

## Theoretical Background and Concepts
An upper triangular matrix is a square matrix whose entries below the main diagonal are all zero ($a_{ij} = 0$ for all $i > j$).
Similarly, a lower triangular matrix has all zeros above the main diagonal ($a_{ij} = 0$ for all $i < j$).

**General Rule:**
The determinant of any triangular (upper or lower) or diagonal matrix is the product of its main diagonal entries:

$$\det T = \prod_{i=1}^n t_{ii} = t_{11} t_{22} \cdots t_{nn}.$$

This property holds because expanding repeatedly along the first column (for an upper triangular matrix) continually eliminates all off-diagonal terms, leaving only the product of the diagonal pivots.

## Detailed Step-by-Step Solution
1. **Identify the structure:**
   The matrix
   $$T = \begin{pmatrix}2&4&1\\0&-3&5\\0&0&7\end{pmatrix}$$
   is upper triangular because all entries below the diagonal ($t_{21}=0, t_{31}=0, t_{32}=0$) are zero.

2. **Apply the diagonal product rule:**
   The diagonal entries are $t_{11} = 2$, $t_{22} = -3$, and $t_{33} = 7$.
   $$\det T = 2 \cdot (-3) \cdot 7 = -42.$$

3. **Explanation using cofactor expansion:**
   Expanding along the first column:
   $$\det T = 2 \cdot \det\begin{pmatrix}-3&5\\0&7\end{pmatrix} - 0 + 0.$$
   The remaining $2\times2$ matrix is also triangular, with determinant $(-3)(7) - 0 = -21$.
   Therefore:
   $$\det T = 2 \cdot [(-3) \cdot 7] = -42.$$

## Verification and Consistency Checks
- Sarrus' rule verification:
  Downward: $(2)(-3)(7) + 0 + 0 = -42$.
  Upward: $0 + 0 + 0 = 0$.
  Determinant: $-42 - 0 = -42$.
- The result confirms the general theorem: triangular matrices have determinants equal to the product of their diagonal elements.
