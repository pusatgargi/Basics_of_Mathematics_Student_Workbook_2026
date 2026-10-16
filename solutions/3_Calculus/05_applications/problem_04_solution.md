# Problem 4: Area Between Curves

## Problem Statement

Find the area of the region bounded by the graphs
$$
y=x
$$
and
$$
y=x^2.
$$

First find the intersection points and justify which function is greater on the relevant interval.

## Theoretical Background and Concepts

Given two continuous functions $f, g : [a, b] \to \mathbb{R}$, the area $A$ of the planar region bounded by their graphs $y = f(x)$ and $y = g(x)$ and the vertical lines $x = a$ and $x = b$ is given by the definite integral of the vertical cross-sectional length $|f(x) - g(x)|$:
$$
A = \int_a^b |f(x) - g(x)|\,dx.
$$
When the region is completely enclosed by the two curves without explicit vertical boundary lines specified, the systematic procedure is:

1. **Locate Intersection Points (Limits of Integration)**:
   Solve the equation $f(x) = g(x)$ to find the $x$-coordinates where the two curves cross. These intersection coordinates $a < b$ define the horizontal span $[a, b]$ of the enclosed region.
2. **Determine the Relative Order of the Functions**:
   On each open subinterval $(a, b)$ between consecutive intersection points, check the sign of the difference $f(x) - g(x)$ (by algebraic factorization or inequalities). If $f(x) \ge g(x)$ for all $x \in [a, b]$, then $y = f(x)$ is the **upper boundary** and $y = g(x)$ is the **lower boundary**, so $|f(x) - g(x)| = f(x) - g(x)$.
3. **Evaluate the Definite Integral**:
   Apply the Fundamental Theorem of Calculus:
   $$
   A = \int_a^b \big(f_{\text{upper}}(x) - f_{\text{lower}}(x)\big)\,dx = \Big[F(x) - G(x)\Big]_a^b.
   $$

## Detailed Step-by-Step Solution

### Step 1: Finding the Intersection Points

Let $f(x) = x$ and $g(x) = x^2$. A point $(x, y)$ lies on the intersection of both graphs if and only if its coordinates satisfy both equations simultaneously:
$$
x^2 = x.
$$
Rearranging all terms to one side and factoring:
$$
x^2 - x = 0 \iff x(x - 1) = 0.
$$
Thus, the $x$-coordinates of the intersection points are:
$$
x_1 = 0 \quad \text{and} \quad x_2 = 1.
$$
Substituting back into $y = x$ gives the corresponding points in the plane:
$$
P_1 = (0, 0) \quad \text{and} \quad P_2 = (1, 1).
$$
Therefore, the enclosed region projects onto the interval $[0, 1]$ on the $x$-axis.

---

### Step 2: Justifying Which Function Is Greater on $[0, 1]$

Consider the difference between the two functions on the interval $[0, 1]$:
$$
f(x) - g(x) = x - x^2 = x(1 - x).
$$
For every $x \in (0, 1)$:
- the factor $x > 0$, and
- the factor $1 - x > 0$ (since $x < 1$).

Because the product of two positive numbers is positive, we have:
$$
x(1 - x) > 0 \implies x > x^2 \quad \text{for all } x \in (0, 1),
$$
and at the endpoints $x = 0$ and $x = 1$, we have $x = x^2$.
Consequently, on the entire interval $[0, 1]$:
$$
x \ge x^2,
$$
meaning the linear function $f(x) = x$ is the **upper curve** and the parabola $g(x) = x^2$ is the **lower curve**.

---

### Step 3: Computing the Area of the Bounded Region

Setting up the definite integral of $(f(x) - g(x))$ over $[0, 1]$:
$$
A = \int_0^1 \left(x - x^2\right) dx.
$$
Using the power rule for antiderivatives, $\int x^n\,dx = \frac{x^{n+1}}{n+1} + C$, we find an antiderivative $H(x) = \frac{x^2}{2} - \frac{x^3}{3}$. Applying the Newton–Leibniz formula (Fundamental Theorem of Calculus):
$$
\begin{aligned}
A &= \left[\frac{x^2}{2} - \frac{x^3}{3}\right]_0^1 \\
&= \left(\frac{1^2}{2} - \frac{1^3}{3}\right) - \left(\frac{0^2}{2} - \frac{0^3}{3}\right) \\
&= \frac{1}{2} - \frac{1}{3} \\
&= \frac{3 - 2}{6} = \frac{1}{6}.
\end{aligned}
$$

Thus, the area of the region bounded by $y = x$ and $y = x^2$ is:
$$
A = \frac{1}{6}.
$$

## Verification and Consistency Checks

1. **Test-Point Check of Function Ordering**:
   At the midpoint $x = \frac{1}{2} \in (0, 1)$:
   $$
   f\left(\frac{1}{2}\right) = \frac{1}{2} = 0.5, \qquad g\left(\frac{1}{2}\right) = \left(\frac{1}{2}\right)^2 = \frac{1}{4} = 0.25.
   $$
   Indeed, $0.5 > 0.25$, confirming that $y = x$ lies above $y = x^2$ on $(0, 1)$.

2. **Geometric Bounding Box and Triangle Check**:
   - The region lies strictly inside the right triangle with vertices $(0,0)$, $(1,0)$, and $(1,1)$, whose area is $A_{\triangle} = \frac{1}{2} \cdot 1 \cdot 1 = \frac{1}{2}$. Since $0 < \frac{1}{6} < \frac{1}{2}$, the magnitude is geometrically reasonable.
   - Archimedes' exhaustion theorem for a parabolic segment states that the area under $y = x^2$ on $[0, 1]$ is $\frac{1}{3}$ of the unit square, leaving $\frac{1}{2} - \frac{1}{3} = \frac{1}{6}$ between the chord $y = x$ and the parabola $y = x^2$.

3. **Horizontal Cross-Section (Integration with Respect to $y$) Check**:
   For $y \in [0, 1]$, the left boundary is $x = y$ and the right boundary is $x = \sqrt{y}$ (with $\sqrt{y} \ge y$ on $[0, 1]$). Integrating with respect to $y$:
   $$
   A = \int_0^1 \left(\sqrt{y} - y\right) dy = \left[\frac{2}{3}y^{3/2} - \frac{y^2}{2}\right]_0^1 = \frac{2}{3} - \frac{1}{2} = \frac{1}{6},
   $$
   which matches our vertical-slice calculation identically.
