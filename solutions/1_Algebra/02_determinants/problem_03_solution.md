# Problem 3: Swapping Two Rows

## Problem Statement
For

$$A=\begin{pmatrix}1&2&0\\0&3&1\\2&1&1\end{pmatrix}$$

compute $\det A$. Then form a matrix $B$ by swapping the first and second rows of $A$.

First predict $\det B$ using a determinant property, and then verify your prediction by calculation.

## Theoretical Background and Concepts
A fundamental property of determinants states that interchanging any two rows (or columns) of a matrix reverses the sign of its determinant:

$$\det(\text{swap}(R_i, R_j)) = -\det A.$$

This alternating multilinear property is a core defining feature of determinants.

## Detailed Step-by-Step Solution
1. **Compute $\det A$:**
   Expand along row 1 of $A$:

   $$\det A = 1 \cdot \det\begin{pmatrix}3&1\\1&1\end{pmatrix} - 2 \cdot \det\begin{pmatrix}0&1\\2&1\end{pmatrix} + 0 \cdot \det\begin{pmatrix}0&3\\2&1\end{pmatrix}$$
   $$\det A = 1 \cdot (3 - 1) - 2 \cdot (0 - 2) + 0 = 1(2) - 2(-2) = 2 + 4 = 6.$$

2. **Form matrix $B$ and predict $\det B$:**
   Swapping row 1 and row 2 of $A$:

   $$B = \begin{pmatrix}0&3&1\\1&2&0\\2&1&1\end{pmatrix}.$$

   By the row interchange property:
   $$\det B = -\det A = -6.$$

3. **Verify by direct calculation of $\det B$:**
   Expand along row 1 of $B$:

   $$\det B = 0 \cdot C_{11} - 3 \cdot \det\begin{pmatrix}1&0\\2&1\end{pmatrix} + 1 \cdot \det\begin{pmatrix}1&2\\2&1\end{pmatrix}$$
   $$\det B = -3(1 - 0) + 1(1 - 4) = -3(1) + 1(-3) = -3 - 3 = -6.$$

## Verification and Consistency Checks
The direct calculation gives $\det B = -6$, which precisely matches the theoretical prediction $-\det A = -(6) = -6$. This confirms that a single row swap negates the determinant.
