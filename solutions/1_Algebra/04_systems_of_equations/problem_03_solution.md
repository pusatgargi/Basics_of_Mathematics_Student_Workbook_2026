# Problem 3: Inconsistent System

## Problem Statement
Solve or show that the system is inconsistent:

$$\begin{cases}x+2y=3,\\2x+4y=7.\end{cases}$$

Show how the contradiction appears in the matrix after elimination and interpret it in terms of equations.

## Theoretical Background and Concepts
A system of linear equations is inconsistent if no assignment of values to the unknowns can satisfy all equations simultaneously.
In elimination, an inconsistent system reveals itself when a row operation produces a contradiction of the form:
$$[0 \; 0 \; \dots \; 0 \mid c] \quad \text{with } c \neq 0,$$
which translates algebraically to $0 = c$.
Geometrically, two linear equations in two variables represent straight lines in $\mathbb{R}^2$. If the lines are parallel and distinct, they have no intersection point.

## Detailed Step-by-Step Solution
1. **Set up the augmented matrix $[A \mid b]$:**
   $$\left[\begin{array}{cc|c} 1 & 2 & 3 \\ 2 & 4 & 7 \end{array}\right]$$

2. **Perform Gaussian elimination:**
   To eliminate $x$ from the second row, apply $R_2 \leftarrow R_2 - 2R_1$:
   - Left side: $(2 - 2(1),\; 4 - 2(2)) = (0, 0)$
   - Right side: $7 - 2(3) = 7 - 6 = 1$

   The resulting augmented matrix is:
   $$\left[\begin{array}{cc|c} 1 & 2 & 3 \\ 0 & 0 & 1 \end{array}\right]$$

3. **Interpret the contradiction in terms of equations:**
   The second row corresponds to the equation:
   $$0 \cdot x + 0 \cdot y = 1 \implies 0 = 1.$$
   This is a mathematical contradiction (an impossible equality).
   Therefore, no pair of real values $(x, y)$ can satisfy both equations simultaneously. The system has **no solution** (it is inconsistent).

4. **Geometric interpretation:**
   Writing both equations in slope-intercept form:
   - Line 1: $x + 2y = 3 \implies y = -\frac{1}{2}x + \frac{3}{2}$.
   - Line 2: $2x + 4y = 7 \implies y = -\frac{1}{2}x + \frac{7}{4}$.
   Both lines have identical slope $m = -\frac{1}{2}$, but different $y$-intercepts ($\frac{3}{2} \neq \frac{7}{4}$).
   The two lines are parallel and distinct, meaning they never intersect.

## Verification and Consistency Checks
Multiplying equation 1 by 2 yields $2x + 4y = 6$. Comparing this directly with equation 2 ($2x + 4y = 7$) asserts that the same quantity $2x + 4y$ must equal both $6$ and $7$ simultaneously ($6 = 7$). This contradiction confirms that the system is inconsistent.
