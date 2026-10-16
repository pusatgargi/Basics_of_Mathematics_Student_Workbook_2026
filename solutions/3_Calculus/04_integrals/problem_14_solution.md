# Problem 14: A Piecewise-Defined Function

## Problem Statement

Let
$$f(x)=\begin{cases}x+1,&-1\le x<1,\\2,&1\le x\le3.\end{cases}$$
Sketch the graph, decide where to split the integral, compute
$$\int_{-1}^{3}f(x)\,dx$$
and verify the result geometrically.

## Theoretical Background and Concepts

- **Interval Additivity of the Definite Integral**:
  For any function $f(x)$ integrable on $[a, b]$ and any interior point $c \in (a, b)$, the definite integral over $[a, b]$ is the sum of the definite integrals over the subintervals $[a, c]$ and $[c, b]$:
  $$\int_a^b f(x)\,dx = \int_a^c f(x)\,dx + \int_c^b f(x)\,dx.$$
  This property is essential for **piecewise-defined functions**: we split the integral at the boundary points where the formula defining $f(x)$ changes, and then apply the **Newton-Leibniz formula** $\int_{x_1}^{x_2} g(x)\,dx = G(x_2) - G(x_1)$ on each subinterval using the formula valid on that subinterval.
  *(Note: Changing the value of a function at a single point, such as whether $x=1$ uses $x+1$ or $2$, has zero width and does not affect the value of the definite integral; here both pieces agree at $x=1$ since $1+1=2$.)*
- **Signed Area vs. Geometric Area**:
  When $f(x) \ge 0$ on the entire interval $[a, b]$, the net signed area $\int_a^b f(x)\,dx$ equals the unsigned geometric area of the region under the graph $y = f(x)$, allowing us to verify the integral using elementary area formulas (triangles, rectangles, trapezoids).
- **Overview of Antiderivative Techniques**: On each subinterval, antiderivatives (which generally include a constant $C \in \mathbb{R}$ that cancels in definite integrals) are found using the power rule ($\int x^n\,dx = \frac{x^{n+1}}{n+1}+C$), $u$-substitution (reversing the chain rule), or integration by parts ($\int u\,dv = uv - \int v\,du$, reversing the product rule).

## Detailed Step-by-Step Solution

### 1. Sketching the Graph of $f(x)$
Let us analyze the two pieces of $f(x)$ on $[-1, 3]$:
1. **First piece ($-1 \le x < 1$)**: $f(x) = x + 1$ is a linear function with slope $1$.
   - At $x = -1$: $f(-1) = -1 + 1 = 0$.
   - As $x \to 1^-$: $x + 1 \to 1 + 1 = 2$.
2. **Second piece ($1 \le x \le 3$)**: $f(x) = 2$ is a constant function (a horizontal line at height $y = 2$).
   - At $x = 1$: $f(1) = 2$ (so the two pieces meet continuously at $(1, 2)$).
   - At $x = 3$: $f(3) = 2$.

```text
          y
        3 +
          |
        2 +             *-------------* (3, 2)
          |            /| (1, 2)      |
        1 +           / |             |
          |         /   |  Rectangle  |
          |       /Tri- |  Area = 4   |
          |     / angle |             |
          |   / Area=2  |             |
  --------+--*----------+------+------+---> x
         -1  0          1      2      3
       (-1,0)
```

### 2. Deciding Where to Split the Integral
Because the algebraic formula for $f(x)$ changes at **$x = 1$** (from $f(x) = x + 1$ on $[-1, 1)$ to $f(x) = 2$ on $[1, 3]$), a single antiderivative formula cannot be written with one algebraic expression across the whole interval $[-1, 3]$. Therefore, we split the integral at the transition point **$x = 1$**:
$$\int_{-1}^{3} f(x)\,dx = \int_{-1}^{1} f(x)\,dx + \int_{1}^{3} f(x)\,dx = \int_{-1}^{1} (x + 1)\,dx + \int_{1}^{3} 2\,dx.$$

### 3. Computing the Definite Integral Analytically
We evaluate each sub-integral using the power rule for integration and the Newton-Leibniz formula:

1. **First sub-integral on $[-1, 1]$**:
   $$\begin{aligned}
   \int_{-1}^{1} (x + 1)\,dx &= \left[\frac{x^2}{2} + x\right]_{-1}^{1} \\
   &= \left(\frac{1^2}{2} + 1\right) - \left(\frac{(-1)^2}{2} + (-1)\right) \\
   &= \left(\frac{1}{2} + 1\right) - \left(\frac{1}{2} - 1\right) \\
   &= \frac{3}{2} - \left(-\frac{1}{2}\right) = \frac{4}{2} = 2.
   \end{aligned}$$

2. **Second sub-integral on $[1, 3]$**:
   $$\begin{aligned}
   \int_{1}^{3} 2\,dx &= \bigl[2x\bigr]_{1}^{3} \\
   &= 2(3) - 2(1) \\
   &= 6 - 2 = 4.
   \end{aligned}$$

3. **Combining both parts**:
   $$\int_{-1}^{3} f(x)\,dx = 2 + 4 = 6.$$

## Verification and Consistency Checks

### Geometric Verification
Since $f(x) \ge 0$ for all $x \in [-1, 3]$, the definite integral $\int_{-1}^{3} f(x)\,dx$ equals the geometric area under the graph of $f(x)$ from $x = -1$ to $x = 3$:

1. **Area on $[-1, 1]$ (Right Triangle)**:
   The region under $y = x + 1$ from $x = -1$ to $x = 1$ is a right triangle with:
   - Base $b_1 = 1 - (-1) = 2$,
   - Height $h_1 = 2$.
   Its area is:
   $$A_1 = \frac{1}{2} \cdot b_1 \cdot h_1 = \frac{1}{2} \cdot 2 \cdot 2 = 2,$$
   which matches $\int_{-1}^{1} (x+1)\,dx = 2$.

2. **Area on $[1, 3]$ (Square/Rectangle)**:
   The region under $y = 2$ from $x = 1$ to $x = 3$ is a rectangle with:
   - Width $w_2 = 3 - 1 = 2$,
   - Height $h_2 = 2$.
   Its area is:
   $$A_2 = w_2 \cdot h_2 = 2 \cdot 2 = 4,$$
   which matches $\int_{1}^{3} 2\,dx = 4$.

3. **Total Area (or Single Trapezoid Check)**:
   Summing the two parts gives $A_{\text{total}} = A_1 + A_2 = 2 + 4 = 6$.
   Alternatively, viewing the entire region on $[-1, 3]$ as a single trapezoid with bottom base $B_1 = 3 - (-1) = 4$, top base $B_2 = 3 - 1 = 2$, and height $H = 2$:
   $$A_{\text{trapezoid}} = \frac{B_1 + B_2}{2} \cdot H = \frac{4 + 2}{2} \cdot 2 = 3 \cdot 2 = 6.$$
   Both geometric calculations confirm our analytical result of $6$.
