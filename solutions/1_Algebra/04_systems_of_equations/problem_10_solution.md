# Problem 10: A Polynomial Through Three Points

## Problem Statement
Find a polynomial $p(x)=ax^2+bx+c$ whose graph passes through $(0,1)$, $(1,3)$, and $(2,9)$. Reduce the problem to a system of equations and check the result by substituting all three points.

## Theoretical Background and Concepts
Polynomial interpolation seeks a polynomial of degree at most $n-1$ passing through $n$ specified points with distinct $x$-coordinates.
For a quadratic polynomial $p(x) = ax^2 + bx + c$, substituting each point $(x_i, y_i)$ yields a linear equation in the unknown coefficients $a, b, c$:

$$a x_i^2 + b x_i + c = y_i.$$

Given $3$ points with distinct abscissas, this produces a $3\times3$ linear system whose coefficient matrix is a **Vandermonde matrix**:
$$V = \begin{pmatrix}x_1^2 & x_1 & 1 \\ x_2^2 & x_2 & 1 \\ x_3^2 & x_3 & 1\end{pmatrix}.$$
Because all $x_i$ are distinct, the Vandermonde matrix is always non-singular, guaranteeing a unique interpolating polynomial.

## Detailed Step-by-Step Solution
1. **Set up the system of linear equations:**
   Substitute each point into $p(x) = ax^2 + bx + c$:
   - For point $(0, 1)$:
     $$p(0) = a(0)^2 + b(0) + c = 1 \implies c = 1.$$
   - For point $(1, 3)$:
     $$p(1) = a(1)^2 + b(1) + c = 3 \implies a + b + c = 3.$$
   - For point $(2, 9)$:
     $$p(2) = a(2)^2 + b(2) + c = 9 \implies 4a + 2b + c = 9.$$

2. **Substitute $c = 1$ into equations 2 and 3:**
   - Equation 2:
     $$a + b + 1 = 3 \implies a + b = 2.$$
   - Equation 3:
     $$4a + 2b + 1 = 9 \implies 4a + 2b = 8 \implies 2a + b = 4.$$

3. **Solve for $a$ and $b$:**
   Subtract the first equation ($a + b = 2$) from the second ($2a + b = 4$):
   $$(2a + b) - (a + b) = 4 - 2 \implies a = 2.$$
   Now substitute $a = 2$ back to find $b$:
   $$2 + b = 2 \implies b = 0.$$

4. **Write the resulting polynomial:**
   With $a = 2$, $b = 0$, and $c = 1$:
   $$p(x) = 2x^2 + 1.$$

## Verification and Consistency Checks
Check by substituting all three given $x$-values into $p(x) = 2x^2 + 1$:
- For $x = 0$: $p(0) = 2(0)^2 + 1 = 1$, which passes through $(0, 1)$ $\checkmark$
- For $x = 1$: $p(1) = 2(1)^2 + 1 = 2 + 1 = 3$, which passes through $(1, 3)$ $\checkmark$
- For $x = 2$: $p(2) = 2(2)^2 + 1 = 2(4) + 1 = 8 + 1 = 9$, which passes through $(2, 9)$ $\checkmark$

All three points lie on the graph of $p(x) = 2x^2 + 1$, confirming the polynomial is correct and unique.
