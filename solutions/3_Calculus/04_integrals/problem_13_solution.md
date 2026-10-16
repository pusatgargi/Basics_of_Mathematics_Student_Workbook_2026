# Problem 13: An Integral Depending on the Upper Limit

## Problem Statement

Let
$$F(x)=\int_0^x(t^2+1)\,dt.$$
Determine $F(x)$, compute $F'(x)$, and compare the result with the integrand. Explain in your own words why the height of the function describes the local rate of increase of the accumulated area.

## Theoretical Background and Concepts

- **The Area Accumulation Function and the First Fundamental Theorem of Calculus**:
  Let $f(t)$ be a continuous function on an interval $I$ containing $a$. The **accumulation function** defined by integrating $f(t)$ from a fixed lower limit $a$ to a variable upper limit $x$:
  $$F(x) = \int_a^x f(t)\,dt$$
  is differentiable with respect to $x$, and its derivative at any point $x$ is simply the integrand evaluated at the upper limit $t = x$:
  $$F'(x) = \frac{d}{dx}\int_a^x f(t)\,dt = f(x).$$
  This shows that every continuous function $f(x)$ has an antiderivative, and that differentiation and integration are inverse operations.
- **Connection to the Newton-Leibniz Formula (Second Fundamental Theorem of Calculus)**:
  If $G(t)$ is any antiderivative of $f(t)$ (so $G'(t) = f(t)$, determined up to a constant of integration $C \in \mathbb{R}$), then by Newton-Leibniz:
  $$F(x) = \int_a^x f(t)\,dt = \bigl[G(t)\bigr]_{t=a}^{t=x} = G(x) - G(a).$$
  Since $G(a)$ is a constant, differentiating $F(x)$ with respect to $x$ gives $F'(x) = G'(x) - 0 = f(x)$.
- **Summary of Core Integration Concepts**: Antiderivatives are computed using the power rule ($\int t^n\,dt = \frac{t^{n+1}}{n+1}+C$), $u$-substitution (reversing the chain rule), or integration by parts ($\int u\,dv = uv - \int v\,du$, reversing the product rule). Definite integrals represent net signed area ($A_{\text{above}} - A_{\text{below}}$), which coincides with geometric area when $f(t) \ge 0$.

## Detailed Step-by-Step Solution

### 1. Recognizing the Method and Determining $F(x)$ Explicitly
In the integral
$$F(x) = \int_0^x (t^2 + 1)\,dt,$$
the integration variable is the dummy variable $t$, and the upper limit of integration is $x$. Since the integrand $f(t) = t^2 + 1$ is a polynomial in $t$, we find its antiderivative with respect to $t$ using the **power rule** ($\int t^2\,dt = \frac{t^3}{3}$ and $\int 1\,dt = t$) and evaluate from $t = 0$ to $t = x$ using the **Newton-Leibniz formula**:

$$\begin{aligned}
F(x) &= \int_0^x (t^2 + 1)\,dt \\
&= \left[\frac{t^3}{3} + t\right]_{t=0}^{t=x} \\
&= \left(\frac{x^3}{3} + x\right) - \left(\frac{0^3}{3} + 0\right) \\
&= \frac{x^3}{3} + x.
\end{aligned}$$

### 2. Computing $F'(x)$ and Comparing with the Integrand
Now we differentiate our explicit formula $F(x) = \frac{x^3}{3} + x$ with respect to $x$:
$$\begin{aligned}
F'(x) &= \frac{d}{dx}\left(\frac{x^3}{3} + x\right) \\
&= \frac{1}{3} \cdot 3x^{3-1} + 1 \\
&= x^2 + 1.
\end{aligned}$$

**Comparison with the integrand**:
The original integrand is $f(t) = t^2 + 1$. When we replace the dummy variable $t$ with the upper limit $x$, we get $f(x) = x^2 + 1$, which is **identical** to $F'(x)$:
$$F'(x) = \frac{d}{dx}\int_0^x (t^2 + 1)\,dt = x^2 + 1 = f(x).$$
This directly illustrates the Fundamental Theorem of Calculus: differentiating the accumulation integral with respect to its upper limit undoes the integration and returns the original function at $x$.

### 3. Explaining Why the Height $f(x)$ Describes the Local Rate of Increase of Accumulated Area

```text
      y
      |                  / y = f(t) = t^2 + 1
      |                 /|
f(x)  + - - - - - - - -* |
      |               /| |  <-- Thin added strip of area Delta F
      |   F(x)       / | |      Height ~= f(x), Width = Delta x
    1 *-------------/  | |      Delta F ~= f(x) * Delta x
      |            |   | |
    0 +------------+---+-+---> t
      0                x x+Delta x
```

Imagine $F(x)$ as the area under the graph $y = f(t)$ between $t = 0$ and a movable vertical wall at $t = x$:
1. **Moving the boundary slightly**: Suppose we slide the right-hand vertical wall a tiny distance $\Delta x$ to the right, from $x$ to $x + \Delta x$.
2. **Shape of the newly added area $\Delta F$**: The change in accumulated area is the narrow vertical strip between $x$ and $x + \Delta x$:
   $$\Delta F = F(x + \Delta x) - F(x) = \int_x^{x+\Delta x} f(t)\,dt.$$
3. **Approximating the strip by a rectangle**: When the step $\Delta x$ is very small, the continuous curve $y = f(t)$ barely changes height across the tiny interval $[x, x + \Delta x]$; its height throughout this narrow strip is almost equal to $f(x)$. Therefore, the strip is almost a thin rectangle of **height $f(x)$** and **width $\Delta x$**:
   $$\Delta F \approx \text{height} \times \text{width} = f(x) \cdot \Delta x.$$
4. **Rate of increase per unit width**: Dividing both sides by the horizontal step $\Delta x$ gives the rate at which area is gained per unit of horizontal movement:
   $$\frac{\Delta F}{\Delta x} \approx f(x).$$
   In the limit as $\Delta x \to 0$, this approximation becomes exact: $F'(x) = \lim_{\Delta x \to 0} \frac{\Delta F}{\Delta x} = f(x)$. Intuitively, the taller the curve is at $x$ (the larger $f(x)$ is), the more area a unit horizontal step sweeps out, so the height $f(x)$ is literally the instantaneous rate at which accumulated area grows!

## Verification and Consistency Checks

1. **Initial Value Check at $x = 0$**:
   When the upper limit equals the lower limit ($x = 0$), no width has been swept out, so the accumulated area must be zero:
   $$F(0) = \int_0^0 (t^2 + 1)\,dt = 0.$$
   Substituting $x = 0$ into our formula $F(x) = \frac{x^3}{3} + x$ gives $F(0) = \frac{0^3}{3} + 0 = 0$, which is completely consistent (notice that $F(x)$ is the unique antiderivative of $x^2+1$ with constant $C = 0$).
2. **Consistency with Problem 10 at $x = 2$**:
   Evaluating $F(2) = \int_0^2 (t^2+1)\,dt = \frac{2^3}{3} + 2 = \frac{14}{3}$ matches our exact definite integral from Problem 10.
3. **Difference Quotient Limit Verification**:
   Using $F(x) = \frac{x^3}{3} + x$, the small change in area is:
   $$\Delta F = F(x + \Delta x) - F(x) = \frac{(x+\Delta x)^3 - x^3}{3} + \Delta x = (x^2 + 1)\Delta x + x(\Delta x)^2 + \frac{(\Delta x)^3}{3}.$$
   Dividing by $\Delta x$ gives $\frac{\Delta F}{\Delta x} = (x^2 + 1) + x\Delta x + \frac{(\Delta x)^2}{3} \to x^2 + 1 = f(x)$ as $\Delta x \to 0$.
