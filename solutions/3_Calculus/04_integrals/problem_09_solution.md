# Problem 9: Definite Integral and Geometric Area

## Problem Statement

Compute
$$\int_{-1}^{2}x\,dx.$$
Then separately compute the areas of the parts of the graph below and above the $x$-axis and explain the difference between the definite integral and geometric area.

## Theoretical Background and Concepts

- **The Definite Integral and the Newton-Leibniz Formula (Fundamental Theorem of Calculus)**:
  If $f(x)$ is continuous on $[a,b]$ and $F(x)$ is any antiderivative of $f(x)$ (so $F'(x) = f(x)$), then the definite integral of $f(x)$ from $a$ to $b$ is given by the **Newton-Leibniz formula**:
  $$\int_a^b f(x)\,dx = \bigl[F(x)\bigr]_a^b = F(b) - F(a).$$
  Note that the constant of integration $C$ cancels out in subtraction: $(F(b)+C) - (F(a)+C) = F(b) - F(a)$.
- **Signed Area vs. Geometric Area**:
  - **Definite Integral (Net Signed Area)**: The definite integral $\int_a^b f(x)\,dx$ accumulates values $f(x)\,dx$ with their **algebraic signs**. Regions where $f(x) > 0$ (above the $x$-axis) contribute positively ($+A_{\text{above}}$), while regions where $f(x) < 0$ (below the $x$-axis) contribute negatively ($-A_{\text{below}}$):
    $$\int_a^b f(x)\,dx = A_{\text{above}} - A_{\text{below}}.$$
  - **Geometric Area (Total Unsigned Area)**: In geometry, the area of a plane figure is always non-negative. The total geometric area bounded by the graph $y = f(x)$, the $x$-axis, and the vertical lines $x = a$ and $x = b$ is the integral of the absolute value $|f(x)|$:
    $$A_{\text{geometric}} = \int_a^b |f(x)|\,dx = A_{\text{above}} + A_{\text{below}}.$$
- **Summary of Integration Techniques**: Antiderivatives $F(x)$ are found using the power rule ($\int x^n\,dx = \frac{x^{n+1}}{n+1}+C$), $u$-substitution (reversing the chain rule), or integration by parts ($\int u\,dv = uv - \int v\,du$, reversing the product rule).

## Detailed Step-by-Step Solution

### 1. Recognizing the Method and Computing the Definite Integral $\int_{-1}^{2} x\,dx$
The integrand $f(x) = x = x^1$ is a simple linear power function. Using the power rule for integration ($\int x^1\,dx = \frac{x^2}{2}$) and the **Newton-Leibniz formula**:

$$\begin{aligned}
\int_{-1}^{2} x\,dx &= \left[\frac{x^2}{2}\right]_{-1}^{2} \\
&= \frac{2^2}{2} - \frac{(-1)^2}{2} \\
&= \frac{4}{2} - \frac{1}{2} \\
&= 2 - \frac{1}{2} = \frac{3}{2} = 1.5.
\end{aligned}$$

### 2. Sketch of the Graph and Separating Regions Below and Above the $x$-Axis
The function $f(x) = x$ crosses the $x$-axis at $x = 0$:
- For $x \in [-1, 0)$, $f(x) = x < 0$, so the graph lies **below** the $x$-axis.
- For $x \in (0, 2]$, $f(x) = x > 0$, so the graph lies **above** the $x$-axis.

```text
          y
        2 +             /| (2, 2)
          |            / |
        1 +           /  |
          |          /++ |   Area above x-axis: A_above = 2
          |         /+++ |
  --------+----+---/-----+---> x
         -1    |  0   1  2
          | -- /
       -1 + | /
        (-1,-1)   Area below x-axis: A_below = 1/2
```

#### Part 1: Region Below the $x$-Axis on $[-1, 0]$
- **Signed definite integral on $[-1, 0]$**:
  $$I_1 = \int_{-1}^{0} x\,dx = \left[\frac{x^2}{2}\right]_{-1}^{0} = 0 - \frac{(-1)^2}{2} = -\frac{1}{2}.$$
- **Geometric area $A_{\text{below}}$**: Since $x \le 0$ on $[-1, 0]$, $|x| = -x$, so the positive geometric area is:
  $$A_{\text{below}} = \int_{-1}^{0} |x|\,dx = -\int_{-1}^{0} x\,dx = -\left(-\frac{1}{2}\right) = \frac{1}{2} = 0.5.$$
  Geometrically, this region is a right triangle with base $b_1 = 0 - (-1) = 1$ and height $h_1 = |-1| = 1$, so its area is $\frac{1}{2} b_1 h_1 = \frac{1}{2}(1)(1) = \frac{1}{2}$.

#### Part 2: Region Above the $x$-Axis on $[0, 2]$
- **Signed definite integral and geometric area $A_{\text{above}}$ on $[0, 2]$**: Since $x \ge 0$ on $[0, 2]$, the definite integral and the geometric area coincide:
  $$A_{\text{above}} = \int_{0}^{2} x\,dx = \left[\frac{x^2}{2}\right]_{0}^{2} = \frac{2^2}{2} - 0 = 2.$$
  Geometrically, this region is a right triangle with base $b_2 = 2 - 0 = 2$ and height $h_2 = 2$, so its area is $\frac{1}{2} b_2 h_2 = \frac{1}{2}(2)(2) = 2$.

### 3. Explaining the Difference Between the Definite Integral and Geometric Area
1. **Definite Integral (Net Signed Area)**:
   $$\int_{-1}^{2} x\,dx = \int_{-1}^{0} x\,dx + \int_{0}^{2} x\,dx = -A_{\text{below}} + A_{\text{above}} = -\frac{1}{2} + 2 = \frac{3}{2} = 1.5.$$
   The definite integral treats area below the $x$-axis as **negative** ($-\frac{1}{2}$) and area above the $x$-axis as **positive** ($+2$), computing their algebraic sum (net accumulation).
2. **Total Geometric Area (Unsigned Area)**:
   $$A_{\text{geometric}} = \int_{-1}^{2} |x|\,dx = A_{\text{below}} + A_{\text{above}} = \frac{1}{2} + 2 = \frac{5}{2} = 2.5.$$
   Geometric area measures the total physical surface enclosed between the curve and the $x$-axis regardless of whether the curve is above or below the axis, so both triangles contribute positively.

## Verification and Consistency Checks

1. **Additivity Check of the Definite Integral**:
   Splitting the integral at $x = 0$ gives:
   $$\int_{-1}^{0} x\,dx + \int_{0}^{2} x\,dx = -\frac{1}{2} + 2 = \frac{3}{2},$$
   which matches our direct evaluation $\left[\frac{x^2}{2}\right]_{-1}^{2} = \frac{3}{2}$.
2. **Antiderivative Check**:
   Differentiating $F(x) = \frac{x^2}{2}$ gives $F'(x) = \frac{2x}{2} = x$, confirming that $F(x)$ is a valid antiderivative of the integrand.
3. **Elementary Triangle Geometry Check**:
   Using $A = \frac{1}{2}\text{base}\times\text{height}$, the lower triangle has area $\frac{1}{2}(1)(1) = \frac{1}{2}$ and the upper triangle has area $\frac{1}{2}(2)(2) = 2$. Subtracting them gives $2 - \frac{1}{2} = \frac{3}{2}$ (the definite integral), and adding them gives $2 + \frac{1}{2} = \frac{5}{2}$ (the geometric area).
