# Problem 7: Integration by Parts as Reversing the Product Rule

## Problem Statement

Compute
$$\int xe^x\,dx.$$
First write the product differentiation rule and, on that basis, explain the meaning of the integration-by-parts formula. Verify the result by differentiation.

## Theoretical Background and Concepts

- **Deriving Integration by Parts from the Product Rule**:
  Let $u(x)$ and $v(x)$ be differentiable functions. The **Product Rule** for differentiation states:
  $$\frac{d}{dx}\bigl[u(x)v(x)\bigr] = u'(x)v(x) + u(x)v'(x).$$
  Integrating both sides with respect to $x$ reverses the differentiation on the left-hand side:
  $$u(x)v(x) = \int u'(x)v(x)\,dx + \int u(x)v'(x)\,dx.$$
  Rearranging this equation to solve for $\int u(x)v'(x)\,dx$ yields the **Integration-by-Parts Formula**:
  $$\int u(x)v'(x)\,dx = u(x)v(x) - \int v(x)u'(x)\,dx.$$
  Using differential notation with $du = u'(x)\,dx$ and $dv = v'(x)\,dx$, this takes the compact standard form:
  $$\int u\,dv = uv - \int v\,du.$$
- **Summary of Core Integration Concepts**:
  - **Antiderivatives & Constant $C$**: $\int f(x)\,dx = F(x) + C$ represents all functions with derivative $f(x)$, shifted vertically by $C \in \mathbb{R}$.
  - **Power Rule**: $\int x^n\,dx = \frac{x^{n+1}}{n+1} + C$ ($n \neq -1$).
  - **$u$-Substitution vs. Integration by Parts**: $u$-substitution reverses the *chain rule* for composite products $f(u(x))u'(x)$, whereas integration by parts reverses the *product rule* for products of distinct types of functions (such as a polynomial $x$ and an exponential $e^x$).
  - **Definite Integrals**: Evaluated via the Newton-Leibniz formula $\int_a^b f(x)\,dx = F(b)-F(a)$ (or for parts: $\int_a^b u\,dv = [uv]_a^b - \int_a^b v\,du$), measuring net signed area rather than unsigned geometric area.

## Detailed Step-by-Step Solution

### 1. Explaining the Meaning of the Integration-by-Parts Formula
From the product rule
$$(uv)' = u'v + uv' \implies uv' = (uv)' - u'v,$$
we see that a single product $u(x)v'(x)$ is Generally **not** the direct derivative of $u(x)v(x)$; rather, differentiating $u(x)v(x)$ produces two terms: the desired term $u(x)v'(x)$ plus an extra "byproduct" term $u'(x)v(x)$.

The integration-by-parts formula
$$\int u\,dv = uv - \int v\,du$$
means that to integrate a product $u\,dv$:
1. We start with the full product $uv$ (whose derivative gives our target term $u\,dv$ plus the extra term $v\,du$).
2. We **subtract the integral of the extra term**, $\int v\,du$, to compensate.
3. Strategically, this trades the original integral $\int u(x)v'(x)\,dx$ for a new integral $\int v(x)u'(x)\,dx$. If we choose $u(x)$ so that its derivative $u'(x)$ is simpler than $u(x)$ (for example, differentiating $x$ gives $1$), while $v'(x)$ is easy to integrate, the new integral $\int v\,du$ becomes simple to compute.

### 2. Recognizing the Method and Choosing $u$ and $dv$
In the integral
$$\int xe^x\,dx,$$
the integrand is a product of an algebraic polynomial ($x$) and an exponential function ($e^x$). Neither factor is the derivative of an inner function of the other (since the exponent is $x$, whose derivative is $1$, not $x$), so $u$-substitution does not simplify the product. Instead, we use **integration by parts**.

We assign the factors as follows:
- Let $u = x$ (because differentiating $x$ reduces it to the constant $1$).
- Let $dv = e^x\,dx$ (because integrating $e^x$ keeps it as $e^x$).

### 3. Computing $du$ and $v$
From our choices of $u$ and $dv$, we compute:
$$\begin{aligned}
u &= x &\implies \quad du &= 1\,dx = dx, \\
dv &= e^x\,dx &\implies \quad v &= \int e^x\,dx = e^x.
\end{aligned}$$
*(Note: We do not need to add a constant of integration to $v$ at this intermediate step, as any such constant cancels out in $uv - \int v\,du$.)*

### 4. Applying the Integration-by-Parts Formula
Substituting $u = x$, $v = e^x$, and $du = dx$ into $\int u\,dv = uv - \int v\,du$:
$$\begin{aligned}
\int xe^x\,dx &= x \cdot e^x - \int e^x \cdot dx \\
&= xe^x - \int e^x\,dx \\
&= xe^x - e^x + C \\
&= (x - 1)e^x + C, \quad C \in \mathbb{R}.
\end{aligned}$$

## Verification and Consistency Checks

We verify our result $F(x) = xe^x - e^x + C$ by differentiating it with respect to $x$, applying the **Product Rule** to the first term $xe^x$:

$$\begin{aligned}
F'(x) &= \frac{d}{dx}\left(xe^x - e^x + C\right) \\
&= \frac{d}{dx}\left(xe^x\right) - \frac{d}{dx}\left(e^x\right) + \frac{d}{dx}(C) \\
&= \left[\left(\frac{d}{dx}x\right)e^x + x\left(\frac{d}{dx}e^x\right)\right] - e^x + 0 \quad \text{(by the Product Rule)} \\
&= \left(1 \cdot e^x + xe^x\right) - e^x \\
&= e^x + xe^x - e^x \\
&= xe^x.
\end{aligned}$$

Notice how differentiating $xe^x$ produces the desired integrand $xe^x$ plus the extra term $+e^x$, and differentiating the second term $-e^x$ produces $-e^x$, which cancels the extra term $+e^x$ exactly.
