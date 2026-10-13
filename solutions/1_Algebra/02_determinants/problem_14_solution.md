# Problem 14: A System of Equations and the Determinant

## Problem Statement
Consider the system $Ax=b$, where

$$A=\begin{pmatrix}1&2\\k&4\end{pmatrix}.$$

For which values of $k$ does the system have exactly one solution for every $b$? For the remaining value, give an example of a right-hand side $b$ for which the system has infinitely many solutions, and an example for which it has no solution.

## Theoretical Background and Concepts
For a square system of linear equations $Ax = b$:
- If $\det A \neq 0$, the matrix $A$ is invertible with inverse $A^{-1}$, so there is a unique solution given by $x = A^{-1}b$ for every right-hand side vector $b$.
- If $\det A = 0$, the matrix is singular, and the system either has infinitely many solutions (if consistent) or no solution (if contradictory).

## Detailed Step-by-Step Solution
1. **Compute $\det A$:**
   $$\det A = 1 \cdot 4 - 2k = 4 - 2k.$$

2. **Condition for exactly one solution:**
   A nonzero determinant gives an inverse $A^{-1}$, guaranteeing one solution $x = A^{-1}b$ for every $b$:
   $$4 - 2k \neq 0 \implies 2k \neq 4 \implies k \neq 2.$$
   Thus, for all $k \neq 2$, the system has exactly one solution for every $b$.

3. **Analysis of the exceptional value $k = 2$:**
   At $k = 2$, the actual equations of the system are:
   $$\begin{cases}x_1 + 2x_2 = b_1 \\ 2x_1 + 4x_2 = b_2\end{cases}$$
   Notice that the original left-hand sides differ by a factor of 2: the left-hand side of the second equation is twice the left-hand side of the first ($2x_1 + 4x_2 = 2(x_1 + 2x_2)$).

   - **Example with infinitely many solutions:**
     Choose $b = \begin{pmatrix}1\\2\end{pmatrix}$. The system becomes:
     $$\begin{cases}x_1 + 2x_2 = 1 \\ 2x_1 + 4x_2 = 2\end{cases}$$
     Here, the second equation is twice the first, leaving only one independent equation in two unknowns ($x_1 + 2x_2 = 1$). One unknown can be chosen freely (e.g. $x_2 = t$, so $x_1 = 1 - 2t$), giving **infinitely many solutions**.

   - **Example with no solution:**
     Choose $b = \begin{pmatrix}1\\3\end{pmatrix}$. The system becomes:
     $$\begin{cases}x_1 + 2x_2 = 1 \\ 2x_1 + 4x_2 = 3\end{cases}$$
     Doubling the first equation $x_1 + 2x_2 = 1$ gives $2x_1 + 4x_2 = 2$, which directly contradicts the second equation $2x_1 + 4x_2 = 3$ ($2 = 3$). Therefore, there is **no solution**.

## Verification and Consistency Checks
- For $k \neq 2$, $\det A = 4 - 2k \neq 0$, so $A^{-1} = \frac{1}{4-2k}\begin{pmatrix}4&-2\\-k&1\end{pmatrix}$ exists, confirming a unique solution for every $b$.
- For $k = 2$, the system is consistent if and only if $b_2 = 2b_1$. The example $b = (1, 2)^T$ satisfies $b_2 = 2b_1$ (infinite solutions), while $b = (1, 3)^T$ violates it (no solution).
