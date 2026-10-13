# Problem 9: A System from a Sum Condition

## Problem Statement
Find numbers $x,y$ satisfying

$$x+y=10,\qquad 2x+5y=32.$$

Solve the system and explain geometrically why the solution is unique.

## Theoretical Background and Concepts
A system of two linear equations in two unknowns represents two lines in the Cartesian plane $\mathbb{R}^2$:
- Line 1: $L_1: a_1 x + b_1 y = c_1$
- Line 2: $L_2: a_2 x + b_2 y = c_2$

A point $(x, y)$ solves the system if and only if it lies on both lines simultaneously (their intersection point).
- The solution is **unique** if and only if the lines have **different slopes** (i.e., their normal vectors $(a_1, b_1)$ and $(a_2, b_2)$ are not collinear).
- In matrix terms, the normal vectors are linearly independent, so the coefficient matrix has non-zero determinant $\det A \neq 0$.

## Detailed Step-by-Step Solution
1. **Solve the system algebraically:**
   $$\begin{cases}x + y = 10 \\ 2x + 5y = 32\end{cases}$$
   From equation 1, isolate $x$:
   $$x = 10 - y.$$
   Substitute this into equation 2:
   $$2(10 - y) + 5y = 32$$
   $$20 - 2y + 5y = 32$$
   $$20 + 3y = 32$$
   $$3y = 12 \implies y = 4.$$
   Now find $x$:
   $$x = 10 - 4 = 6.$$

   The solution is:
   $$(x, y) = (6, 4).$$

2. **Geometric interpretation and uniqueness:**
   Express each equation in slope-intercept form ($y = mx + b$):
   - Line 1 ($x + y = 10$):
     $$y = -x + 10 \implies \text{slope } m_1 = -1.$$
   - Line 2 ($2x + 5y = 32$):
     $$5y = -2x + 32 \implies y = -\frac{2}{5}x + \frac{32}{5} \implies \text{slope } m_2 = -\frac{2}{5} = -0.4.$$

   Because the slopes are different ($m_1 = -1 \neq -0.4 = m_2$):
   The two lines are **not parallel**. In the Euclidean plane $\mathbb{R}^2$, two non-parallel straight lines must intersect at **exactly one point**.
   Therefore, the system has a unique geometric intersection point at $(6, 4)$.

## Verification and Consistency Checks
- Substitute $(6, 4)$ into the original equations:
  - $6 + 4 = 10$ (Verified $\checkmark$)
  - $2(6) + 5(4) = 12 + 20 = 32$ (Verified $\checkmark$)
- Determinant check:
  $$A = \begin{pmatrix}1 & 1 \\ 2 & 5\end{pmatrix},\qquad \det A = (1)(5) - (1)(2) = 5 - 2 = 3.$$
  Since $\det A = 3 \neq 0$, the matrix is invertible, algebraically guaranteeing uniqueness of the solution.
