# Problem 12: A Function with an Absolute Value

## Problem Statement

Analyze
$$f(x)=|x^2-4|.$$
First sketch $x^2-4$, then explain the effect of the absolute value. Indicate the points where the derivative does not exist and justify the reason geometrically.

## Theoretical Background and Concepts

Functions of the form $f(x) = |g(x)|$, where $g(x)$ is a smooth function, highlight the interplay between geometry, piecewise definitions, and non-differentiability:

1. **Geometric Effect of the Absolute Value Transformation $g(x) \mapsto |g(x)|$**:
   By the definition of absolute value,
   $$|g(x)| = \begin{cases} g(x), & \text{if } g(x) \ge 0, \\ -g(x), & \text{if } g(x) < 0. \end{cases}$$
   Geometrically:
   - Every portion of the graph of $y = g(x)$ that lies **on or above the $x$-axis** ($g(x) \ge 0$) remains **unchanged**.
   - Every portion of the graph of $y = g(x)$ that lies **strictly below the $x$-axis** ($g(x) < 0$) is **reflected vertically across the $x$-axis** into the upper half-plane $y > 0$.
2. **Differentiability at the Zeros of $g(x)$**:
   - Away from the zeros of $g(x)$, $f(x) = \pm g(x)$ is differentiable with $f'(x) = \operatorname{sgn}(g(x)) \cdot g'(x)$.
   - At a zero $x_0$ where $g(x_0) = 0$ and $g(x)$ changes sign, reflecting the negative branch reverses the sign of its slope. Consequently, the one-sided derivatives at $x_0$ have opposite signs:
     $$f'_-(x_0) = -f'_+(x_0) = \pm |g'(x_0)|.$$
   - Therefore, whenever $g(x_0) = 0$ and $g'(x_0) \neq 0$ (a simple/transverse root), $f'_-(x_0) \neq f'_+(x_0)$, so **$f$ is not differentiable at $x_0$**, and the graph of $f$ has a **sharp corner** at $(x_0, 0)$.
3. **Generalized Critical Points**:
   A local extremum of a continuous function $f$ can occur either at a **stationary point** where $f'(c) = 0$ or at a **singular (non-differentiable) point** where $f'(c)$ does not exist. Both types of points must be included in the monotonicity and extrema table.

## Detailed Step-by-Step Solution

### Step 1: Analysis and Sketch of the Inner Quadratic $g(x) = x^2 - 4$

Let $g(x) = x^2 - 4 = (x - 2)(x + 2)$.
- **Domain and Symmetry**: $D_g = \mathbb{R}$, and $g(-x) = g(x)$ (even function).
- **Zeros ($x$-intercepts)**: $g(x) = 0 \iff x = -2$ or $x = 2$.
- **Vertex (Global Minimum)**: Since $g'(x) = 2x = 0 \iff x = 0$, the parabola opens upward with vertex at $(0, -4)$.
- **Sign of $g(x)$**:
  - $g(x) > 0$ on $(-\infty, -2) \cup (2, \infty)$,
  - $g(x) = 0$ at $x = -2$ and $x = 2$,
  - $g(x) < 0$ on $(-2, 2)$.

```text
                 Graph of g(x) = x^2 - 4
                        y
                        ^
                      5 +  \                         /
                        |   \                       /
                      2 +    \                     /
                        |     \                   /
  ----------------------+------*--------+--------*------> x
             -3        -2      |\       0       / 2      3
                        |      | \      |      /
                     -2 +      |  \     |     /
                        |      |   \    |    /   (Portion below x-axis
                     -4 +      |    ' - * - '     to be reflected upward)
                                     (0, -4)
```

### Step 2: Effect of the Absolute Value and Piecewise Formula for $f(x) = |x^2 - 4|$

Applying the absolute value to $g(x) = x^2 - 4$ leaves the outer branches $(-\infty, -2]$ and $[2, \infty)$ unchanged and reflects the middle arc $(-2, 2)$ across the $x$-axis:
$$f(x) = |x^2 - 4| = \begin{cases} x^2 - 4, & \text{if } x \in (-\infty, -2] \cup [2, \infty), \\ -(x^2 - 4) = 4 - x^2, & \text{if } x \in (-2, 2). \end{cases}$$

- **Domain and Range**: $D_f = \mathbb{R}$, and since $|x^2 - 4| \ge 0$ with $\lim_{x \to \pm\infty} f(x) = +\infty$, the range is $[0, \infty)$.
- **Symmetry**: $f(-x) = |(-x)^2 - 4| = |x^2 - 4| = f(x)$, so $f$ is an **even function**.
- **Zeros**: $f(x) = 0 \iff x^2 - 4 = 0 \iff x = -2$ or $x = 2$.
- **$y$-Intercept**: $f(0) = |0 - 4| = 4 \implies (0, 4)$, which is the reflected image of the vertex $(0, -4)$ of $g$.

### Step 3: Derivative Analysis and Points of Non-Differentiability

1. **Derivative on the Open Intervals $(-\infty, -2)$, $(-2, 2)$, and $(2, \infty)$**:
   Differentiating each smooth piece on its interior gives:
   $$f'(x) = \begin{cases} 2x, & \text{if } x \in (-\infty, -2) \cup (2, \infty), \\ -2x, & \text{if } x \in (-2, 2). \end{cases}$$
   Setting $f'(x) = 0$ on these open intervals:
   - On $(-\infty, -2) \cup (2, \infty)$: $2x = 0$ has no solution in these intervals.
   - On $(-2, 2)$: $-2x = 0 \iff x = 0 \in (-2, 2)$.

2. **One-Sided Derivatives at the Transition Points $x = -2$ and $x = 2$**:
   - **At $x = -2$** (where $f(-2) = 0$):
     $$f'_-(-2) = \lim_{x \to -2^-} \frac{f(x) - f(-2)}{x - (-2)} = \lim_{x \to -2^-} \frac{x^2 - 4}{x + 2} = \lim_{x \to -2^-} (x - 2) = -4,$$
     $$f'_+(-2) = \lim_{x \to -2^+} \frac{f(x) - f(-2)}{x - (-2)} = \lim_{x \to -2^+} \frac{4 - x^2}{x + 2} = \lim_{x \to -2^+} (2 - x) = +4.$$
     Because $f'_-(-2) = -4 \neq +4 = f'_+(-2)$, **$f'(-2)$ does not exist**.
   - **At $x = 2$** (where $f(2) = 0$):
     $$f'_-(2) = \lim_{x \to 2^-} \frac{f(x) - f(2)}{x - 2} = \lim_{x \to 2^-} \frac{4 - x^2}{x - 2} = \lim_{x \to 2^-} -(x + 2) = -4,$$
     $$f'_+(2) = \lim_{x \to 2^+} \frac{f(x) - f(2)}{x - 2} = \lim_{x \to 2^+} \frac{x^2 - 4}{x - 2} = \lim_{x \to 2^+} (x + 2) = +4.$$
     Because $f'_-(2) = -4 \neq +4 = f'_+(2)$, **$f'(2)$ does not exist**.

3. **Geometric Justification for Non-Differentiability at $x = -2$ and $x = 2$**:
   The parabola $y = x^2 - 4$ crosses the $x$-axis at $(-2, 0)$ and $(2, 0)$ at a steep, non-zero angle (with slopes $g'(-2) = -4$ and $g'(2) = +4$). When the negative arc between $-2$ and $2$ is folded upward across the $x$-axis, the tangent ray from the left of $x = 2$ (which was pointing upward with slope $+4$) is reflected into a ray pointing **downward with slope $-4$**, while the tangent ray from the right of $x = 2$ still points **upward with slope $+4$**. Thus, at both $(-2, 0)$ and $(2, 0)$, the graph forms a **sharp V-shaped corner** with two distinct half-tangents (slopes $-4$ and $+4$) rather than a single unique tangent line.

### Step 4: Monotonicity, Extrema, Curvature, and Sketch of $f(x) = |x^2 - 4|$

Combining the stationary point $x = 0$ and the two non-differentiable corner points $x = -2, 2$:

| Interval / Point | $(-\infty, -2)$ | $x = -2$ | $(-2, 0)$ | $x = 0$ | $(0, 2)$ | $x = 2$ | $(2, \infty)$ |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| $f'(x)$ | $2x < 0$ ($-$) | DNE ($-4 \mid +4$) | $-2x > 0$ ($+$) | $0$ | $-2x < 0$ ($-$) | DNE ($-4 \mid +4$) | $2x > 0$ ($+$) |
| $f''(x)$ | $+2$ ($\cup$) | DNE | $-2$ ($\cap$) | $-2$ ($\cap$) | $-2$ ($\cap$) | DNE | $+2$ ($\cup$) |
| Behavior of $f(x)$ | $\searrow$ | **Global Min** $0$ | $\nearrow$ | **Local Max** $4$ | $\searrow$ | **Global Min** $0$ | $\nearrow$ |

- **Monotonicity**:
  - **Strictly decreasing** on $(-\infty, -2]$ and on $[0, 2]$.
  - **Strictly increasing** on $[-2, 0]$ and on $[2, \infty)$.
- **Extrema**:
  - **Local and Global Minima** at $x = -2$ and $x = 2$, with value $f(-2) = f(2) = 0$ (attained at the sharp corners where $f'$ does not exist).
  - **Local Maximum** at $x = 0$, with value $f(0) = 4$ (attained at the smooth peak where $f'(0) = 0$).
- **Curvature**: Strictly convex ($\cup$) on $(-\infty, -2]$ and $[2, \infty)$; strictly concave ($\cap$) on $[-2, 2]$.

```text
                 Graph of f(x) = |x^2 - 4|
                        y
                        ^
                      5 +  \                         /
                        |   \      Local Max        /
                      4 +    \      * (0, 4)       /
                        |     \   / | \           /
                      2 +      \ /  |  \         /
                        |       |   |   |       /
  ----------------------+-------*---+---*------+-------> x
             -3        -2      -1   0   1      2       3
                     (-2, 0)                (2, 0)
                    Sharp Corner          Sharp Corner
                    (Global Min)          (Global Min)
```

## Verification and Consistency Checks

1. **Test Points in Each of the Four Monotonicity Intervals**:
   - At $x = -3 \in (-\infty, -2)$: $f(-3) = |9 - 4| = 5$, and $f'(-3) = 2(-3) = -6 < 0$.
   - At $x = -1 \in (-2, 0)$: $f(-1) = |1 - 4| = 3$, and $f'(-1) = -2(-1) = +2 > 0$.
   - At $x = 1 \in (0, 2)$: $f(1) = |1 - 4| = 3$, and $f'(1) = -2(1) = -2 < 0$.
   - At $x = 3 \in (2, \infty)$: $f(3) = |9 - 4| = 5$, and $f'(3) = 2(3) = +6 > 0$.
2. **Important Calculus Lesson**:
   If one searched for extrema solely by solving $f'(x) = 0$, one would find only the local maximum at $x = 0$ and completely miss the global minima at $x = -2$ and $x = 2$, because $f'(-2)$ and $f'(2)$ do not exist.
