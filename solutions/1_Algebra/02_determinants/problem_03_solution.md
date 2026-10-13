# Problem 3: Swapping Two Rows

## Problem Statement
For

$$A=\begin{pmatrix}1&2&0\\0&3&1\\2&1&1\end{pmatrix}$$

compute $\det A$. Then form a matrix $B$ by swapping the first and second rows of $A$.

First predict $\det B$ using a determinant property, and then verify your prediction by calculation.

## Theoretical Background and Concepts
- **First-row expansion:** Expanding a $3\times3$ determinant along its first row uses alternating signs $+,-,+$. Each term is the product of the row entry and the $2\times2$ minor obtained by deleting that entry's row and column. A zero entry in the first row contributes zero, which simplifies the computation.
- **Row-swap property:** Interchanging any two rows of a matrix reverses the sign of its determinant:
  $$\det(\text{swap}(R_i, R_j)) = -\det A.$$

## Detailed Step-by-Step Solution
1. **Compute $\det A$ using first-row expansion:**
   For $A = \begin{pmatrix}1&2&0\\0&3&1\\2&1&1\end{pmatrix}$:
   - Entry $a_{11} = 1$ (sign $+$): Deleting row 1 and column 1 leaves the minor $\begin{pmatrix}3&1\\1&1\end{pmatrix}$, with determinant $(3)(1) - (1)(1) = 2$.
   - Entry $a_{12} = 2$ (sign $-$): Deleting row 1 and column 2 leaves the minor $\begin{pmatrix}0&1\\2&1\end{pmatrix}$, with determinant $(0)(1) - (1)(2) = -2$.
   - Entry $a_{13} = 0$ (sign $+$): Contributes zero because $0 \cdot \text{minor} = 0$.

   Combining these with their respective signs:
   $$\det A = +1(2) - 2(-2) + 0 = 2 + 4 = 6.$$

2. **Form matrix $B$ and predict $\det B$:**
   Swapping row 1 and row 2 of $A$ gives:
   $$B = \begin{pmatrix}0&3&1\\1&2&0\\2&1&1\end{pmatrix}.$$
   By the row-swap property, swapping two rows reverses the sign of the determinant:
   $$\det B = -\det A = -6.$$

3. **Verify by calculation of $\det B$:**
   Expand along row 1 of $B$:
   - Entry $b_{11} = 0$: Contributes zero.
   - Entry $b_{12} = 3$ (sign $-$): Deleting row 1 and column 2 leaves minor $\begin{pmatrix}1&0\\2&1\end{pmatrix}$, with determinant $(1)(1) - (0)(2) = 1$.
   - Entry $b_{13} = 1$ (sign $+$): Deleting row 1 and column 3 leaves minor $\begin{pmatrix}1&2\\2&1\end{pmatrix}$, with determinant $(1)(1) - (2)(2) = 1 - 4 = -3$.

   Evaluating:
   $$\det B = -3(1) + 1(-3) = -3 - 3 = -6.$$

## Verification and Consistency Checks
The calculated value $\det B = -6$ matches the predicted sign reversal $-\det A = -6$, confirming that swapping two rows negates the determinant.
