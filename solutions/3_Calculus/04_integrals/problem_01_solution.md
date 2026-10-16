# Problem 1: Antiderivative and Verification

## Problem Statement

For
$$f(x)=3x^2-4x+5$$
find one antiderivative $F(x)$. Write the entire family of antiderivatives, verify the result by differentiation, and explain the meaning of the constant $C$.

## Theoretical Background and Concepts

- **Antiderivative (Primitive Function)**: A function $F(x)$ is called an *antiderivative* of a function $f(x)$ on an interval $I$ if $F$ is differentiable on $I$ and its derivative equals $f(x)$ at every point of $I$:
  $$F'(x) = f(x) \quad \text{for all } x \in I.$$
  Finding an antiderivative (antidifferentiation or integration) is the inverse operation to differentiation.
- **The Indefinite Integral and the Constant of Integration $C$**: Because the derivative of any constant is zero ($\frac{d}{dx}[C] = 0$), adding an arbitrary real constant $C$ to an antiderivative $F_0(x)$ yields another valid antiderivative. Conversely, by a consequence of the Mean Value Theorem, any two antiderivatives of the same function on a single connected interval differ only by a constant. The collection of all antiderivatives is called the **indefinite integral** and is written as:
  $$\int f(x)\,dx = F_0(x) + C, \quad C \in \mathbb{R}.$$
- **Linearity of Integration**: For any integrable functions $f(x), g(x)$ and constants $a, b \in \mathbb{R}$:
  $$\int \bigl(a f(x) + b g(x)\bigr)\,dx = a \int f(x)\,dx + b \int g(x)\,dx.$$
- **Power Rule for Integration**: By reversing the power rule for differentiation $\frac{d}{dx}[x^{n+1}] = (n+1)x^n$, we obtain for any real exponent $n \neq -1$:
  $$\int x^n\,dx = \frac{x^{n+1}}{n+1} + C.$$
- **Definite vs. Indefinite Integrals (Overview)**: While an indefinite integral $\int f(x)\,dx = F(x)+C$ represents a *family of functions*, a definite integral $\int_a^b f(x)\,dx = F(b)-F(a)$ (via the Newton-Leibniz formula) represents a *number* measuring the net signed area between the graph of $f(x)$ and the $x$-axis over $[a,b]$ (where regions above the $x$-axis contribute positively and regions below contribute negatively, in contrast to unsigned geometric area $\int_a^b |f(x)|\,dx$). Techniques for more complex integrands include $u$-substitution (reversing the chain rule) and integration by parts (reversing the product rule).

## Detailed Step-by-Step Solution

### 1. Recognizing the Integration Method
The given function $f(x) = 3x^2 - 4x + 5$ is a polynomial. Since it is a linear combination of power functions $x^2$, $x^1$, and $x^0 = 1$, no substitution or integration by parts is needed. We can apply **direct integration** using the **linearity of the integral** and the **power rule for integration** term-by-term.

### 2. Term-by-Term Antidifferentiation
We find the antiderivative of each term individually using $\int x^n\,dx = \frac{x^{n+1}}{n+1}$:

1. **Quadratic term ($3x^2$, where $n = 2$)**:
   $$\int 3x^2\,dx = 3 \int x^2\,dx = 3 \cdot \frac{x^{2+1}}{2+1} = 3 \cdot \frac{x^3}{3} = x^3.$$
2. **Linear term ($-4x$, where $n = 1$)**:
   $$\int (-4x)\,dx = -4 \int x^1\,dx = -4 \cdot \frac{x^{1+1}}{1+1} = -4 \cdot \frac{x^2}{2} = -2x^2.$$
3. **Constant term ($5 = 5x^0$, where $n = 0$)**:
   $$\int 5\,dx = 5 \int x^0\,dx = 5 \cdot \frac{x^{0+1}}{0+1} = 5x.$$

### 3. One Particular Antiderivative
Combining the individual terms and choosing the simplest constant $C = 0$, we obtain one particular antiderivative:
$$F_0(x) = x^3 - 2x^2 + 5x.$$
(Any other specific choice of constant, such as $F_1(x) = x^3 - 2x^2 + 5x + 1$, is also a valid single antiderivative.)

### 4. The Entire Family of Antiderivatives
Adding the arbitrary constant of integration $C \in \mathbb{R}$, we write the complete family of antiderivatives (the indefinite integral):
$$\int (3x^2 - 4x + 5)\,dx = F(x) = x^3 - 2x^2 + 5x + C, \quad C \in \mathbb{R}.$$

### 5. Explaining the Meaning of the Constant $C$
- **Analytical Meaning**: Differentiation measures the rate of change of a function. A constant $C$ does not change as $x$ varies, so its derivative is identically zero: $\frac{d}{dx}[C] = 0$. Consequently, knowing only the derivative $f(x) = F'(x)$ determines how the function changes at every point, but loses information about its starting height (baseline value). The constant $C$ restores all possible baseline values. To pin down a single unique value of $C$, an additional piece of information—such as an initial condition $F(x_0) = y_0$—is required.
- **Geometric Meaning**: Changing the value of $C$ shifts the graph of $y = x^3 - 2x^2 + 5x$ **vertically** up or down by $C$ units. Thus, $F(x) = x^3 - 2x^2 + 5x + C$ represents an infinite family of vertically translated curves. At any fixed horizontal coordinate $x$, the tangent lines to all curves in this family are parallel because they all share the exact same slope $F'(x) = 3x^2 - 4x + 5$.

## Verification and Consistency Checks

We verify our family of antiderivatives $F(x) = x^3 - 2x^2 + 5x + C$ by differentiating it step-by-step with respect to $x$:

$$\begin{aligned}
F'(x) &= \frac{d}{dx}\left(x^3 - 2x^2 + 5x + C\right) \\
&= \frac{d}{dx}(x^3) - 2\frac{d}{dx}(x^2) + 5\frac{d}{dx}(x) + \frac{d}{dx}(C) \\
&= 3x^{3-1} - 2(2x^{2-1}) + 5(1) + 0 \\
&= 3x^2 - 4x + 5.
\end{aligned}$$

Since $F'(x) = 3x^2 - 4x + 5 = f(x)$ for all $x \in \mathbb{R}$ and for every constant $C \in \mathbb{R}$, our antiderivative is completely verified.
