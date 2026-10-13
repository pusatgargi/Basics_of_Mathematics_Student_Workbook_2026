# Problem 9: A System from a Sum Condition

## Problem Statement
Find numbers $x,y$ satisfying

$$x+y=10,\qquad 2x+5y=32.$$

Solve the system and explain geometrically why the solution is unique.

## Theoretical Background and Concepts
Each linear equation in two variables represents a straight line in the Cartesian plane $\mathbb{R}^2$.
A solution $(x, y)$ corresponds to an intersection point of the two lines.
The solution is unique if and only if the lines have different slopes, which means they are not parallel and intersect at exactly one point.

## Detailed Step-by-Step Solution
1. **Solve by substitution or elimination:**
   $$\begin{cases}x + y = 10 \\ 2x + 5y = 32\end{cases}$$
   From equation 1: $x = 10 - y$.
   Substitute into equation 2:
   $$2(10 - y) + 5y = 32$$
   $$20 - 2y + 5y = 32$$
   $$20 + 3y = 32$$
   $$3y = 12 \implies y = 4.$$
   Now find $x$:
   $$x = 10 - 4 = 6.$$
   Thus, $(x, y) = (6, 4)$.

2. **Geometric interpretation and uniqueness:**
   Rewrite both equations in slope-intercept form ($y = mx + b$):
   - Equation 1:
     $$y = 10 - x \implies \text{slope } m_1 = -1.$$
   - Equation 2:
     $$5y = 32 - 2x \implies y = \frac{32}{5} - \frac{2}{5}x \implies \text{slope } m_2 = -\frac{2}{5} = -0.4.$$

   Because the slopes are different ($m_1 = -1 \neq -0.4 = m_2$), the lines are **not parallel**.
   In the Euclidean plane $\mathbb{R}^2$, two non-parallel lines must intersect at **exactly one unique point**.
   Therefore, $(6, 4)$ is the unique solution of the system.

## Verification and Consistency Checks
Substitute $(x, y) = (6, 4)$ into both equations:
- $6 + 4 = 10$ (Verified $\checkmark$)
- $2(6) + 5(4) = 12 + 20 = 32$ (Verified $\checkmark$)
The unique intersection point $(6, 4)$ satisfies both conditions.
