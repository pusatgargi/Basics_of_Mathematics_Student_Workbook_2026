# Problem 13: Determinant by Elimination

## Problem Statement
Compute the determinant

$$A=\begin{pmatrix}1&2&3\\2&5&7\\1&0&2\end{pmatrix}$$

using elimination. Record the effect of every row operation used on the value of the determinant.

## Theoretical Background and Concepts
Gaussian elimination transforms any square matrix into an upper triangular matrix $U$ using elementary row operations.
Tracking how these operations affect the determinant:
- **Row replacement ($R_i \leftarrow R_i + cR_j$):** Determinant is multiplied by $1$ (unchanged).
- **Row swap ($R_i \leftrightarrow R_j$):** Determinant is multiplied by $-1$.
- **Row scaling ($R_i \leftarrow cR_i$):** Determinant is multiplied by $c$.

Once reduced to upper triangular form $U$, its determinant is simply the product of its diagonal entries:
$$\det U = \prod_{i=1}^n u_{ii}.$$
The original determinant $\det A$ is then obtained by accounting for any sign changes or scaling factors accumulated during elimination.

## Detailed Step-by-Step Solution
Start with matrix $A$:
$$A = \begin{pmatrix}1&2&3\\2&5&7\\1&0&2\end{pmatrix}.$$

1. **Step 1: Eliminate below $a_{11}$ in Column 1:**
   - Operation 1: $R_2 \leftarrow R_2 - 2R_1$.
     - Effect on determinant: **Multiplied by 1** (determinant unchanged).
     - Calculation: $R_2 = (2 - 2(1),\; 5 - 2(2),\; 7 - 2(3)) = (0, 1, 1)$.
   - Operation 2: $R_3 \leftarrow R_3 - R_1$.
     - Effect on determinant: **Multiplied by 1** (determinant unchanged).
     - Calculation: $R_3 = (1 - 1,\; 0 - 2,\; 2 - 3) = (0, -2, -1)$.

   Current matrix:
   $$A_1 = \begin{pmatrix}1&2&3\\0&1&1\\0&-2&-1\end{pmatrix},\qquad \det A = \det A_1.$$

2. **Step 2: Eliminate below $a_{22}$ in Column 2:**
   - Operation 3: $R_3 \leftarrow R_3 + 2R_2$.
     - Effect on determinant: **Multiplied by 1** (determinant unchanged).
     - Calculation: $R_3 = (0 + 2(0),\; -2 + 2(1),\; -1 + 2(1)) = (0, 0, 1)$.

   Current matrix (upper triangular):
   $$U = \begin{pmatrix}1&2&3\\0&1&1\\0&0&1\end{pmatrix},\qquad \det A = \det U.$$

3. **Step 3: Calculate $\det U$:**
   Since all row operations performed were row replacements, no scaling or row-swapping factors were introduced:
   $$\det A = \det U = 1 \cdot 1 \cdot 1 = 1.$$

## Verification and Consistency Checks
Verification via Sarrus' rule on the original matrix $A$:
- Downward diagonals:
  $$(1)(5)(2) + (2)(7)(1) + (3)(2)(0) = 10 + 14 + 0 = 24.$$
- Upward diagonals:
  $$(3)(5)(1) + (1)(7)(0) + (2)(2)(2) = 15 + 0 + 8 = 23.$$
- Determinant:
  $$\det A = 24 - 23 = 1.$$
Both Gaussian elimination and Sarrus' rule give $\det A = 1$.
