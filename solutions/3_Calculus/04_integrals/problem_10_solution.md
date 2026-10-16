# Problem 10: Definite Integral and Checking the Result

## Problem Statement

Before carrying out the exact calculation, estimate the possible range of values of the integral
$$\int_0^2(x^2+1)\,dx,$$
using
$$1\le x^2+1\le5$$
on $[0,2]$. Only then compute the integral exactly, compare the result with the earlier estimate, and explain what type of computational error such a check can detect.

## Theoretical Background and Concepts

- **Comparison and Bounding Property of the Definite Integral**:
  If a continuous function $f(x)$ satisfies the inequality
  $$m \le f(x) \le M \quad \text{for all } x \in [a, b],$$
  where $a < b$, then integrating all three parts over $[a, b]$ preserves the inequalities:
  $$\int_a^b m\,dx \le \int_a^b f(x)\,dx \le \int_a^b M\,dx \implies m(b - a) \le \int_a^b f(x)\,dx \le M(b - a).$$
  Geometrically, if a positive curve $y = f(x)$ lies between horizontal lines $y = m$ and $y = M$ over an interval of width $b - a$, the area under the curve is bounded below by the area of the inscribed rectangle $m(b - a)$ and bounded above by the area of the circumscribed rectangle $M(b - a)$.
- **Newton-Leibniz Formula (Fundamental Theorem of Calculus)**:
  To compute $\int_a^b f(x)\,dx$ exactly, we find an antiderivative $F(x)$ satisfying $F'(x) = f(x)$ (where the integration constant $C$ cancels) and evaluate $F(b) - F(a)$.
- **Summary of Integration Techniques and Interpretation**: Antiderivatives are obtained via the power rule ($\int x^n\,dx = \frac{x^{n+1}}{n+1}+C$), $u$-substitution (reversing the chain rule), or integration by parts ($\int u\,dv = uv - \int v\,du$, reversing the product rule). The definite integral computes net signed area, which equals geometric area whenever $f(x) \ge 0$ on $[a,b]$ (as is the case here since $x^2+1 \ge 1 > 0$).

## Detailed Step-by-Step Solution

### 1. Estimating the Range of Values Before Exact Calculation
On the interval $[0, 2]$, the integrand $f(x) = x^2 + 1$ is strictly increasing because $f'(x) = 2x > 0$ for $x \in (0, 2]$. Therefore:
- Its minimum value on $[0, 2]$ occurs at the left endpoint $x = 0$:
  $$m = f(0) = 0^2 + 1 = 1.$$
- Its maximum value on $[0, 2]$ occurs at the right endpoint $x = 2$:
  $$M = f(2) = 2^2 + 1 = 5.$$

Thus, for every $x \in [0, 2]$, we have the double inequality:
$$1 \le x^2 + 1 \le 5.$$
Integrating all three parts over the interval $[0, 2]$ of length $b - a = 2 - 0 = 2$:
$$\int_0^2 1\,dx \le \int_0^2 (x^2 + 1)\,dx \le \int_0^2 5\,dx$$
$$1 \cdot (2 - 0) \le \int_0^2 (x^2 + 1)\,dx \le 5 \cdot (2 - 0)$$
$$2 \le \int_0^2 (x^2 + 1)\,dx \le 10.$$
*(Furthermore, because $x^2 + 1$ is non-constant and continuous, both inequalities are strict: $2 < \int_0^2 (x^2+1)\,dx < 10$.)*

```text
      y
    5 + - - - - - - - - - - - - * (2, 5)   <-- Upper bound rectangle (height 5, width 2, Area = 10)
      |                       . |
    4 +                     .   |
      |                   .     |
    3 +                 .       |
      |               .         |          <-- Curve y = x^2 + 1 strictly above y = 1 on (0, 2]
    2 +             .           |
      |       . . '             |
    1 * - - - - - - - - - - - - +          <-- Lower bound rectangle (height 1, width 2, Area = 2)
    (0,1)                       |
    0 +-------------------------+---> x
      0             1           2
```

### 2. Recognizing the Method and Computing the Integral Exactly
The integrand $f(x) = x^2 + 1$ is a polynomial. We use **direct integration via the power rule** ($\int x^2\,dx = \frac{x^3}{3}$ and $\int 1\,dx = x$) together with the **Newton-Leibniz formula**:

$$\begin{aligned}
\int_0^2 (x^2 + 1)\,dx &= \left[\frac{x^3}{3} + x\right]_0^2 \\
&= \left(\frac{2^3}{3} + 2\right) - \left(\frac{0^3}{3} + 0\right) \\
&= \left(\frac{8}{3} + \frac{6}{3}\right) - 0 \\
&= \frac{14}{3} = 4\frac{2}{3} \approx 4.67.
\end{aligned}$$

### 3. Comparing the Exact Result with the Estimate
Our exact result is $\frac{14}{3} \approx 4.67$. Comparing this with our prior estimate $[2, 10]$:
$$2 < \frac{14}{3} \approx 4.67 < 10.$$
The exact value lies comfortably inside the predicted range $[2, 10]$ (and slightly below the midpoint $6$, which makes geometric sense because $y = x^2 + 1$ is concave upward / convex, bowing below the secant line connecting $(0, 1)$ and $(2, 5)$ whose trapezoidal area is $\frac{1+5}{2}\cdot 2 = 6$).

### 4. Explaining What Types of Computational Errors This Check Can Detect
Estimating bounds before calculating provides a fundamental qualitative check, but it is important to distinguish what it can and cannot detect:

1. **Errors Ruled Out by the Strict Bound ($2 < I < 10$)**:
   - **Sign errors / Swapped limits**: Swapping the upper and lower limits ($F(0) - F(2) = -\frac{14}{3}$) gives a negative value, immediately ruled out since the integral must be $> 2$.
   - **Subtraction instead of addition in the antiderivative**: Calculating $\frac{8}{3} - 2 = \frac{2}{3} \approx 0.67$ falls below the lower bound $2$.
   - **Missing denominator in the power rule**: Forgetting to divide by $3$ in $\int x^2\,dx$, writing $x^3 + x$, gives $[x^3 + x]_0^2 = 8 + 2 = 10$. This hits the upper bound $10$, which is ruled out because $x^2 + 1 < 5$ everywhere on $[0, 2)$.
   - **Gross arithmetic / Exponent errors**: An erroneous exponent operation such as $[3x^3 + x]_0^2 = 24 + 2 = 26$ yields a value far above the upper bound $10$.

2. **Limitations of the Bound (Necessary vs. Sufficient)**:
   - Passing the bound ($2 < I < 10$) is a **necessary condition for correctness, but not a proof of correctness**.
   - An incorrect calculation may still happen to fall within the wide interval $(2, 10)$:
     - Erroneously **differentiating** the integrand instead of integrating gives $\bigl[2x\bigr]_0^2 = 4 - 0 = 4$. Because $4 \in (2, 10)$, this bound alone does not detect the differentiation mistake.
     - **Omitting the integral of the constant term $1$** gives $\int_0^2 x^2\,dx = \bigl[\frac{x^3}{3}\bigr]_0^2 = \frac{8}{3} \approx 2.67$. Because $\frac{8}{3} \in (2, 10)$, this omission also goes undetected by this bounding rectangle alone.
   - To catch such internal errors, one must combine the bound check with an **independent derivative check** ($F'(x) = f(x)$) or tighter geometric bounds (such as the refined tangent-secant trapezoidal bounds $4 < I < 6$, which successfully catches $\frac{8}{3} < 4$).

## Verification and Consistency Checks

1. **Antiderivative Differentiation Check**:
   Differentiating $F(x) = \frac{x^3}{3} + x$ gives:
   $$F'(x) = \frac{d}{dx}\left(\frac{x^3}{3} + x\right) = \frac{3x^2}{3} + 1 = x^2 + 1,$$
   confirming the antiderivative used in the Newton-Leibniz evaluation.
2. **Refined Trapezoidal Convexity Check**:
   Since $f''(x) = 2 > 0$, the graph of $f(x) = x^2 + 1$ lies above its tangent line at $x=1$ ($y = 2x$, area $\int_0^2 2x\,dx = 4$) and below the secant line through $(0,1)$ and $(2,5)$ (trapezoid area $\frac{1+5}{2}\cdot 2 = 6$). Indeed:
   $$4 < \frac{14}{3} \approx 4.67 < 6,$$
   providing an even tighter verification of $\frac{14}{3}$.
