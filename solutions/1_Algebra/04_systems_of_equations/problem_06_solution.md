# Problem 6: A System with a Parameter — Which Cases Actually Occur?

## Problem Statement
Analyze, depending on the parameter $a$, the system

$$\begin{cases}x+y=2,\\ax+ay=4.\end{cases}$$

Among the three possibilities — exactly one solution, infinitely many solutions, no solution — determine which actually occur and for which values of $a$. If one type cannot occur, explain why.

## Theoretical Background and Concepts
For a $2\times2$ system of linear equations, the coefficient matrix is:
$$A = \begin{pmatrix}1 & 1 \\ a & a\end{pmatrix}.$$
Notice that row 2 is $a$ times row 1: $(a, a) = a(1, 1)$.
The determinant is:
$$\det A = 1(a) - 1(a) = 0 \quad \text{for all } a \in \mathbb{R}.$$
Because $\det A = 0$ for every value of $a$, the coefficient matrix never has full rank ($r < 2$). Consequently, **a unique solution can never occur** for any value of $a$.

## Detailed Step-by-Step Solution
1. **Analyze the equations:**
   - Equation 1: $x + y = 2$.
   - Equation 2: $a(x + y) = 4$.
   Substitute $x + y = 2$ from equation 1 into equation 2:
   $$a(2) = 4 \implies 2a = 4.$$

2. **Case 1: $2a = 4 \iff a = 2$:**
   When $a = 2$, the system becomes:
   $$\begin{cases}x + y = 2 \\ 2x + 2y = 4\end{cases}$$
   The second equation is an exact multiple of the first, leaving only one independent equation in two variables:
   $$x + y = 2.$$
   Setting $x = t$ as a free parameter, $y = 2 - t$, giving:
   $$(x, y) = (t, 2 - t),\quad t \in \mathbb{R}.$$
   **Outcome:** **Infinitely many solutions** occur when **$a = 2$**.

3. **Case 2: $2a \neq 4 \iff a \neq 2$:**
   When $a \neq 2$:
   - If $a = 0$: Equation 2 becomes $0x + 0y = 4 \implies 0 = 4$, which is a contradiction.
   - If $a \neq 0$: Dividing equation 2 by $a$ gives $x + y = \frac{4}{a}$. Since $a \neq 2$, $\frac{4}{a} \neq 2$, giving $2 = x + y = \frac{4}{a}$, which is a contradiction.
   **Outcome:** **No solution** occurs for all **$a \neq 2$**.

4. **Why exactly one solution cannot occur:**
   For a $2\times2$ system to have a unique solution, the lines must have different slopes, requiring $\det A \neq 0$. Here, the coefficients of $x$ and $y$ are identical in both equations ($(1, 1)$ and $(a, a)$), meaning the lines are always parallel (or coincident). Because the rank of the coefficient matrix is at most 1, a unique solution can never occur.

## Verification and Consistency Checks
- When $a = 2$: $(x, y) = (0, 2) \implies x+y=2$ and $2(0)+2(2)=4$, satisfying both equations.
- When $a = 1$: $x+y=2$ and $x+y=4$, which is impossible ($2 \neq 4$).
- When $a = 0$: $0x+0y = 4$, impossible ($0 \neq 4$).
The analysis excludes a unique solution for all $a$ and completely classifies the system.
