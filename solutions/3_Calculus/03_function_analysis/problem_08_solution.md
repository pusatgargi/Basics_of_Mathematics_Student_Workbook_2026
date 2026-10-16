# Problem 8: The Second Derivative

## Problem Statement

For
$$f(x)=x^4-4x^2$$
find the local extrema, intervals of convexity and concavity, and inflection points. Sketch the graph and mark all the identified features on it.

## Theoretical Background and Concepts

While the first derivative $f'(x)$ controls the **direction** of a graph (monotonicity and local extrema), the second derivative $f''(x) = (f'(x))'$ controls the **curvature** (how the slope $f'(x)$ itself changes):

1. **Convexity and Concavity via the Second Derivative**:
   Let $f$ be twice differentiable on an open interval $I$:
   - If $f''(x) > 0$ for all $x \in I$, then $f'(x)$ is strictly increasing on $I$, so $f$ is **strictly convex** (concave up, $\cup$) on $I$. Geometrically, the graph lies above its tangent lines on $I$.
   - If $f''(x) < 0$ for all $x \in I$, then $f'(x)$ is strictly decreasing on $I$, so $f$ is **strictly concave** (concave down, $\cap$) on $I$. Geometrically, the graph lies below its tangent lines on $I$.
2. **Inflection Points**:
   - A point $(x_0, f(x_0))$ is an **inflection point** of $f$ if $f$ is continuous at $x_0$ and changes curvature (from convex to concave or from concave to convex) across $x_0$.
   - **Necessary Condition**: If $f$ is twice differentiable at an inflection point $x_0$, then $f''(x_0) = 0$.
   - **Sufficient Condition**: If $f''(x_0) = 0$ and $f''(x)$ **changes sign** as $x$ passes through $x_0$, then $(x_0, f(x_0))$ is an inflection point.
3. **Second Derivative Test for Local Extrema**:
   If $f'(c) = 0$ and $f''(c) > 0$, then $c$ is a strict local minimum; if $f'(c) = 0$ and $f''(c) < 0$, then $c$ is a strict local maximum.

## Detailed Step-by-Step Solution

### Step 1: Domain, Symmetry, Zeros, and End Behavior

- **Domain**: $D_f = \mathbb{R} = (-\infty, \infty)$.
- **Symmetry**: Since $f(-x) = (-x)^4 - 4(-x)^2 = x^4 - 4x^2 = f(x)$ for all $x \in \mathbb{R}$, $f$ is an **even function**, so its graph is symmetric with respect to the $y$-axis.
- **Zeros ($x$-intercepts) and $y$-intercept**:
  Factoring $f(x)$ completely:
  $$f(x) = x^2(x^2 - 4) = x^2(x - 2)(x + 2).$$
  Setting $f(x) = 0$ gives three zeros:
  $$x = -2, \qquad x = 0 \text{ (double root)}, \qquad x = 2.$$
  The $y$-intercept is $(0, 0)$.
- **End Behavior**: Since the leading term is $x^4$ with positive coefficient,
  $$\lim_{x \to -\infty} (x^4 - 4x^2) = +\infty, \qquad \lim_{x \to +\infty} (x^4 - 4x^2) = +\infty.$$

### Step 2: First Derivative, Monotonicity, and Local Extrema

Differentiating $f(x) = x^4 - 4x^2$:
$$f'(x) = 4x^3 - 8x = 4x(x^2 - 2) = 4x\left(x - \sqrt{2}\right)\left(x + \sqrt{2}\right).$$

1. **Critical Points**:
   $$f'(x) = 0 \iff x = -\sqrt{2} \approx -1.414, \quad x = 0, \quad \text{or} \quad x = \sqrt{2} \approx 1.414.$$
2. **Sign Chart of $f'(x)$**:
   The polynomial $f'(x)$ has positive leading coefficient $4$ and three simple roots $-\sqrt{2} < 0 < \sqrt{2}$, so its sign alternates across the four intervals:
   - On $(-\infty, -\sqrt{2})$: $f'(x) < 0 \implies f$ is **strictly decreasing**.
   - On $(-\sqrt{2}, 0)$: $f'(x) > 0 \implies f$ is **strictly increasing**.
   - On $(0, \sqrt{2})$: $f'(x) < 0 \implies f$ is **strictly decreasing**.
   - On $(\sqrt{2}, \infty)$: $f'(x) > 0 \implies f$ is **strictly increasing**.

   | Interval / Point | $(-\infty, -\sqrt{2})$ | $x = -\sqrt{2}$ | $(-\sqrt{2}, 0)$ | $x = 0$ | $(0, \sqrt{2})$ | $x = \sqrt{2}$ | $(\sqrt{2}, \infty)$ |
   | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
   | Sign of $f'(x)$ | $-$ | $0$ | $+$ | $0$ | $-$ | $0$ | $+$ |
   | Behavior of $f(x)$ | $\searrow$ | **Local Min** $-4$ | $\nearrow$ | **Local Max** $0$ | $\searrow$ | **Local Min** $-4$ | $\nearrow$ |

3. **Local (and Global) Extrema**:
   - At $x = -\sqrt{2}$ and $x = \sqrt{2}$: $f'(x)$ changes sign from $-$ to $+$, so $f$ attains **local (and global) minima** at $x = \pm\sqrt{2}$:
     $$f\left(\pm\sqrt{2}\right) = \left(\pm\sqrt{2}\right)^4 - 4\left(\pm\sqrt{2}\right)^2 = 4 - 8 = -4 \implies \left(-\sqrt{2}, -4\right) \text{ and } \left(\sqrt{2}, -4\right).$$
   - At $x = 0$: $f'(x)$ changes sign from $+$ to $-$, so $f$ attains a **local maximum** at $x = 0$:
     $$f(0) = 0^4 - 4(0)^2 = 0 \implies (0, 0).$$

### Step 3: Second Derivative, Convexity/Concavity, and Inflection Points

Differentiating $f'(x) = 4x^3 - 8x$:
$$f''(x) = 12x^2 - 8 = 4(3x^2 - 2) = 12\left(x - \sqrt{\frac{2}{3}}\right)\left(x + \sqrt{\frac{2}{3}}\right) = 12\left(x - \frac{\sqrt{6}}{3}\right)\left(x + \frac{\sqrt{6}}{3}\right).$$

1. **Candidate Points for Inflection ($f''(x) = 0$)**:
   $$3x^2 - 2 = 0 \iff x^2 = \frac{2}{3} \iff x = -\frac{\sqrt{6}}{3} \approx -0.8165 \quad \text{or} \quad x = \frac{\sqrt{6}}{3} \approx 0.8165.$$
2. **Sign Chart of $f''(x)$ and Curvature**:
   Since $f''(x) = 12x^2 - 8$ is a parabola opening upward with roots at $\pm\frac{\sqrt{6}}{3}$:
   - On $\left(-\infty, -\frac{\sqrt{6}}{3}\right)$: $f''(x) > 0 \implies f$ is **strictly convex** (concave up, $\cup$).
   - On $\left(-\frac{\sqrt{6}}{3}, \frac{\sqrt{6}}{3}\right)$: $f''(x) < 0 \implies f$ is **strictly concave** (concave down, $\cap$).
   - On $\left(\frac{\sqrt{6}}{3}, \infty\right)$: $f''(x) > 0 \implies f$ is **strictly convex** (concave up, $\cup$).

   | Interval / Point | $\left(-\infty, -\frac{\sqrt{6}}{3}\right)$ | $x = -\frac{\sqrt{6}}{3}$ | $\left(-\frac{\sqrt{6}}{3}, \frac{\sqrt{6}}{3}\right)$ | $x = \frac{\sqrt{6}}{3}$ | $\left(\frac{\sqrt{6}}{3}, \infty\right)$ |
   | :---: | :---: | :---: | :---: | :---: | :---: |
   | Sign of $f''(x)$ | $+$ | $0$ | $-$ | $0$ | $+$ |
   | Curvature of $f(x)$ | $\cup$ (convex) | **Inflection Point** | $\cap$ (concave) | **Inflection Point** | $\cup$ (convex) |

3. **Inflection Points**:
   Because $f''(x)$ changes sign at both $x = -\frac{\sqrt{6}}{3}$ and $x = \frac{\sqrt{6}}{3}$, both are inflection points. Computing their $y$-coordinates (using $x^2 = \frac{2}{3}$):
   $$f\left(\pm\frac{\sqrt{6}}{3}\right) = \left(\frac{2}{3}\right)^2 - 4\left(\frac{2}{3}\right) = \frac{4}{9} - \frac{24}{9} = -\frac{20}{9} \approx -2.222.$$
   Therefore, the two **inflection points** are:
   $$I_1 = \left(-\frac{\sqrt{6}}{3}, -\frac{20}{9}\right) \approx (-0.82, -2.22), \qquad I_2 = \left(\frac{\sqrt{6}}{3}, -\frac{20}{9}\right) \approx (0.82, -2.22).$$

### Step 4: Structured Summary of Features and Graph Sketch

- **Domain**: $\mathbb{R}$ (even function, symmetric across the $y$-axis)
- **Zeros**: $(-2, 0)$, $(0, 0)$, and $(2, 0)$
- **Local Maximum**: $(0, 0)$
- **Local and Global Minima**: $\left(-\sqrt{2}, -4\right) \approx (-1.41, -4)$ and $\left(\sqrt{2}, -4\right) \approx (1.41, -4)$
- **Intervals of Convexity ($\cup$)**: $\left(-\infty, -\frac{\sqrt{6}}{3}\right]$ and $\left[\frac{\sqrt{6}}{3}, \infty\right)$
- **Interval of Concavity ($\cap$)**: $\left[-\frac{\sqrt{6}}{3}, \frac{\sqrt{6}}{3}\right]$
- **Inflection Points**: $\left(-\frac{\sqrt{6}}{3}, -\frac{20}{9}\right)$ and $\left(\frac{\sqrt{6}}{3}, -\frac{20}{9}\right)$

```text
                        y
                        ^
                      2 +   \                                   /
                        |    \                                 /
                      1 +     \                               /
                        |      \         Local Max           /
            (-2, 0)     |       \          (0, 0)           /     (2, 0)
  ----------------------*--------*-----------*-------------*--------*------> x
                       -2     -1.41  -0.82   |   0.82    1.41       2
                        |         \    :   / | \   :    /
                     -1 +          \   :  /  |  \  :   /
                        |           \  : /   |   \ :  /
    Inflection       -2 +       I1 -> *      |      * <- I2  (+-sqrt(6)/3, -20/9)
    Points              |              \     |     /
                     -3 +               \    |    /
                        |                \   |   /
                     -4 + . . . . . . . . *--+--* . . . . . . . .
                                  (-sqrt(2),-4) (sqrt(2),-4)
                                     Local/Global Minima
```

## Verification and Consistency Checks

1. **Second Derivative Test at Critical Points**:
   - At $x = 0$: $f''(0) = 12(0)^2 - 8 = -8 < 0$, which confirms that $(0, 0)$ is a strict local maximum and lies inside the concave interval $\left(-\frac{\sqrt{6}}{3}, \frac{\sqrt{6}}{3}\right)$.
   - At $x = \pm\sqrt{2}$: $f''\left(\pm\sqrt{2}\right) = 12(2) - 8 = 16 > 0$, which confirms that $\left(\pm\sqrt{2}, -4\right)$ are strict local minima and lie inside the convex intervals $\left(-\infty, -\frac{\sqrt{6}}{3}\right)$ and $\left(\frac{\sqrt{6}}{3}, \infty\right)$.
2. **Completing the Square in $u = x^2$**:
   Writing $f(x) = (x^2)^2 - 4x^2 = (x^2 - 2)^2 - 4$, we see immediately that $(x^2 - 2)^2 \ge 0$, so $f(x) \ge -4$ for all $x \in \mathbb{R}$, with equality if and only if $x^2 = 2 \iff x = \pm\sqrt{2}$. This independently verifies the global minimum value $-4$ and its locations $x = \pm\sqrt{2}$.
3. **Ordering of Key $x$-Coordinates**:
   For $x \ge 0$, the special points occur in the strict order
   $$0 < \frac{\sqrt{6}}{3} \approx 0.8165 < \sqrt{2} \approx 1.4142 < 2,$$
   with corresponding $y$-values $f(0) = 0 > f\left(\frac{\sqrt{6}}{3}\right) = -\frac{20}{9} > f\left(\sqrt{2}\right) = -4 < f(2) = 0$, matching the W-shaped graph.
