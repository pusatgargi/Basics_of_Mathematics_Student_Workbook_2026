# Problem 2: Maximum Area of a Rectangle

## Problem Statement

A rectangle has perimeter $40$.

1. Write its area as a function of the length of one side.
2. Determine the domain of this function resulting from the geometry of the problem.
3. Find the dimensions that give the maximum area.
4. Justify that the point found actually gives a maximum.

## Theoretical Background and Concepts

In constrained geometric optimization, we seek the extremum of an **objective quantity** (here, the area $A$ of a rectangle) subject to a **constraint equation** (here, a fixed perimeter $P = 40$). The general optimization workflow proceeds in four stages:

1. **Formulating the Single-Variable Objective Function**:
   Introduce variables for the geometric dimensions ($x$ and $y$), write the constraint $g(x, y) = c$, solve the constraint for one variable in terms of the other ($y = \phi(x)$), and substitute into the objective formula $A(x, y)$ to obtain a function of a single variable $A(x)$.
2. **Determining the Feasible (Geometric) Domain**:
   In Euclidean geometry, lengths of sides of a non-degenerate rectangle must be strictly positive ($x > 0$ and $y > 0$). These positivity conditions restrict $x$ to a well-defined open interval $(a, b)$.
3. **Finding Stationary (Critical) Points**:
   By Fermat's theorem on stationary points, if a differentiable function $A(x)$ attains a local extremum at an interior point $x^*$ of its domain, then $A'(x^*) = 0$.
4. **Sufficient Conditions for a Global Maximum**:
   - **First Derivative Test (Monotonicity)**: If $A'(x) > 0$ for all $x \in (a, x^*)$ and $A'(x) < 0$ for all $x \in (x^*, b)$, then $A(x)$ increases strictly up to $x^*$ and decreases strictly after $x^*$, ensuring a unique global maximum on $(a, b)$.
   - **Second Derivative Test (Concavity)**: If $A''(x) < 0$ on $(a, b)$, then $A(x)$ is strictly concave on the entire domain, so any stationary point $A'(x^*) = 0$ is the unique global maximum.

## Detailed Step-by-Step Solution

### Part 1: Area as a Function of the Length of One Side

Let $x$ and $y$ denote the lengths of the two adjacent sides of the rectangle.
- The perimeter of the rectangle is $P = 2x + 2y = 40$. Dividing both sides by $2$ gives the linear constraint:
  $$
  x + y = 20 \implies y = 20 - x.
  $$
- The area of the rectangle is $A = x \cdot y$. Substituting $y = 20 - x$ yields the area as a function of a single variable $x$:
  $$
  A(x) = x(20 - x) = 20x - x^2.
  $$

---

### Part 2: Domain Resulting from the Geometry of the Problem

For a non-degenerate rectangle to exist geometrically, both side lengths must be strictly positive:
$$
\begin{cases}
x > 0, \\
y = 20 - x > 0 \implies x < 20.
\end{cases}
$$
Combining these two inequalities gives the open geometric domain:
$$
D = (0, 20).
$$
*(Note: If degenerate rectangles of zero width or zero height are included as limiting boundary cases, the closed interval is $[0, 20]$, where $A(0) = A(20) = 0$.)*

---

### Part 3: Finding the Dimensions that Give the Maximum Area

We differentiate the objective function $A(x) = 20x - x^2$ on $D = (0, 20)$:
$$
A'(x) = \frac{d}{dx}\left(20x - x^2\right) = 20 - 2x.
$$
Setting the derivative equal to zero to find the stationary point:
$$
A'(x) = 0 \iff 20 - 2x = 0 \iff 2x = 20 \iff x = 10.
$$
The critical point $x = 10$ lies inside the geometric domain $(0, 20)$.

Substituting $x = 10$ back into the constraint $y = 20 - x$ gives the second side length:
$$
y = 20 - 10 = 10.
$$
The corresponding maximum area is:
$$
A(10) = 10 \times (20 - 10) = 100.
$$
Thus, the dimensions that maximize the area are $x = 10$ and $y = 10$ (a square of side length $10$).

---

### Part 4: Justification that the Point Gives a Maximum

We provide three independent justifications that $x = 10$ yields the unique global maximum on $(0, 20)$:

1. **First Derivative Test (Sign of $A'(x)$)**:
   Since $A'(x) = 2(10 - x)$:
   - For $x \in (0, 10)$, we have $10 - x > 0 \implies A'(x) > 0$, so $A(x)$ is **strictly increasing** on $(0, 10]$.
   - For $x \in (10, 20)$, we have $10 - x < 0 \implies A'(x) < 0$, so $A(x)$ is **strictly decreasing** on $[10, 20)$.
   Therefore, $A(x)$ attains its unique global maximum on $(0, 20)$ at $x = 10$.

2. **Second Derivative Test (Concavity)**:
   Differentiating $A'(x) = 20 - 2x$ a second time gives:
   $$
   A''(x) = -2 < 0 \quad \text{for all } x \in (0, 20).
   $$
   Because $A''(10) = -2 < 0$ (and $A$ is strictly concave everywhere), $x = 10$ is a strict global maximum.

3. **Algebraic Verification (Completing the Square / AM-GM Inequality)**:
   Rewriting $A(x)$ in vertex form:
   $$
   A(x) = 20x - x^2 = 100 - (x^2 - 20x + 100) = 100 - (x - 10)^2.
   $$
   Since $(x - 10)^2 \ge 0$ for all $x \in (0, 20)$ with equality if and only if $x = 10$, we have $A(x) \le 100$, with the maximum value $100$ achieved uniquely at $x = 10$.

## Verification and Consistency Checks

1. **Boundary Behavior**:
   As $x \to 0^+$ or $x \to 20^-$, the rectangle flattens into a line segment and its area approaches zero:
   $$
   \lim_{x \to 0^+} A(x) = 0, \qquad \lim_{x \to 20^-} A(x) = 0,
   $$
   which is strictly less than $A(10) = 100$.

2. **Numerical Check Near the Optimum**:
   Evaluating $A(x)$ at symmetric perturbations $x = 10 \pm \delta$:
   - For $x = 9, y = 11$: $P = 2(9+11) = 40$, and $A(9) = 9 \times 11 = 99 < 100$.
   - For $x = 9.9, y = 10.1$: $P = 2(9.9+10.1) = 40$, and $A(9.9) = 9.9 \times 10.1 = 99.99 < 100$.
   - For $x = 10, y = 10$: $P = 2(10+10) = 40$, and $A(10) = 10 \times 10 = 100$.
   This confirms that among all rectangles of fixed perimeter $40$, the square of side $10$ has the largest area.
