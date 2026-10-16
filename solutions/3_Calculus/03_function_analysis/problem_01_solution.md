# Problem 1: A Cubic Polynomial

## Problem Statement

Analyze the monotonicity and extrema of
$$f(x)=x^3-3x^2+2.$$
Sketch the graph based on the results and mark the critical points.

## Theoretical Background and Concepts

To analyze the shape of a differentiable function $f: \mathbb{R} \to \mathbb{R}$, particularly a polynomial, we combine information from its domain, derivatives, and asymptotic behavior:

1. **Domain and Continuity**: Every polynomial function is defined, continuous, and infinitely differentiable on the entire real line $\mathbb{R} = (-\infty, \infty)$.
2. **Critical Points and Fermat's Theorem**: A point $c$ in the interior of the domain is a **critical (stationary) point** of a differentiable function $f$ if $f'(c) = 0$. By Fermat's Theorem, any local extremum of a differentiable function must occur at a critical point.
3. **Monotonicity Criterion**: As a consequence of Lagrange's Mean Value Theorem on an interval $I$:
   - If $f'(x) > 0$ for all interior points $x \in I$ (and vanishes only at isolated points), then $f$ is **strictly increasing** on $I$.
   - If $f'(x) < 0$ for all interior points $x \in I$ (and vanishes only at isolated points), then $f$ is **strictly decreasing** on $I$.
4. **First Derivative Test for Local Extrema**: Let $c$ be a critical point ($f'(c) = 0$):
   - If $f'(x)$ changes sign from **positive to negative** as $x$ passes through $c$ from left to right, then $f$ has a **strict local maximum** at $x = c$.
   - If $f'(x)$ changes sign from **negative to positive** as $x$ passes through $c$ from left to right, then $f$ has a **strict local minimum** at $x = c$.
   - If $f'(x)$ does not change sign across $c$, then $f$ has no local extremum at $x = c$.
5. **Second Derivative, Curvature, and Inflection Points**:
   - Where $f''(x) > 0$, the graph is **convex** (concave up); where $f''(x) < 0$, the graph is **concave** (concave down).
   - A point $(x_0, f(x_0))$ where $f''$ changes sign is an **inflection point**. For any cubic polynomial $ax^3 + bx^2 + cx + d$, the unique inflection point is also the center of point symmetry of the graph and lies halfway between the two critical points when they exist.

## Detailed Step-by-Step Solution

### Step 1: Domain, Intercepts, and End Behavior

- **Domain**: Since $f(x) = x^3 - 3x^2 + 2$ is a polynomial, its domain is
  $$D_f = \mathbb{R} = (-\infty, \infty).$$
- **$y$-intercept**: Evaluating at $x = 0$ gives
  $$f(0) = 0^3 - 3(0)^2 + 2 = 2 \implies (0, 2).$$
- **Zeros ($x$-intercepts)**: By inspection, $x = 1$ is a root because $f(1) = 1 - 3 + 2 = 0$. Dividing $x^3 - 3x^2 + 2$ by $(x - 1)$ yields:
  $$f(x) = (x - 1)(x^2 - 2x - 2).$$
  Solving $x^2 - 2x - 2 = 0$ via the quadratic formula gives $x = \frac{2 \pm \sqrt{4 - 4(1)(-2)}}{2} = 1 \pm \sqrt{3}$. Thus, the three real zeros of $f$ are:
  $$x_1 = 1 - \sqrt{3} \approx -0.732, \qquad x_2 = 1, \qquad x_3 = 1 + \sqrt{3} \approx 2.732.$$
- **Limits at infinity (End Behavior)**: The leading term $x^3$ dominates for large $|x|$:
  $$\lim_{x \to -\infty} f(x) = \lim_{x \to -\infty} x^3\left(1 - \frac{3}{x} + \frac{2}{x^3}\right) = -\infty,$$
  $$\lim_{x \to +\infty} f(x) = \lim_{x \to +\infty} x^3\left(1 - \frac{3}{x} + \frac{2}{x^3}\right) = +\infty.$$
  Since $f$ is a polynomial of degree $3$, it has no vertical, horizontal, or oblique asymptotes.

### Step 2: First Derivative and Critical Points

Differentiating $f(x) = x^3 - 3x^2 + 2$ term by term using the power rule gives:
$$f'(x) = 3x^2 - 6x.$$
Factoring $f'(x)$ completely:
$$f'(x) = 3x(x - 2).$$
To find the critical points, we solve $f'(x) = 0$:
$$3x(x - 2) = 0 \iff x = 0 \quad \text{or} \quad x = 2.$$
Hence, the critical points are $x = 0$ and $x = 2$.

### Step 3: Sign Chart of $f'(x)$ and Monotonicity

The critical points $x = 0$ and $x = 2$ partition the real line into three open intervals: $(-\infty, 0)$, $(0, 2)$, and $(2, \infty)$. Since $f'(x) = 3x(x - 2)$ is a quadratic polynomial with leading coefficient $3 > 0$ and roots at $0$ and $2$:
- On $(-\infty, 0)$: both $x < 0$ and $x - 2 < 0$, so their product is positive: $f'(x) > 0$.
- On $(0, 2)$: $x > 0$ while $x - 2 < 0$, so their product is negative: $f'(x) < 0$.
- On $(2, \infty)$: both $x > 0$ and $x - 2 > 0$, so their product is positive: $f'(x) > 0$.

We summarize the sign of $f'(x)$ and the resulting behavior of $f(x)$ in the following table:

| Interval / Point | $(-\infty, 0)$ | $x = 0$ | $(0, 2)$ | $x = 2$ | $(2, \infty)$ |
| :---: | :---: | :---: | :---: | :---: | :---: |
| Sign of $3x$ | $-$ | $0$ | $+$ | $+$ | $+$ |
| Sign of $x - 2$ | $-$ | $-$ | $-$ | $0$ | $+$ |
| Sign of $f'(x) = 3x(x-2)$ | $+$ | $0$ | $-$ | $0$ | $+$ |
| Behavior of $f(x)$ | $\nearrow$ ( strictly increasing ) | **Local Max** $f(0) = 2$ | $\searrow$ ( strictly decreasing ) | **Local Min** $f(2) = -2$ | $\nearrow$ ( strictly increasing ) |

Therefore:
- $f$ is **strictly increasing** on the intervals $(-\infty, 0]$ and $[2, \infty)$.
- $f$ is **strictly decreasing** on the interval $[0, 2]$.

### Step 4: Local and Global Extrema

Evaluating $f(x)$ at the critical points:
1. At $x = 0$:
   $$f(0) = 0^3 - 3(0)^2 + 2 = 2.$$
   Since $f'(x)$ changes sign from $+$ to $-$ across $x = 0$, the function attains a **local maximum** of $2$ at $x = 0$, corresponding to the point $(0, 2)$.
2. At $x = 2$:
   $$f(2) = 2^3 - 3(2)^2 + 2 = 8 - 12 + 2 = -2.$$
   Since $f'(x)$ changes sign from $-$ to $+$ across $x = 2$, the function attains a **local minimum** of $-2$ at $x = 2$, corresponding to the point $(2, -2)$.
3. Because $\lim_{x \to -\infty} f(x) = -\infty$ and $\lim_{x \to +\infty} f(x) = +\infty$, $f$ has **no global maximum** and **no global minimum** on $\mathbb{R}$.

### Step 5: Second Derivative and Curvature (Supporting the Sketch)

Computing the second derivative helps ensure accurate curvature in the sketch:
$$f''(x) = 6x - 6 = 6(x - 1).$$
- At the critical points: $f''(0) = -6 < 0$ (confirming the local maximum at $x = 0$) and $f''(2) = 6 > 0$ (confirming the local minimum at $x = 2$).
- For $x \in (-\infty, 1)$, $f''(x) < 0$, so $f$ is **concave** (concave down).
- For $x \in (1, \infty)$, $f''(x) > 0$, so $f$ is **convex** (concave up).
- At $x = 1$, $f''(1) = 0$ and $f''$ changes sign, so $(1, f(1)) = (1, 0)$ is an **inflection point**.

### Step 6: Structured Summary of Features and Graph Sketch

- **Domain**: $\mathbb{R}$
- **Zeros**: $(1 - \sqrt{3}, 0) \approx (-0.73, 0)$, $(1, 0)$, and $(1 + \sqrt{3}, 0) \approx (2.73, 0)$
- **$y$-intercept**: $(0, 2)$
- **Intervals of Increase**: $(-\infty, 0]$ and $[2, \infty)$
- **Interval of Decrease**: $[0, 2]$
- **Critical Points & Local Extrema**:
  - Local maximum at $(0, 2)$
  - Local minimum at $(2, -2)$
- **Inflection Point**: $(1, 0)$ (concave on $(-\infty, 1)$, convex on $(1, \infty)$)

```text
                      y
                      ^
                    4 +                                     /
                      |                                    /
                    3 +                                   /
                      |                                  /
       Local Max -> 2 * (0, 2)                          /
                   /  |  \                             /
                  /   |   \                           /
                 /    +    \                         /
                /     |     \    Inflection         /
  -------------+------+------*-------+-------------+----> x
        -1    /       0     (1, 0)   2      (2.73) 3
     (-0.73) /        |        \                 /
            /         +         \               /
           /          |          \             /
          /          -2 +         * (2, -2) --'
         /            |             Local Min
        /            -3 +
```

## Verification and Consistency Checks

1. **Test Points for the Derivative Sign**:
   - In $(-\infty, 0)$, pick $x = -1$: $f'(-1) = 3(-1)(-1 - 2) = 9 > 0$ (confirms $f$ is increasing). Also $f(-1) = -1 - 3 + 2 = -2 < 2 = f(0)$.
   - In $(0, 2)$, pick $x = 1$: $f'(1) = 3(1)(1 - 2) = -3 < 0$ (confirms $f$ is decreasing). Also $f(0) = 2 > 0 = f(1) > -2 = f(2)$.
   - In $(2, \infty)$, pick $x = 3$: $f'(3) = 3(3)(3 - 2) = 9 > 0$ (confirms $f$ is increasing). Also $f(2) = -2 < 2 = f(3)$.
2. **Cubic Symmetry Check**:
   A cubic polynomial is point-symmetric about its inflection point $(1, 0)$, meaning $f(1 + h) + f(1 - h) = 2f(1) = 0$. Checking $h = 1$ (which maps to the two critical points $x = 2$ and $x = 0$):
   $$f(2) + f(0) = -2 + 2 = 0,$$
   and $f'(1 + h) = 3(1 + h)(h - 1) = 3(h^2 - 1) = f'(1 - h)$, which is even in $h$. This confirms that the local maximum $(0, 2)$ and local minimum $(2, -2)$ are symmetrically located relative to the inflection point $(1, 0)$.
