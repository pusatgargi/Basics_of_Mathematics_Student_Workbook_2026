# Problem 15: Classifying Three Systems

## Problem Statement
For each of the following systems, perform only as much elimination as necessary to recognize its type:

1. $\begin{cases}x+y=2,\\x-y=0,\end{cases}$
2. $\begin{cases}x+y=2,\\2x+2y=4,\end{cases}$
3. $\begin{cases}x+y=2,\\2x+2y=5.\end{cases}$

For each, justify the classification: one solution, infinitely many solutions, or no solution.

## Theoretical Background and Concepts
A system of two linear equations in two unknowns belongs to one of three types:
1. **Exactly one solution:** The equations are independent and consistent (lines intersect at a single point).
2. **Infinitely many solutions:** One equation is a multiple of the other (lines are coincident, leaving a free choice).
3. **No solution:** The equations require the same linear combination of variables to equal two different values (lines are parallel and distinct, producing a contradiction).

## Detailed Step-by-Step Solution
1. **System 1:**
   $$\begin{cases}x + y = 2 \\ x - y = 0\end{cases}$$
   Adding the two equations:
   $$(x + y) + (x - y) = 2 + 0 \implies 2x = 2 \implies x = 1.$$
   Then $y = x = 1$.
   Addition fixes the pair $(x, y) = (1, 1)$ uniquely.
   **Classification:** **Exactly one solution**.

2. **System 2:**
   $$\begin{cases}x + y = 2 \\ 2x + 2y = 4\end{cases}$$
   The second equation is an exact duplication (twice the first equation: $2(x+y)=4$).
   Elimination gives $0 = 0$, leaving only one independent equation $x + y = 2$ in two unknowns. This leaves a free choice (e.g. $y = t$, $x = 2 - t$).
   **Classification:** **Infinitely many solutions**.

3. **System 3:**
   $$\begin{cases}x + y = 2 \\ 2x + 2y = 5\end{cases}$$
   Dividing the second equation by $2$ gives $x + y = 2.5$.
   Comparing with the first equation requires $x + y = 2$ and $x + y = 2.5$.
   These incompatible values of $x + y$ yield the contradiction $2 = 2.5$.
   **Classification:** **No solution**.

## Verification and Consistency Checks
- System 1 represents perpendicular lines intersecting at $(1, 1)$. Unique solution verified.
- System 2 represents identical lines. Infinitely many solutions verified.
- System 3 represents parallel distinct lines that never intersect. No solution verified.
