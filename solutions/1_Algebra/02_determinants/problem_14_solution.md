# Problem 14: A System of Equations and the Determinant

## Problem Statement
Consider the system $Ax=b$, where

$$A=\begin{pmatrix}1&2\\k&4\end{pmatrix}.$$

For which values of $k$ does the system have exactly one solution for every $b$? For the remaining value, give an example of a right-hand side $b$ for which the system has infinitely many solutions, and an example for which it has no solution.

## Theoretical Background and Concepts
For a square system $Ax = b$ with $n$ equations and $n$ unknowns:
1. **Unique solution:** If $\det A \neq 0$, the matrix $A$ is invertible, and there is a unique solution given by $x = A^{-1}b$ for every right-hand side vector $b$.
2. **Singular matrix:** If $\det A = 0$, the matrix has linearly dependent rows, and the system is either:
   - **Consistent with infinitely many solutions:** when the augmented matrix $[A \mid b]$ has the same rank as $A$ (i.e., $b$ lies in the column space of $A$).
   - **Inconsistent with no solution:** when $\text{rank}[A \mid b] > \text{rank}(A)$ (i.e., elimination produces an equation of the form $0 = c$ with $c \neq 0$).

## Detailed Step-by-Step Solution
1. **Compute $\det A$:**
   $$\det A = (1)(4) - (2)(k) = 4 - 2k.$$

2. **Condition for a unique solution:**
   The system has a unique solution for every $b$ if and only if $\det A \neq 0$:
   $$4 - 2k \neq 0 \implies 2k \neq 4 \implies k \neq 2.$$
   Thus, for all $k \in \mathbb{R} \setminus \{2\}$, the system has exactly one solution for every $b$.

3. **Analyze the exceptional value $k = 2$:**
   When $k = 2$, the matrix is:
   $$A = \begin{pmatrix}1&2\\2&4\end{pmatrix}.$$
   The system equations are:
   $$\begin{cases}x_1 + 2x_2 = b_1 \\ 2x_1 + 4x_2 = b_2\end{cases}$$
   Notice that the left-hand side of the second equation is twice the left-hand side of the first: $2(x_1 + 2x_2) = 2x_1 + 4x_2$.

   - **Example with infinitely many solutions:**
     Choose $b$ such that $b_2 = 2b_1$, for example $b = \begin{pmatrix}1\\2\end{pmatrix}$.
     The system becomes:
     $$\begin{cases}x_1 + 2x_2 = 1 \\ 2x_1 + 4x_2 = 2\end{cases}$$
     Elimination via $R_2 \leftarrow R_2 - 2R_1$ yields the row $[0\; 0 \mid 0]$, leaving the single equation $x_1 + 2x_2 = 1$. Setting $x_2 = t$, the solutions are:
     $$x = \begin{pmatrix}1 - 2t \\ t\end{pmatrix},\quad t \in \mathbb{R}.$$
     Hence, there are infinitely many solutions.

   - **Example with no solution:**
     Choose $b$ such that $b_2 \neq 2b_1$, for example $b = \begin{pmatrix}1\\3\end{pmatrix}$.
     The system becomes:
     $$\begin{cases}x_1 + 2x_2 = 1 \\ 2x_1 + 4x_2 = 3\end{cases}$$
     Elimination via $R_2 \leftarrow R_2 - 2R_1$ gives:
     $$0 \cdot x_1 + 0 \cdot x_2 = 3 - 2(1) = 1 \implies 0 = 1.$$
     This is a contradiction, so no solution exists.

## Verification and Consistency Checks
- For $k \neq 2$, $\det A = 4 - 2k \neq 0$, giving explicit inverse:
  $$A^{-1} = \frac{1}{4-2k}\begin{pmatrix}4&-2\\-k&1\end{pmatrix}.$$
  Since $A^{-1}$ exists and is unique, $x = A^{-1}b$ uniquely solves the system for any $b$.
- For $k = 2$, $\text{rank}(A) = 1$. The system is consistent if and only if $\text{rank}[A \mid b] = 1$, which requires $b_2 = 2b_1$.
