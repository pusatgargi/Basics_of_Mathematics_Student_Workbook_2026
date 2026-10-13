# Problem 3: Inconsistent System

## Problem Statement
Solve or show that the system is inconsistent:

$$\begin{cases}x+2y=3,\\2x+4y=7.\end{cases}$$

Show how the contradiction appears in the matrix after elimination and interpret it in terms of equations.

## Theoretical Background and Concepts
A system of linear equations is called **inconsistent** if it has no solutions.
In Gaussian elimination, a contradiction appears when an elementary row operation transforms a row into the form:

$$[0 \; 0 \; \dots \; 0 \mid c] \quad \text{where } c \neq 0.$$

This corresponds to the algebraic equation:
$$0 \cdot x_1 + 0 \cdot x_2 + \dots + 0 \cdot x_n = c,$$
which asserts $0 = c$. Since $c \neq 0$, this is impossible for any choice of variables.
By the Rouché–Capelli theorem, a system $Ax = b$ is consistent if and only if $\text{rank}(A) = \text{rank}[A \mid b]$. When $\text{rank}(A) < \text{rank}[A \mid b]$, the system is inconsistent.

## Detailed Step-by-Step Solution
1. **Set up the augmented matrix $[A \mid b]$:**
   $$\left[\begin{array}{cc|c} 1 & 2 & 3 \\ 2 & 4 & 7 \end{array}\right]$$

2. **Perform elimination on the second row:**
   Apply $R_2 \leftarrow R_2 - 2R_1$:
   - Left side: $R_2 = (2 - 2(1),\; 4 - 2(2)) = (0, 0)$
   - Right side: $7 - 2(3) = 7 - 6 = 1$

   Augmented matrix after elimination:
   $$\left[\begin{array}{cc|c} 1 & 2 & 3 \\ 0 & 0 & 1 \end{array}\right]$$

3. **Interpret the contradiction in terms of equations:**
   The second row translates to:
   $$0 \cdot x + 0 \cdot y = 1 \implies 0 = 1.$$
   This is an obvious mathematical contradiction (false statement).
   Therefore, no pair of real numbers $(x, y)$ can satisfy both equations simultaneously. The system has **no solution** (it is inconsistent).

4. **Geometric interpretation:**
   Rewrite both equations in slope-intercept form:
   - Equation 1: $x + 2y = 3 \implies y = -\frac{1}{2}x + \frac{3}{2}$.
   - Equation 2: $2x + 4y = 7 \implies y = -\frac{1}{2}x + \frac{7}{4}$.
   Both lines have identical slope $m = -\frac{1}{2}$ but different $y$-intercepts ($\frac{3}{2} \neq \frac{7}{4}$).
   The two lines are parallel and distinct, meaning they never intersect.

## Verification and Consistency Checks
- Rank comparison:
  $$\text{rank}(A) = 1,\qquad \text{rank}[A \mid b] = 2.$$
  Since $\text{rank}(A) \neq \text{rank}[A \mid b]$, the system has no solution.
- Doubling equation 1 gives $2x + 4y = 6$. Comparing this with equation 2 ($2x + 4y = 7$) directly reveals $6 = 7$, confirming inconsistency.
