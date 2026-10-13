# Problem 15: Classifying Three Systems

## Problem Statement
For each of the following systems, perform only as much elimination as necessary to recognize its type:

1. $\begin{cases}x+y=2,\\x-y=0,\end{cases}$
2. $\begin{cases}x+y=2,\\2x+2y=4,\end{cases}$
3. $\begin{cases}x+y=2,\\2x+2y=5.\end{cases}$

For each, justify the classification: one solution, infinitely many solutions, or no solution.

## Theoretical Background and Concepts
By the Rouché–Capelli theorem, the structure of the augmented matrix $[A \mid b]$ in row echelon form immediately classifies a linear system:
1. **Exactly one solution:** $\text{rank}(A) = \text{rank}[A \mid b] = n$ (full rank, no zero rows on the left, each column has a pivot).
2. **Infinitely many solutions:** $\text{rank}(A) = \text{rank}[A \mid b] = r < n$ (consistent, at least one free variable, row of zeros $[0 \; 0 \mid 0]$ appears).
3. **No solution:** $\text{rank}(A) < \text{rank}[A \mid b]$ (a contradiction row $[0 \; 0 \mid c]$ with $c \neq 0$ appears).

## Detailed Step-by-Step Solution
1. **System 1:**
   $$\begin{cases}x+y=2\\x-y=0\end{cases}$$
   - Augmented matrix:
     $$\left[\begin{array}{cc|c} 1 & 1 & 2 \\ 1 & -1 & 0 \end{array}\right]$$
   - Elimination ($R_2 \leftarrow R_2 - R_1$):
     $$\left[\begin{array}{cc|c} 1 & 1 & 2 \\ 0 & -2 & -2 \end{array}\right]$$
   - **Structure:**
     There are two nonzero pivot entries ($1$ in row 1, $-2$ in row 2). Both columns have pivots, and there is no contradiction.
     $\text{rank}(A) = \text{rank}[A \mid b] = 2 = n$.
   - **Classification:** **Exactly one solution** (unique solution $(x, y) = (1, 1)$).

2. **System 2:**
   $$\begin{cases}x+y=2\\2x+2y=4\end{cases}$$
   - Augmented matrix:
     $$\left[\begin{array}{cc|c} 1 & 1 & 2 \\ 2 & 2 & 4 \end{array}\right]$$
   - Elimination ($R_2 \leftarrow R_2 - 2R_1$):
     $$\left[\begin{array}{cc|c} 1 & 1 & 2 \\ 0 & 0 & 0 \end{array}\right]$$
   - **Structure:**
     Row 2 is completely zero ($[0 \; 0 \mid 0]$), representing $0 = 0$ (no contradiction).
     $\text{rank}(A) = \text{rank}[A \mid b] = 1 < 2$. Variable $y$ is free.
   - **Classification:** **Infinitely many solutions** (described by $x = 2 - y$).

3. **System 3:**
   $$\begin{cases}x+y=2\\2x+2y=5\end{cases}$$
   - Augmented matrix:
     $$\left[\begin{array}{cc|c} 1 & 1 & 2 \\ 2 & 2 & 5 \end{array}\right]$$
   - Elimination ($R_2 \leftarrow R_2 - 2R_1$):
     $$\left[\begin{array}{cc|c} 1 & 1 & 2 \\ 0 & 0 & 1 \end{array}\right]$$
   - **Structure:**
     Row 2 has zeros on the left and a nonzero constant on the right ($[0 \; 0 \mid 1]$), which asserts $0 = 1$.
     $\text{rank}(A) = 1 < 2 = \text{rank}[A \mid b]$.
   - **Classification:** **No solution** (inconsistent).

## Verification and Consistency Checks
- Geometric check:
  - System 1 lines have slopes $-1$ and $+1$ (perpendicular lines intersecting at $(1, 1)$). One solution.
  - System 2 lines are identical ($2x+2y=4 \iff x+y=2$). Infinitely many solutions.
  - System 3 lines are parallel and distinct ($x+y=2$ and $x+y=2.5$). No solution.
The classifications are completely confirmed geometrically and algebraically.
