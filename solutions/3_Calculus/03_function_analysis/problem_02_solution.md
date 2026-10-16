# Problem 2: A Parabola from the Perspective of the Derivative

## Problem Statement

For $f(x)=x^2-4x+1$, find the minimum using the derivative. Compare the result with the vertex form and explain why both approaches lead to the same point.

## Theoretical Background and Concepts

A quadratic function $f(x) = ax^2 + bx + c$ ($a \neq 0$) has a parabola as its graph. Its extremum can be analyzed from two complementary viewpoints—differential calculus and elementary algebra:

1. **Calculus Perspective (Derivatives and Critical Points)**:
   - **Domain**: $D_f = \mathbb{R}$, and $f$ is smooth ($C^\infty$) everywhere.
   - **First Derivative and Monotonicity**: The derivative $f'(x) = 2ax + b$ is a linear function with a unique root at $x_0 = -\frac{b}{2a}$. When $a > 0$, $f'(x) < 0$ for $x < x_0$ (so $f$ is strictly decreasing on $(-\infty, x_0]$) and $f'(x) > 0$ for $x > x_0$ (so $f$ is strictly increasing on $[x_0, \infty)$).
   - **Global Minimum**: Because $f$ decreases to the left of $x_0$ and increases to the right of $x_0$ across its entire domain $\mathbb{R}$, the unique critical point $x_0$ is not only a local minimum but also the **strict global minimum** of $f$.
   - **Second Derivative and Convexity**: $f''(x) = 2a$. When $a > 0$, $f''(x) > 0$ on $\mathbb{R}$, so $f$ is strictly convex everywhere and has no inflection points.
2. **Algebraic Perspective (Completing the Square / Vertex Form)**:
   - Rewriting $f(x)$ in vertex form gives
     $$f(x) = a(x - p)^2 + q, \qquad \text{where } p = -\frac{b}{2a}, \quad q = c - \frac{b^2}{4a}.$$
   - Because $(x - p)^2 \ge 0$ for all $x \in \mathbb{R}$ and equals $0$ if and only if $x = p$, when $a > 0$ we immediately have $f(x) \ge q$ for all $x \in \mathbb{R}$, with equality uniquely at $x = p$.

## Detailed Step-by-Step Solution

### Step 1: Finding the Minimum Using the Derivative

1. **Domain and Asymptotes**:
   The function $f(x) = x^2 - 4x + 1$ is a polynomial defined for all $x \in \mathbb{R}$. Since $\lim_{x \to \pm\infty} (x^2 - 4x + 1) = +\infty$, there are no vertical, horizontal, or oblique asymptotes, and $f$ has no global maximum.
2. **First Derivative and Critical Point**:
   Differentiating $f(x) = x^2 - 4x + 1$ with respect to $x$:
   $$f'(x) = 2x - 4 = 2(x - 2).$$
   Setting $f'(x) = 0$ to locate the critical point:
   $$2(x - 2) = 0 \iff x = 2.$$
3. **Sign Chart of $f'(x)$ and Monotonicity**:
   The critical point $x = 2$ divides $\mathbb{R}$ into two intervals, $(-\infty, 2)$ and $(2, \infty)$:
   - For $x \in (-\infty, 2)$, we have $x - 2 < 0 \implies f'(x) < 0$, so $f$ is **strictly decreasing** on $(-\infty, 2]$.
   - For $x \in (2, \infty)$, we have $x - 2 > 0 \implies f'(x) > 0$, so $f$ is **strictly increasing** on $[2, \infty)$.

   | Interval / Point | $(-\infty, 2)$ | $x = 2$ | $(2, \infty)$ |
   | :---: | :---: | :---: | :---: |
   | Sign of $f'(x) = 2(x - 2)$ | $-$ | $0$ | $+$ |
   | Behavior of $f(x)$ | $\searrow$ (strictly decreasing) | **Global Min** $f(2) = -3$ | $\nearrow$ (strictly increasing) |

4. **Minimum Value and Second Derivative Check**:
   Evaluating $f$ at $x = 2$:
   $$f(2) = 2^2 - 4(2) + 1 = 4 - 8 + 1 = -3.$$
   Moreover, $f''(x) = 2 > 0$ for all $x \in \mathbb{R}$, so $f$ is strictly convex on $\mathbb{R}$. Thus, $f$ attains its **local and global minimum** at the point $(2, -3)$, with minimum value $f_{\min} = -3$.

### Step 2: Finding the Minimum Using the Vertex Form

We complete the square for $f(x) = x^2 - 4x + 1$ by adding and subtracting $\left(\frac{-4}{2}\right)^2 = 4$:
$$f(x) = \left(x^2 - 4x + 4\right) - 4 + 1 = (x - 2)^2 - 3.$$
Since the square of any real number is non-negative:
$$(x - 2)^2 \ge 0 \quad \text{for all } x \in \mathbb{R},$$
with equality $(x - 2)^2 = 0$ if and only if $x = 2$, adding $-3$ to both sides yields:
$$f(x) = (x - 2)^2 - 3 \ge -3 \quad \text{for all } x \in \mathbb{R}.$$
Hence, the minimum value is $-3$, attained uniquely at $x = 2$, which gives the vertex $(2, -3)$.

### Step 3: Comparing Both Approaches and Explaining Why They Coincide

Both methods produce the exact same point $(2, -3)$ for two closely related reasons:

1. **Analytic Explanation (Differentiation of the Vertex Form)**:
   Any quadratic function with $a > 0$ can be written in vertex form as
   $$f(x) = a(x - p)^2 + q.$$
   Differentiating this expression directly using the chain rule gives:
   $$f'(x) = 2a(x - p).$$
   Because $a \neq 0$, the derivative vanishes if and only if the squared term $(x - p)^2$ vanishes:
   $$f'(x) = 0 \iff 2a(x - p) = 0 \iff x = p.$$
   Furthermore, the constant term $q = f(p)$ disappears upon differentiation, which is why $f'(x) = 0$ identifies the horizontal coordinate $x = p$ of the vertex, and substituting $x = p$ back into $f(x)$ recovers the vertical coordinate $q = -3$.
2. **Geometric Explanation (Symmetry and Horizontal Tangent)**:
   From the vertex form $f(x) = (x - 2)^2 - 3$, the parabola is symmetric across the vertical axis $x = 2$ because
   $$f(2 + h) = h^2 - 3 = (-h)^2 - 3 = f(2 - h) \quad \text{for all } h \in \mathbb{R}.$$
   Differentiating this symmetry identity with respect to $h$ gives $f'(2 + h) = -f'(2 - h)$. Setting $h = 0$ forces $f'(2) = -f'(2)$, so $f'(2) = 0$. Geometrically, at the lowest point of a smooth symmetric U-shaped curve, the tangent line must be horizontal ($y = -3$).

## Verification and Consistency Checks

1. **Test Points on Both Sides of $x = 2$**:
   - At $x = 0 \in (-\infty, 2)$: $f'(0) = 2(0) - 4 = -4 < 0$, and $f(0) = 1 > -3 = f(2)$.
   - At $x = 4 \in (2, \infty)$: $f'(4) = 2(4) - 4 = 4 > 0$, and $f(4) = 16 - 16 + 1 = 1 > -3 = f(2)$.
   Notice that $x = 0$ and $x = 4$ are symmetric about $x = 2$ ($2 - 2 = 0$ and $2 + 2 = 4$), and indeed $f(0) = f(4) = 1$ while $f'(0) = -f'(4) = -4$.
2. **Intercepts Consistency Check**:
   Setting the vertex form equal to zero: $(x - 2)^2 - 3 = 0 \iff x = 2 \pm \sqrt{3}$ ($x_1 = 2 - \sqrt{3} \approx 0.268$, $x_2 = 2 + \sqrt{3} \approx 3.732$). The midpoint of the two roots is $\frac{(2 - \sqrt{3}) + (2 + \sqrt{3})}{2} = 2$, which matches the critical point $x = 2$.
