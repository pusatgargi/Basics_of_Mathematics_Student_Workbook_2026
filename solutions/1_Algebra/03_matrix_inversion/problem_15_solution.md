# Problem 15: Two Methods for Solving the Same System

## Problem Statement
For

$$A=\begin{pmatrix}2&1\\1&3\end{pmatrix},\qquad b=\begin{pmatrix}7\\8\end{pmatrix}$$

solve $Ax=b$ in two ways:

1. using $A^{-1}b$,
2. using Gaussian elimination.

Compare both solutions, the number of essential steps, and state which method was simpler in this example.

## Theoretical Background and Concepts
A linear system $Ax = b$ with an invertible coefficient matrix can be solved using:
- **Matrix inversion:** Compute $A^{-1}$ explicitly and evaluate the matrix-vector product $x = A^{-1}b$.
- **Gaussian elimination:** Row-reduce the augmented matrix $[A \mid b]$ to row-echelon form and solve via back substitution.

## Detailed Step-by-Step Solution
Given:
$$A=\begin{pmatrix}2&1\\1&3\end{pmatrix},\qquad b=\begin{pmatrix}7\\8\end{pmatrix}.$$

1. **Method 1: Using $A^{-1}b$:**
   - For an invertible $2\times 2$ matrix $M = \begin{pmatrix}a & b \\ c & d\end{pmatrix}$ with $\det M = ad - bc \neq 0$, the inverse formula is:
     $$M^{-1} = \frac{1}{\det M}\begin{pmatrix}d & -b \\ -c & a\end{pmatrix}.$$
   - Compute the determinant of $A = \begin{pmatrix}2 & 1 \\ 1 & 3\end{pmatrix}$:
     $$\det A = (2)(3) - (1)(1) = 6 - 1 = 5 \neq 0.$$
   - Form the adjugate matrix by exchanging the diagonal entries ($2$ and $3$) and negating the off-diagonal entries ($1$ becomes $-1$ in both positions):
     $$\operatorname{adj}(A) = \begin{pmatrix}3 & -1 \\ -1 & 2\end{pmatrix}.$$
   - Dividing by $\det A = 5$ yields:
     $$A^{-1} = \frac{1}{5}\begin{pmatrix}3 & -1 \\ -1 & 2\end{pmatrix}.$$
   - Evaluate $x = A^{-1}b$:
     $$x = \frac{1}{5}\begin{pmatrix}3 & -1 \\ -1 & 2\end{pmatrix}\begin{pmatrix}7\\8\end{pmatrix}.$$
     The vector components are:
     $$x_1 = \frac{3(7) - 1(8)}{5} = \frac{21 - 8}{5} = \frac{13}{5}.$$
     $$x_2 = \frac{-1(7) + 2(8)}{5} = \frac{-7 + 16}{5} = \frac{9}{5}.$$

     Thus, $x = \begin{pmatrix}\frac{13}{5} \\ \frac{9}{5}\end{pmatrix}$.

2. **Method 2: Using Gaussian Elimination:**
   - Augmented matrix:
     $$\left[\begin{array}{cc|c} 2 & 1 & 7 \\ 1 & 3 & 8 \end{array}\right]$$
   - Swap rows ($R_1 \leftrightarrow R_2$) to obtain a leading pivot of $1$:
     $$\left[\begin{array}{cc|c} 1 & 3 & 8 \\ 2 & 1 & 7 \end{array}\right]$$
   - Eliminate the first unknown from row 2 via $R_2 \leftarrow R_2 - 2R_1$:
     $$R_2 = (2 - 2(1),\; 1 - 2(3) \mid 7 - 2(8)) = (0, -5 \mid -9).$$
     Intervening matrix in upper-triangular echelon form:
     $$\left[\begin{array}{cc|c} 1 & 3 & 8 \\ 0 & -5 & -9 \end{array}\right]$$
   - Back substitution:
     From row 2: $-5x_2 = -9 \implies x_2 = \frac{9}{5}$.
     From row 1: $x_1 + 3\left(\frac{9}{5}\right) = 8 \implies x_1 = 8 - \frac{27}{5} = \frac{13}{5}$.

     Thus, $x = \begin{pmatrix}\frac{13}{5} \\ \frac{9}{5}\end{pmatrix}$.

3. **Check by substituting into original equations:**
   - Equation 1: $2\left(\frac{13}{5}\right) + \frac{9}{5} = \frac{26 + 9}{5} = \frac{35}{5} = 7$.
   - Equation 2: $\frac{13}{5} + 3\left(\frac{9}{5}\right) = \frac{13 + 27}{5} = \frac{40}{5} = 8$.

4. **Comparison of Essential Steps:**
   Counting the essential method stages:
   - **Method 1 (Matrix Inversion):** 3 stages (compute determinant, assemble adjugate inverse matrix, perform matrix-vector multiplication).
   - **Method 2 (Elimination):** 3 stages (pivot swap, row elimination, back substitution).
   - **Which method is preferred:** For a single right-hand side vector $b$, Gaussian elimination is preferred because it solves this one right-hand side directly without forming the entire inverse matrix $A^{-1}$. Forming the full inverse requires extra computational work to determine all entries of $A^{-1}$, whereas solving directly for $x$ via elimination only processes the single column vector $b$.

## Verification and Consistency Checks
Both methods produce the identical unique solution $(x_1, x_2) = (13/5, 9/5) = (2.6, 1.8)$. Substituting into both original equations confirms the solution.
