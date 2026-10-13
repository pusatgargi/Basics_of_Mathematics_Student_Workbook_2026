# Problem 10: A Polynomial Through Three Points

## Problem Statement
Find a polynomial $p(x)=ax^2+bx+c$ whose graph passes through $(0,1)$, $(1,3)$, and $(2,9)$. Reduce the problem to a system of equations and check the result by substituting all three points.

## Theoretical Background and Concepts
A quadratic polynomial $p(x) = ax^2 + bx + c$ passing through given points $(x_i, y_i)$ requires that $p(x_i) = y_i$ for each point. This sets up a system of linear equations in the unknown coefficients $a, b, c$.

## Detailed Step-by-Step Solution
1. **Model the problem as a linear system:**
   Substitute each point into $p(x) = ax^2 + bx + c$:
   - For $(0, 1)$: $p(0) = a(0)^2 + b(0) + c = 1 \implies c = 1$.
   - For $(1, 3)$: $p(1) = a(1)^2 + b(1) + c = 3 \implies a + b + c = 3$.
   - For $(2, 9)$: $p(2) = a(2)^2 + b(2) + c = 9 \implies 4a + 2b + c = 9$.

2. **Substitute $c = 1$ and simplify:**
   - From equation 2:
     $$a + b + 1 = 3 \implies a + b = 2.$$
   - From equation 3:
     $$4a + 2b + 1 = 9 \implies 4a + 2b = 8.$$
     Dividing this equation by $2$ gives:
     $$2a + b = 4.$$

3. **Solve for $a$ and $b$:**
   Subtract the first equation ($a + b = 2$) from the second ($2a + b = 4$) to eliminate $b$:
   $$(2a + b) - (a + b) = 4 - 2 \implies a = 2.$$
   Now solve for $b$:
   $$b = 2 - a = 2 - 2 = 0.$$

   With $a = 2$, $b = 0$, and $c = 1$, the polynomial is:
   $$p(x) = 2x^2 + 1.$$

4. **Explicit check at all three points:**
   - At $x = 0$: $p(0) = 2(0)^2 + 1 = 0 + 1 = 1$, matching $(0, 1)$ $\checkmark$
   - At $x = 1$: $p(1) = 2(1)^2 + 1 = 2(1) + 1 = 3$, matching $(1, 3)$ $\checkmark$
   - At $x = 2$: $p(2) = 2(2)^2 + 1 = 2(4) + 1 = 9$, matching $(2, 9)$ $\checkmark$

## Verification and Consistency Checks
The polynomial $p(x) = 2x^2 + 1$ satisfies $p(0)=1$, $p(1)=3$, and $p(2)=9$, confirming the unique interpolating quadratic.
