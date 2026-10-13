# Problem 12: Homogeneous System

## Problem Statement
Solve

$$\begin{cases}x+2y-z=0,\\2x+4y-2z=0,\\x-y+2z=0.\end{cases}$$

Give all solutions in parametric form and explain why $(0,0,0)$ always satisfies a homogeneous system.

## Theoretical Background and Concepts
A system is homogeneous if all right-hand sides are zero: $Ax = 0$.
A homogeneous system has zero on every right-hand side. Setting every unknown to zero makes every linear left-hand side zero too ($a_1(0) + \dots + a_n(0) = 0$), so every equation is automatically satisfied. Thus, the zero vector $(0, 0, 0)$ is always a solution of any homogeneous system.

## Detailed Step-by-Step Solution
1. **Set up the system:**
   $$\begin{cases}x + 2y - z = 0 \\ 2x + 4y - 2z = 0 \\ x - y + 2z = 0\end{cases}$$
   Notice that equation 2 is twice equation 1 ($2(x+2y-z) = 2x+4y-2z = 0$). It is redundant and can be omitted.

2. **Elimination on the remaining two equations:**
   $$\begin{cases}x + 2y - z = 0 \\ x - y + 2z = 0\end{cases}$$
   Subtract equation 2 from equation 1:
   $$(x + 2y - z) - (x - y + 2z) = 0$$
   $$3y - 3z = 0 \implies y = z.$$
   Substitute $y = z$ into equation 1:
   $$x + 2z - z = 0 \implies x + z = 0 \implies x = -z.$$

3. **Parametric solution:**
   Let $z = t \in \mathbb{R}$ be the free parameter.
   Then $x = -t$ and $y = t$.
   In vector form:
   $$\begin{pmatrix}x\\y\\z\end{pmatrix} = \begin{pmatrix}-t \\ t \\ t\end{pmatrix} = t\begin{pmatrix}-1\\1\\1\end{pmatrix},\quad t \in \mathbb{R}.$$
   The system has **infinitely many solutions**.

4. **Why $(0,0,0)$ always satisfies a homogeneous system:**
   In any linear equation of the form $c_1 x_1 + c_2 x_2 + \dots + c_n x_n = 0$, evaluating at $x_1 = x_2 = \dots = x_n = 0$ gives:
   $$c_1(0) + c_2(0) + \dots + c_n(0) = 0 + 0 + \dots + 0 = 0.$$
   Because every right-hand side is zero, setting all variables to zero trivially satisfies every equation simultaneously. (In our parametric family, setting $t = 0$ confirms this fact).

## Verification and Consistency Checks
Substitute $(-t, t, t)$ into the three equations:
- Eq 1: $-t + 2t - t = 0$ $\checkmark$
- Eq 2: $2(-t) + 4t - 2t = 0$ $\checkmark$
- Eq 3: $-t - t + 2t = 0$ $\checkmark$
All equations hold identically for all $t$.
