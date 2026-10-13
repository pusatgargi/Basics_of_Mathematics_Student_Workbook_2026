# Problem 4: Triangular Matrix

## Problem Statement
Without expanding the determinant, compute

$$\det\begin{pmatrix}2&4&1\\0&-3&5\\0&0&7\end{pmatrix}.$$

State the rule for an arbitrary triangular matrix and explain it using this example.

## Theoretical Background and Concepts
- **Upper-triangular matrix:** A square matrix is upper triangular if all entries below its main diagonal are equal to zero ($a_{ij} = 0$ for all $i > j$).
- **Lower-triangular matrix:** A square matrix is lower triangular if all entries above its main diagonal are equal to zero ($a_{ij} = 0$ for all $i < j$).
- **Triangular determinant rule:** For any triangular matrix (upper or lower), the determinant is the product of its main diagonal entries:
  $$\det T = \prod_{i=1}^n t_{ii} = t_{11} t_{22} \cdots t_{nn}.$$

## Detailed Step-by-Step Solution
1. **Identify the structure:**
   Consider the matrix:
   $$A = \begin{pmatrix}2&4&1\\0&-3&5\\0&0&7\end{pmatrix}.$$
   - The entries below the main diagonal are $a_{21} = 0$, $a_{31} = 0$, and $a_{32} = 0$. Because all entries below the main diagonal are zero, $A$ is an **upper-triangular matrix**.
   - The main diagonal entries are $a_{11} = 2$, $a_{22} = -3$, and $a_{33} = 7$.

2. **Apply the triangular determinant rule:**
   Without expanding the determinant, we apply the diagonal product rule directly:
   $$\det A = a_{11} \cdot a_{22} \cdot a_{33} = 2 \cdot (-3) \cdot 7 = -42.$$

3. **Generalization:**
   For a lower-triangular matrix, all entries above the main diagonal are zero, and the exact same rule applies: the determinant is simply the product of the diagonal entries.

## Verification and Consistency Checks
The structure has zeros strictly below the diagonal at positions $(2,1)$, $(3,1)$, and $(3,2)$. The product of the three diagonal elements $2 \times (-3) \times 7 = -42$ gives the determinant directly, fulfilling the requirement not to expand.
