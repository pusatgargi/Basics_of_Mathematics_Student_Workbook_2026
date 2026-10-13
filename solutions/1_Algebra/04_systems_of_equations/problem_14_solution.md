# Problem 14: A Small Change in the Right-Hand Side

## Problem Statement
Compare the systems

$$\begin{cases}x+y=2,\\2x-y=1,\\3x=3\end{cases}\qquad \text{and}\qquad \begin{cases}x+y=2,\\2x-y=1,\\3x=3.1.\end{cases}$$

Check the consistency of each system and explain why a small change in one number can change the type of the system.

## Theoretical Background and Concepts
An overdetermined system has more equations than unknowns (here, 3 equations for 2 unknowns).
In $\mathbb{R}^2$, each equation represents a line.
- For an overdetermined system to have a solution, all three lines must intersect at the exact same point.
- A tiny change in a constant term shifts one line parallel to itself. If the lines originally intersected at a single point, shifting one line creates a triangle of intersections, making the system inconsistent.

## Detailed Step-by-Step Solution
1. **Analyze System 1:**
   $$\begin{cases}x + y = 2 \\ 2x - y = 1 \\ 3x = 3\end{cases}$$
   Add the first two equations:
   $$(x + y) + (2x - y) = 2 + 1 \implies 3x = 3 \implies x = 1.$$
   Substitute $x = 1$ into equation 1:
   $$1 + y = 2 \implies y = 1.$$
   The unique intersection of the first two equations is $(x, y) = (1, 1)$.
   Now check equation 3:
   $$3(1) = 3.$$
   This matches the right-hand side $3$.
   Therefore, **System 1 is consistent** and has the **unique solution** $(1, 1)$.

2. **Analyze System 2:**
   $$\begin{cases}x + y = 2 \\ 2x - y = 1 \\ 3x = 3.1\end{cases}$$
   The first two equations are identical to System 1, which again forces:
   $$x = 1,\qquad y = 1.$$
   Now test equation 3 at $(1, 1)$:
   $$3x = 3(1) = 3.$$
   However, equation 3 requires:
   $$3x = 3.1.$$
   This produces the contradiction:
   $$3 = 3.1.$$
   Therefore, no values $(x, y)$ can satisfy all three equations simultaneously.
   **System 2 is inconsistent** and has **no solution**.

3. **Explanation of the change:**
   In System 1, all three lines pass through $(1, 1)$. The third equation is consistent with the first two.
   Changing $3$ to $3.1$ shifts the vertical line from $x = 1$ to $x = 1.0333$, destroying the common intersection. Because there are more equations than unknowns, consistency is fragile: a small perturbation of the right-hand side changes the system from having a unique solution to having no solution.

## Verification and Consistency Checks
- System 1: $1 + 1 = 2$, $2(1) - 1 = 1$, $3(1) = 3$. Consistent!
- System 2: $(1, 1)$ satisfies the first two equations but fails the third ($3 \neq 3.1$). Inconsistent!
