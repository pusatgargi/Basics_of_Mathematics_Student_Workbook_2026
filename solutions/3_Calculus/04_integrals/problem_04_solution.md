# Problem 4: Substitution as Reversing the Chain Rule

## Problem Statement

Compute
$$\int 2x(x^2+1)^4\,dx.$$
Before calculating, identify a candidate for the new variable $u$ and show that its derivative appears in the integral. Finally, verify the result by differentiation.

## Theoretical Background and Concepts

- **Antiderivatives, the Power Rule, and the Constant $C$**: An antiderivative $F(x)$ of $f(x)$ satisfies $F'(x) = f(x)$, and the general indefinite integral is $F(x) + C$ where $C \in \mathbb{R}$ represents vertical shifts ($\frac{d}{dx}[C] = 0$). For simple powers, the power rule gives $\int u^n\,du = \frac{u^{n+1}}{n+1} + C$ ($n \neq -1$).
- **Integration by Substitution ($u$-Substitution) as Reversing the Chain Rule**:
  Recall the **Chain Rule** for differentiating a composite function $F(u(x))$:
  $$\frac{d}{dx}\bigl[F(u(x))\bigr] = F'(u(x)) \cdot u'(x) = f(u(x)) \cdot u'(x),$$
  where $F'(u) = f(u)$. Integrating both sides with respect to $x$ reverses the chain rule:
  $$\int f(u(x)) \cdot u'(x)\,dx = F(u(x)) + C.$$
  By introducing the new variable $u = u(x)$ and its differential $du = u'(x)\,dx$, the integral transforms into a simpler basic integral in terms of $u$:
  $$\int f(u(x)) \cdot u'(x)\,dx = \int f(u)\,du = F(u) + C.$$
- **Comparison with Other Core Concepts**: While $u$-substitution handles products arising from the chain rule (an outer function of $u(x)$ multiplied by $u'(x)$), **integration by parts** ($\int u\,dv = uv - \int v\,du$) handles products of unrelated functions by reversing the product rule. For definite integrals $\int_a^b f(x)\,dx = F(b)-F(a)$ (Newton-Leibniz), the integral computes net signed area rather than unsigned geometric area.

## Detailed Step-by-Step Solution

### 1. Recognizing the Integration Method and Identifying $u$
While we *could* expand $(x^2+1)^4$ using the binomial theorem and integrate term-by-term, that would be tedious and would become impractical for larger exponents like $(x^2+1)^{50}$. Instead, we look at the structure of the integrand:
$$2x(x^2+1)^4.$$
It is a product of two parts:
1. A composite function $(x^2+1)^4$, which has an **inner function** $u(x) = x^2+1$ raised to the 4th power.
2. A remaining factor $2x$.

Differentiating the inner function gives:
$$u'(x) = \frac{d}{dx}(x^2+1) = 2x.$$
Because the exact derivative $u'(x) = 2x$ of the inner function appears as a factor multiplying $(x^2+1)^4$, the integrand has the exact chain-rule form $f(u(x))\,u'(x)$ with outer function $f(u) = u^4$. This immediately tells us to use **$u$-substitution**.

### 2. Setting Up the Substitution ($u$ and $du$)
Let the new variable $u$ be the inner function:
$$u = x^2 + 1.$$
Differentiating $u$ with respect to $x$:
$$\frac{du}{dx} = 2x \implies du = 2x\,dx.$$
Notice how the factor $2x$ and the differential $dx$ combine directly into $du$:
$$\int \underbrace{(x^2+1)^4}_{u^4} \cdot \underbrace{2x\,dx}_{du}.$$

### 3. Transforming and Computing the Integral
Substituting $u = x^2 + 1$ and $du = 2x\,dx$ into the integral reduces it to a basic power-rule integral in $u$:
$$\begin{aligned}
\int 2x(x^2+1)^4\,dx &= \int (x^2+1)^4 (2x\,dx) \\
&= \int u^4\,du.
\end{aligned}$$
Applying the power rule for integration ($\int u^n\,du = \frac{u^{n+1}}{n+1} + C$ with $n = 4$):
$$\int u^4\,du = \frac{u^{4+1}}{4+1} + C = \frac{u^5}{5} + C.$$

### 4. Back-Substituting to the Original Variable $x$
Replacing $u$ with $x^2 + 1$, we obtain the final family of antiderivatives in terms of $x$:
$$\int 2x(x^2+1)^4\,dx = \frac{(x^2+1)^5}{5} + C = \frac{1}{5}(x^2+1)^5 + C, \quad C \in \mathbb{R}.$$

## Verification and Consistency Checks

We verify our result $F(x) = \frac{1}{5}(x^2+1)^5 + C$ by differentiating it with respect to $x$ using the **Chain Rule**:

$$\begin{aligned}
F'(x) &= \frac{d}{dx}\left[\frac{1}{5}(x^2+1)^5 + C\right] \\
&= \frac{1}{5} \cdot \frac{d}{dx}\left[(x^2+1)^5\right] + \frac{d}{dx}(C) \\
&= \frac{1}{5} \cdot 5(x^2+1)^{5-1} \cdot \frac{d}{dx}(x^2+1) + 0 \quad \text{(by the Chain Rule)} \\
&= (x^2+1)^4 \cdot (2x + 0) \\
&= 2x(x^2+1)^4.
\end{aligned}$$

We see explicitly how the factor of $5$ cancels $\frac{1}{5}$ via the outer power derivative, while the chain rule multiplies by the inner derivative $2x$, recovering the original integrand $2x(x^2+1)^4$.
