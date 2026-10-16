# Problem 5: The Same Substitution in a Different Context

## Problem Statement

Compute
$$\int xe^{x^2}\,dx.$$
First compare the structure with Problem 4 and explain what is common despite the different appearance of the function.

## Theoretical Background and Concepts

- **$u$-Substitution as Reversing the Chain Rule**: By the chain rule, $\frac{d}{dx}[F(u(x))] = f(u(x))u'(x)$, where $F'(u) = f(u)$. Reversing this process yields the substitution formula:
  $$\int f(u(x))\,u'(x)\,dx = \int f(u)\,du = F(u) + C.$$
  Crucially, this mechanism depends on the **composite structure** $f(u(x)) \cdot u'(x)$, **not** on which particular outer function $f(u)$ is present (whether $f(u)$ is a power $u^n$, an exponential $e^u$, or a trigonometric function $\cos u$).
- **Adjusting for Constant Factors in Substitution**: If the integrand contains $u'(x)$ up to a non-zero constant multiplier $k$—for instance, if $du = k \cdot g(x)\,dx$—we can divide by $k$ to write $g(x)\,dx = \frac{1}{k}\,du$ and factor $\frac{1}{k}$ out of the integral by linearity.
- **Broader Calculus Context**: In all indefinite integrals, the constant of integration $C \in \mathbb{R}$ represents the family of vertical shifts ($\frac{d}{dx}[C]=0$). Other foundational tools include the power rule ($\int u^n\,du = \frac{u^{n+1}}{n+1}+C$), integration by parts ($\int u\,dv = uv - \int v\,du$, reversing the product rule), and the Newton-Leibniz formula ($\int_a^b f(x)\,dx = F(b)-F(a)$) for definite integrals, which measures net signed area rather than unsigned geometric area.

## Detailed Step-by-Step Solution

### 1. Comparing the Structure with Problem 4 and Recognizing the Method
Let us compare the integrand in Problem 4 with the integrand in Problem 5 side by side:

| Feature | Problem 4: $\int 2x(x^2+1)^4\,dx$ | Problem 5: $\int xe^{x^2}\,dx$ |
| :--- | :--- | :--- |
| **Composite expression** | $(x^2+1)^4$ | $e^{x^2}$ |
| **Inner function $u(x)$** | $u = x^2 + 1$ | $u = x^2$ |
| **Derivative $u'(x)$** | $u'(x) = 2x$ | $u'(x) = 2x$ |
| **Outside factor in integrand** | $2x = u'(x)$ | $x = \frac{1}{2}u'(x)$ |
| **Outer function $f(u)$** | Power function: $f(u) = u^4$ | Exponential function: $f(u) = e^u$ |

**What is common despite the different appearance:**
1. Both integrands are products of a **composite function** $f(u(x))$ whose inner argument is quadratic in $x$ ($x^2+1$ vs. $x^2$) and a **linear outside factor** ($2x$ vs. $x$).
2. Because the derivative of both $x^2+1$ and $x^2$ is $2x$, the outside factor $x$ in Problem 5 is proportional to the derivative of the inner exponent $x^2$, differing only by a constant factor of $2$.
3. Therefore, despite replacing the algebraic power $(x^2+1)^4$ with the transcendental exponential $e^{x^2}$, the underlying chain-rule structure $\int f(u(x))\,u'(x)\,dx$ is identical, so we recognize **$u$-substitution** as the exact method to use.

### 2. Setting Up the Substitution ($u$ and $du$)
Choose the inner function (the exponent of $e^{x^2}$) as our new variable:
$$u = x^2.$$
Compute the differential $du$:
$$\frac{du}{dx} = 2x \implies du = 2x\,dx.$$
Solving for the factor $x\,dx$ that actually appears in our integral:
$$x\,dx = \frac{1}{2}\,du.$$

### 3. Transforming and Computing the Integral
Substitute $u = x^2$ and $x\,dx = \frac{1}{2}\,du$ into the integral:
$$\begin{aligned}
\int xe^{x^2}\,dx &= \int e^{x^2} \cdot (x\,dx) \\
&= \int e^u \cdot \left(\frac{1}{2}\,du\right) \\
&= \frac{1}{2} \int e^u\,du.
\end{aligned}$$
Since $\frac{d}{du}(e^u) = e^u$, the antiderivative of $e^u$ with respect to $u$ is simply $e^u + C$:
$$\frac{1}{2} \int e^u\,du = \frac{1}{2}e^u + C.$$

### 4. Back-Substituting to the Original Variable $x$
Replacing $u$ with $x^2$, we obtain the final family of antiderivatives:
$$\int xe^{x^2}\,dx = \frac{1}{2}e^{x^2} + C, \quad C \in \mathbb{R}.$$

## Verification and Consistency Checks

We verify our result $F(x) = \frac{1}{2}e^{x^2} + C$ by differentiating it with respect to $x$ using the **Chain Rule**:

$$\begin{aligned}
F'(x) &= \frac{d}{dx}\left(\frac{1}{2}e^{x^2} + C\right) \\
&= \frac{1}{2} \cdot \frac{d}{dx}\left(e^{x^2}\right) + \frac{d}{dx}(C) \\
&= \frac{1}{2} \cdot e^{x^2} \cdot \frac{d}{dx}(x^2) + 0 \quad \text{(by the Chain Rule)} \\
&= \frac{1}{2} e^{x^2} \cdot (2x) \\
&= xe^{x^2}.
\end{aligned}$$

The factor of $2$ from differentiating the inner exponent $x^2$ cancels the coefficient $\frac{1}{2}$, recovering the exact original integrand $xe^{x^2}$.
