# Problem 15: Recovering a Function from Its Derivative and a Condition

## Problem Statement

The function $F$ satisfies
$$F'(x)=2xe^{x^2}$$
and
$$F(0)=3.$$

1. Recognize the method needed to find the function $F$.
2. Determine the entire family of functions with the given derivative.
3. Use the condition $F(0)=3$ to determine the correct constant.
4. Verify the final result by differentiation and substitution of $x=0$.

## Theoretical Background and Concepts

- **Recovering a Function from Its Derivative (Initial Value Problem)**:
  Knowing the derivative $F'(x) = f(x)$ determines $F(x)$ up to an arbitrary **constant of integration** $C \in \mathbb{R}$:
  $$F(x) = \int f(x)\,dx = F_0(x) + C.$$
  Geometrically, the derivative specifies the slope of the curve at every $x$, producing a family of vertically shifted curves. Specifying a single point on the curve—an **initial condition** $F(x_0) = y_0$—selects the unique curve in the family that passes through $(x_0, y_0)$ and uniquely fixes the value of $C$.
- **$u$-Substitution as Reversing the Chain Rule**:
  When the derivative $f(x)$ has the composite structure $g(u(x)) \cdot u'(x)$, we reverse the chain rule $\frac{d}{dx}[G(u(x))] = g(u(x))u'(x)$ by substituting $u = u(x)$ and $du = u'(x)\,dx$:
  $$\int g(u(x))\,u'(x)\,dx = \int g(u)\,du = G(u(x)) + C.$$
- **Overview of Related Integration Concepts**: Other core techniques include the power rule ($\int x^n\,dx = \frac{x^{n+1}}{n+1}+C$) and integration by parts ($\int u\,dv = uv - \int v\,du$, reversing the product rule). Via the Newton-Leibniz formula ($\int_a^b f(x)\,dx = F(b)-F(a)$, which measures net signed area rather than unsigned geometric area), we can also write the solution to $F'(x) = f(x)$ with $F(x_0) = y_0$ directly as $F(x) = y_0 + \int_{x_0}^{x} f(t)\,dt$.

## Detailed Step-by-Step Solution

### 1. Recognizing the Method Needed to Find $F(x)$
To find $F(x)$ from its derivative $F'(x) = 2xe^{x^2}$, we must evaluate the indefinite integral:
$$F(x) = \int 2xe^{x^2}\,dx.$$
Examining the structure of the integrand $2xe^{x^2}$:
- It contains a composite exponential function $e^{x^2}$, whose **inner function** (the exponent) is $u(x) = x^2$.
- The derivative of this inner function is $u'(x) = \frac{d}{dx}(x^2) = 2x$, which appears **verbatim** as the factor multiplying $e^{x^2}$.

Because the integrand has the exact chain-rule form $e^{u(x)} \cdot u'(x)$, the appropriate method is **$u$-substitution** (reversing the chain rule).

### 2. Determining the Entire Family of Functions with the Given Derivative
We set up the substitution:
$$u = x^2 \implies \frac{du}{dx} = 2x \implies du = 2x\,dx.$$
Substituting $u = x^2$ and $du = 2x\,dx$ into the integral gives:
$$\begin{aligned}
F(x) &= \int 2xe^{x^2}\,dx \\
&= \int e^{x^2} \cdot (2x\,dx) \\
&= \int e^u\,du.
\end{aligned}$$
Since $\frac{d}{du}(e^u) = e^u$, integrating with respect to $u$ and back-substituting $u = x^2$ yields the entire one-parameter family of antiderivatives:
$$F(x) = e^u + C = e^{x^2} + C, \quad C \in \mathbb{R}.$$

### 3. Using the Condition $F(0) = 3$ to Determine the Constant $C$
We substitute $x = 0$ into our general family $F(x) = e^{x^2} + C$ and enforce the given condition $F(0) = 3$:
$$F(0) = e^{0^2} + C = 3.$$
Since $0^2 = 0$ and $e^0 = 1$ (note carefully that $e^0 = 1 \neq 0$, so $C$ is not simply $3$):
$$1 + C = 3 \implies C = 3 - 1 = 2.$$
Substituting $C = 2$ back into the family gives the unique function:
$$F(x) = e^{x^2} + 2.$$

## Verification and Consistency Checks

We verify that $F(x) = e^{x^2} + 2$ satisfies both requirements of the problem:

1. **Verification of the Derivative $F'(x) = 2xe^{x^2}$**:
   Differentiating $F(x) = e^{x^2} + 2$ with respect to $x$ using the **Chain Rule**:
   $$\begin{aligned}
   F'(x) &= \frac{d}{dx}\left(e^{x^2} + 2\right) \\
   &= \frac{d}{dx}\left(e^{x^2}\right) + \frac{d}{dx}(2) \\
   &= e^{x^2} \cdot \frac{d}{dx}(x^2) + 0 \quad \text{(by the Chain Rule)} \\
   &= e^{x^2} \cdot (2x) \\
   &= 2xe^{x^2}. \quad \checkmark
   \end{aligned}$$

2. **Verification of the Initial Condition $F(0) = 3$**:
   Evaluating $F(x) = e^{x^2} + 2$ at $x = 0$:
   $$F(0) = e^{0^2} + 2 = e^0 + 2 = 1 + 2 = 3. \quad \checkmark$$

3. **Definite Integral Accumulation Check**:
   By the Newton-Leibniz theorem, $F(x) - F(0) = \int_0^x 2te^{t^2}\,dt = \left[e^{t^2}\right]_0^x = e^{x^2} - e^0 = e^{x^2} - 1$. Therefore:
   $$F(x) = F(0) + (e^{x^2} - 1) = 3 + e^{x^2} - 1 = e^{x^2} + 2,$$
   independently confirming our solution.
