# Problem 12: Symmetry, Sign, and Absolute Value

## Problem Statement

Compare
$$\int_{-2}^{2}x\,dx$$
and
$$\int_{-2}^{2}|x|\,dx.$$
Before calculating, predict the results from symmetry and a sketch, then carry out the calculation and explain the difference.

## Theoretical Background and Concepts

- **Symmetry of Functions on a Symmetric Interval $[-a, a]$**:
  1. **Odd Function ($f(-x) = -f(x)$)**: The graph of an odd function is symmetric with respect to the origin $(0,0)$. For every positive height $f(x)$ on $[0, a]$, there is an equal and opposite negative height $f(-x) = -f(x)$ on $[-a, 0]$. Because the definite integral measures **net signed area**, the negative signed area on $[-a, 0]$ and the positive signed area on $[0, a]$ cancel out completely:
     $$\int_{-a}^{a} f(x)\,dx = 0 \quad \text{(if } f \text{ is odd)}.$$
  2. **Even Function ($g(-x) = g(x)$)**: The graph of an even function is symmetric across the vertical $y$-axis. The signed area on $[-a, 0]$ is the mirror image of the signed area on $[0, a]$, so they double rather than cancel:
     $$\int_{-a}^{a} g(x)\,dx = 2\int_{0}^{a} g(x)\,dx \quad \text{(if } g \text{ is even)}.$$
- **Signed Area vs. Geometric Area**:
  For any function $f(x)$, $\int_a^b f(x)\,dx = F(b)-F(a)$ (evaluated via the Newton-Leibniz formula) is the **net signed area** ($A_{\text{above}} - A_{\text{below}}$), whereas $\int_a^b |f(x)|\,dx$ flips any negative part of the graph above the $x$-axis and computes the **total unsigned geometric area** ($A_{\text{above}} + A_{\text{below}}$).
- **Overview of Integration Methods**: Antiderivatives $F(x)$ (which form a family $F(x)+C$ in indefinite integration) are computed using the power rule ($\int x^n\,dx = \frac{x^{n+1}}{n+1}+C$), $u$-substitution (reversing the chain rule), or integration by parts ($\int u\,dv = uv - \int v\,du$, reversing the product rule).

## Detailed Step-by-Step Solution

### 1. Predicting the Results from Symmetry and Sketches (Before Calculating)

Both integrals are evaluated over the symmetric interval $[-2, 2]$ centered at $x = 0$.

#### Sketch and Prediction for $\int_{-2}^{2} x\,dx$
The function $f(x) = x$ is an **odd function** since $f(-x) = -x = -f(x)$.

```text
                     y = x
                       y
                       |             * (2, 2)
                   2   +            /|
                       |           / |
                   1   +          /  |   Area = +2
                       |         /   |
  -----+-------+-------*-------+-----+----> x
      -2      -1     (0,0)     1     2
       |  Area        /|
       |  = -2       / |
       |            /  |
  -1   +           /   |
       |          /    |
  -2   +         /     |
       *--------/------+
    (-2,-2)
```

- On $[-2, 0]$, the line $y = x$ lies **below** the $x$-axis, forming a right triangle with base on $[-2, 0]$ (base length $2$) and vertical leg of length $2$, which contributes a **negative signed area** of $-\frac{1}{2}(2)(2) = -2$.
- On $[0, 2]$, the line $y = x$ lies **above** the $x$-axis, forming a congruent right triangle with base on $[0, 2]$ (base length $2$) and vertical leg of length $2$, which contributes a **positive signed area** of $+\frac{1}{2}(2)(2) = +2$.
- **Prediction**: By odd symmetry, the two signed areas cancel exactly:
  $$\int_{-2}^{2} x\,dx = -2 + 2 = 0.$$

#### Sketch and Prediction for $\int_{-2}^{2} |x|\,dx$
The function $g(x) = |x|$ is an **even function** since $g(-x) = |-x| = |x| = g(x)$, and it satisfies $|x| \ge 0$ everywhere. Its graph forms a single symmetric V with its vertex at the intersection of the coordinate axes $(0, 0)$ and endpoints at $(-2, 2)$ and $(2, 2)$:

```text
                     y = |x|
                       y
     (-2, 2) *         |         * (2, 2)
             |\        |        /|
             | \       |       / |
         1   +  \      |      /  +   1
             |   \    Area   Area/
             |    \   =+2    =+2/|
             |     \   |   /     |
  -----+-----+------+--*--+------+-----+----> x
      -2    -1       (0,0)       1     2
       <--- Base 2 ---> <--- Base 2 --->
          Area = +2         Area = +2
```

- Taking the absolute value reflects the negative portion on $[-2, 0]$ across the $x$-axis so that both triangular regions lie **above** the $x$-axis, forming two base-2 right triangles that meet at the origin $(0, 0)$.
- Each right triangle (on $[-2, 0]$ and on $[0, 2]$) has base $2$ and height $2$, so each has positive geometric area $\frac{1}{2}(2)(2) = 2$.
- **Prediction**: By even symmetry, the two areas add together:
  $$\int_{-2}^{2} |x|\,dx = 2 + 2 = 4.$$

---

### 2. Carrying Out the Analytical Calculations

#### A. Exact Calculation of $\int_{-2}^{2} x\,dx$
Using the power rule ($\int x\,dx = \frac{x^2}{2}$) and the Newton-Leibniz formula:
$$\begin{aligned}
\int_{-2}^{2} x\,dx &= \left[\frac{x^2}{2}\right]_{-2}^{2} \\
&= \frac{2^2}{2} - \frac{(-2)^2}{2} \\
&= \frac{4}{2} - \frac{4}{2} = 2 - 2 = 0.
\end{aligned}$$

#### B. Exact Calculation of $\int_{-2}^{2} |x|\,dx$
By the piecewise definition of the absolute value function:
$$|x| = \begin{cases} -x, & \text{if } x < 0, \\ x, & \text{if } x \ge 0. \end{cases}$$
We split the integral at the corner point $x = 0$ where the formula changes:
$$\begin{aligned}
\int_{-2}^{2} |x|\,dx &= \int_{-2}^{0} (-x)\,dx + \int_{0}^{2} x\,dx \\
&= \left[-\frac{x^2}{2}\right]_{-2}^{0} + \left[\frac{x^2}{2}\right]_{0}^{2} \\
&= \left(0 - \left(-\frac{(-2)^2}{2}\right)\right) + \left(\frac{2^2}{2} - 0\right) \\
&= (0 + 2) + (2 - 0) = 2 + 2 = 4.
\end{aligned}$$
*(Alternatively, using even symmetry directly: $\int_{-2}^{2} |x|\,dx = 2\int_0^2 x\,dx = 2\left[\frac{x^2}{2}\right]_0^2 = 2(2) = 4$.)*

---

### 3. Explaining the Difference Between the Two Results
- $\int_{-2}^{2} x\,dx = 0$ computes the **net signed area** of $y = x$. Because $y = x$ is an odd function, the region below the $x$-axis on $[-2, 0]$ has signed area $-2$, which cancels the signed area $+2$ above the $x$-axis on $[0, 2]$. Note that a definite integral being $0$ does **not** mean the geometric area is zero!
- $\int_{-2}^{2} |x|\,dx = 4$ computes the **total unsigned geometric area** between $y = x$ and the $x$-axis on $[-2, 2]$. The absolute value converts the negative values of $x$ on $[-2, 0]$ into positive heights $|x| = -x > 0$, so both triangular regions contribute $+2$, yielding a total geometric area of $4$.

## Verification and Consistency Checks

1. **Piecewise Additivity Check for $\int_{-2}^{2} x\,dx$**:
   Splitting $\int_{-2}^{2} x\,dx$ at $x = 0$ gives:
   $$\int_{-2}^{0} x\,dx + \int_{0}^{2} x\,dx = \left[\frac{x^2}{2}\right]_{-2}^{0} + \left[\frac{x^2}{2}\right]_{0}^{2} = (0 - 2) + (2 - 0) = -2 + 2 = 0,$$
   confirming the exact cancellation of the two halves.
2. **Geometric Triangle Formula Check**:
   Each triangle has base $b = 2$ and height $h = 2$, so $A_{\triangle} = \frac{1}{2}bh = \frac{1}{2}(2)(2) = 2$.
   - Net signed area: $-A_{\triangle} + A_{\triangle} = -2 + 2 = 0$.
   - Total geometric area: $A_{\triangle} + A_{\triangle} = 2 + 2 = 4$.
   Both analytical calculations match the geometric predictions.
