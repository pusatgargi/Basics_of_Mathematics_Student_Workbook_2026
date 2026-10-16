# Problem 14: Reconstructing Information from the Derivative

## Problem Statement

It is known that
$$f'(x)=(x-1)(x+2).$$
Determine the monotonicity and the locations of the extrema, and sketch a possible qualitative shape of the function. Then, for
$$g(x)=\frac{x^3}{3}+\frac{x^2}{2}-2x$$
verify that $g'(x)=(x-1)(x+2)$, and compare the specific graph with the earlier qualitative sketch.

## Theoretical Background and Concepts

Reconstructing the behavior of a function $f$ directly from its derivative $f'$ highlights what $f'$ determines uniquely and what remains free up to a constant:

1. **Features Uniquely Determined by $f'(x)$**:
   - **Critical Points and Monotonicity**: The zeros of $f'(x)$ are the critical points of $f$, and the sign of $f'(x)$ on each interval uniquely determines where $f$ is strictly increasing ($f'(x) > 0$) and where $f$ is strictly decreasing ($f'(x) < 0$).
   - **$x$-Coordinates and Character of Local Extrema**: Wherever $f'(x)$ changes sign from $+$ to $-$, $f$ has a local maximum; wherever $f'(x)$ changes sign from $-$ to $+$, $f$ has a local minimum.
   - **Curvature and $x$-Coordinate of Inflection Points**: Differentiating $f'(x)$ yields $f''(x) = (f'(x))'$, which uniquely determines the intervals of convexity ($f''(x) > 0$), concavity ($f''(x) < 0$), and the $x$-coordinates of any inflection points.
   - **Relative Height Differences**: For any two points $x_1, x_2$, the difference $f(x_2) - f(x_1)$ is uniquely fixed by $f'$.
2. **What $f'(x)$ Alone Does Not Determine (Vertical Translation Freedom)**:
   - By a corollary of Lagrange's Mean Value Theorem on $\mathbb{R}$, if $f'(x) = g'(x)$ for all $x \in \mathbb{R}$, then there exists a constant $C \in \mathbb{R}$ such that
     $$f(x) = g(x) + C \quad \text{for all } x \in \mathbb{R}.$$
   - Thus, all possible functions $f$ with derivative $f'(x) = (x - 1)(x + 2)$ have the **exact same shape** and differ only by a rigid **vertical shift $C$** (which changes the $y$-intercept, the absolute $y$-values of the extrema, and the number/location of $x$-intercepts).

## Detailed Step-by-Step Solution

### Step 1: Monotonicity, Extrema Locations, and Curvature from $f'(x) = (x - 1)(x + 2)$

1. **Domain and Critical Points**:
   The derivative $f'(x) = (x - 1)(x + 2) = x^2 + x - 2$ is defined on all of $\mathbb{R}$, so $f$ is smooth on $\mathbb{R}$. Setting $f'(x) = 0$:
   $$(x - 1)(x + 2) = 0 \iff x = -2 \quad \text{or} \quad x = 1.$$
   Thus, the critical points of $f$ are $x = -2$ and $x = 1$.

2. **Sign Chart of $f'(x)$ and Monotonicity**:
   The critical points $-2 < 1$ partition $\mathbb{R}$ into three intervals: $(-\infty, -2)$, $(-2, 1)$, and $(1, \infty)$. Since $f'(x) = (x - 1)(x + 2)$ is a quadratic with leading coefficient $+1 > 0$:
   - On $(-\infty, -2)$: $x + 2 < 0$ and $x - 1 < 0 \implies f'(x) > 0$, so $f$ is **strictly increasing** on $(-\infty, -2]$.
   - On $(-2, 1)$: $x + 2 > 0$ and $x - 1 < 0 \implies f'(x) < 0$, so $f$ is **strictly decreasing** on $[-2, 1]$.
   - On $(1, \infty)$: $x + 2 > 0$ and $x - 1 > 0 \implies f'(x) > 0$, so $f$ is **strictly increasing** on $[1, \infty)$.

3. **Locations and Character of Local Extrema**:
   - At **$x = -2$**: $f'(x)$ changes sign from $+$ to $-$, so $f$ has a **strict local maximum at $x = -2$**.
   - At **$x = 1$**: $f'(x)$ changes sign from $-$ to $+$, so $f$ has a **strict local minimum at $x = 1$**.

4. **Second Derivative and Inflection Point Location**:
   Differentiating $f'(x) = x^2 + x - 2$ gives:
   $$f''(x) = 2x + 1 = 2\left(x + \frac{1}{2}\right).$$
   - For $x \in \left(-\infty, -\frac{1}{2}\right)$, $f''(x) < 0$ ($f$ is **concave**, $\cap$).
   - For $x \in \left(-\frac{1}{2}, \infty\right)$, $f''(x) > 0$ ($f$ is **convex**, $\cup$).
   - At **$x = -\frac{1}{2}$** (the midpoint of $-2$ and $1$), $f$ has an **inflection point**.

| Interval / Point | $(-\infty, -2)$ | $x = -2$ | $\left(-2, -\frac{1}{2}\right)$ | $x = -\frac{1}{2}$ | $\left(-\frac{1}{2}, 1\right)$ | $x = 1$ | $(1, \infty)$ |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Sign of $f'(x)$ | $+$ | $0$ | $-$ | $-\frac{9}{4}$ | $-$ | $0$ | $+$ |
| Sign of $f''(x)$ | $-$ | $-3$ | $-$ | $0$ | $+$ | $+3$ | $+$ |
| Behavior of $f(x)$ | $\nearrow \cap$ | **Local Max** | $\searrow \cap$ | **Inflection Point** | $\searrow \cup$ | **Local Min** | $\nearrow \cup$ |

### Step 2: Qualitative Sketch of $f(x)$

Without a specified value of $f$ at a point, the vertical placement relative to the $x$-axis is arbitrary (shifted by $+C$), but the cubic S-wave shape with local maximum at $x = -2$, inflection point at $x = -0.5$, and local minimum at $x = 1$ is completely fixed:

```text
             Qualitative Shape of Any Function f with f'(x) = (x - 1)(x + 2)
                                  (Vertical axis position up to +C)
                                    ^
                 Local Max          |                  /
                    *               |                 /
                  / : \             |                /
                 /  :  \            |               /
                /   :   * <-- Inflection Point     /
               /    :   : \         |             /
              /     :   :  \        |            /
             /      :   :   \       |           /
            /       :   :    ' - - -+- - * - - '
           /        :   :           |    :  Local Min
       ---+---------+---+-----------+----+-------------> x
                   -2  -0.5         0    1
```

### Step 3: Verification for $g(x) = \frac{x^3}{3} + \frac{x^2}{2} - 2x$ and Specific Graph Comparison

1. **Verifying $g'(x) = (x - 1)(x + 2)$**:
   Differentiating $g(x) = \frac{x^3}{3} + \frac{x^2}{2} - 2x$ term by term using the power rule:
   $$g'(x) = \frac{3x^2}{3} + \frac{2x}{2} - 2(1) = x^2 + x - 2.$$
   Factoring the quadratic trinomial (since $2 + (-1) = 1$ and $2 \cdot (-1) = -2$):
   $$g'(x) = (x - 1)(x + 2).$$
   This confirms that $g'(x) = f'(x)$ for all $x \in \mathbb{R}$, so $f(x) = g(x) + C$ for some constant $C \in \mathbb{R}$ (with $g$ corresponding to the choice $C = 0$ so that $g(0) = 0$).

2. **Specific Coordinates of Key Features for $g(x)$**:
   - **Origin ($x$- and $y$-intercept)**: $g(0) = 0 \implies (0, 0)$.
   - **Other Zeros of $g(x)$**: Factoring $g(x) = x\left(\frac{x^2}{3} + \frac{x}{2} - 2\right) = \frac{x}{6}(2x^2 + 3x - 12) = 0$ gives $x = 0$ and $x = \frac{-3 \pm \sqrt{9 - 4(2)(-12)}}{4} = \frac{-3 \pm \sqrt{105}}{4}$ ($x_1 \approx -3.31$, $x_3 \approx 1.81$).
   - **Local Maximum at $x = -2$**:
     $$g(-2) = \frac{(-2)^3}{3} + \frac{(-2)^2}{2} - 2(-2) = -\frac{8}{3} + 2 + 4 = \frac{10}{3} \approx 3.33 \implies \left(-2, \frac{10}{3}\right).$$
   - **Inflection Point at $x = -\frac{1}{2}$**:
     $$g\left(-\frac{1}{2}\right) = \frac{-1/8}{3} + \frac{1/4}{2} - 2\left(-\frac{1}{2}\right) = -\frac{1}{24} + \frac{3}{24} + 1 = \frac{13}{12} \approx 1.08 \implies \left(-\frac{1}{2}, \frac{13}{12}\right).$$
   - **Local Minimum at $x = 1$**:
     $$g(1) = \frac{1^3}{3} + \frac{1^2}{2} - 2(1) = \frac{1}{3} + \frac{1}{2} - 2 = -\frac{7}{6} \approx -1.17 \implies \left(1, -\frac{7}{6}\right).$$

3. **Comparison Between the Specific Graph of $g(x)$ and the Qualitative Sketch**:
   - The **monotonicity intervals**, the **$x$-coordinates of the local extrema** ($x = -2$ and $x = 1$), the **inflection $x$-coordinate** ($x = -\frac{1}{2}$), and the **vertical drop from the local maximum to the local minimum** ($\frac{10}{3} - \left(-\frac{7}{6}\right) = \frac{27}{6} = \frac{9}{2} = 4.5$) are **identical** in both graphs.
   - Fixing the specific formula $g(x)$ pins down the vertical position via $g(0) = 0$, placing the local maximum $\left(-2, \frac{10}{3}\right)$ in the second quadrant, the inflection point $\left(-\frac{1}{2}, \frac{13}{12}\right)$ in the second quadrant, and the local minimum $\left(1, -\frac{7}{6}\right)$ in the fourth quadrant, so that $g$ crosses the $x$-axis at three specific points ($\approx -3.31$, $0$, and $\approx 1.81$).

```text
              Specific Graph of g(x) = x^3/3 + x^2/2 - 2x
                                    y
                                    ^
                 Local Max          |
              (-2, 10/3) * . . . . .+ 3.33              /
                       / : \        |                  /
                      /  :  \       |                 /
                     /   :   * (-0.5, 13/12) + 1.08  /
                    /    :    \     |               /
  -----------------*-----+-----+----*----+---------*---------> x
                -3.31   -2   -0.5   0 \  1       1.81
                  /                    \ :       /
                 /                      * . . . + -1.17
                /                    (1, -7/6)
                                     Local Min
```

## Verification and Consistency Checks

1. **Test Points for $g'(x) = (x - 1)(x + 2)$**:
   - In $(-\infty, -2)$, test $x = -3$: $g'(-3) = (-4)(-1) = +4 > 0$ ($\nearrow$).
   - In $(-2, 1)$, test $x = 0$: $g'(0) = (-1)(2) = -2 < 0$ ($\searrow$).
   - In $(1, \infty)$, test $x = 2$: $g'(2) = (1)(4) = +4 > 0$ ($\nearrow$).
2. **Cubic Symmetry Check on $g(x)$**:
   The midpoint of the local maximum $\left(-2, \frac{10}{3}\right)$ and the local minimum $\left(1, -\frac{7}{6}\right)$ is:
   $$\left(\frac{-2 + 1}{2}, \frac{\frac{10}{3} + \left(-\frac{7}{6}\right)}{2}\right) = \left(-\frac{1}{2}, \frac{\frac{13}{6}}{2}\right) = \left(-\frac{1}{2}, \frac{13}{12}\right),$$
   which is the exact inflection point $\left(-\frac{1}{2}, g\left(-\frac{1}{2}\right)\right)$.
