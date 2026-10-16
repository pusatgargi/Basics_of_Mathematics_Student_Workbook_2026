# Problem 11: Choose the Method First

## Problem Statement

For each integral, first write which method you choose and how you recognize it, and then compute:
1. $\int\sin(3x)\,dx$,
2. $\int x\ln x\,dx$,
3. $\int\frac{x}{\sqrt{x^2+1}}\,dx$.

## Theoretical Background and Concepts

- **How to Choose an Integration Method Based on Structure**:
  1. **Direct Integration (Power Rule and Basic Table)**: Used when the integrand is a linear combination of elementary functions of $x$ alone, such as $\int x^n\,dx = \frac{x^{n+1}}{n+1}+C$ ($n \neq -1$), $\int e^x\,dx = e^x+C$, $\int \sin x\,dx = -\cos x+C$.
  2. **$u$-Substitution (Reversing the Chain Rule)**: Used when the integrand has a **composite structure** $\int f(u(x))\,u'(x)\,dx$ (or up to a constant multiple of $u'(x)$). Setting $u = u(x)$ and $du = u'(x)\,dx$ reduces the integral to $\int f(u)\,du$.
     - Special case (*linear substitution*): If the inner function is linear, $u = ax + b$, then $du = a\,dx$ is a constant, so $\int f(ax+b)\,dx = \frac{1}{a}F(ax+b) + C$.
  3. **Integration by Parts (Reversing the Product Rule)**: Used when the integrand is a **product of two different types of functions** (e.g., algebraic and logarithmic, or algebraic and trigonometric/exponential) that is *not* of chain-rule form. We apply:
     $$\int u\,dv = uv - \int v\,du,$$
     choosing $u$ so that differentiating it ($du$) simplifies the integrand (following the **LIATE** priority for $u$: **L**ogarithmic, **I**nverse trig, **A**lgebraic/polynomial, **T**rigonometric, **E**xponential), and choosing $dv$ so it can be easily integrated to $v$.
- **Definite vs. Indefinite Integrals**: In indefinite integrals, the constant of integration $C \in \mathbb{R}$ represents vertical shifts ($\frac{d}{dx}[C]=0$). In definite integrals $\int_a^b f(x)\,dx = F(b)-F(a)$ (Newton-Leibniz), the result represents net signed area rather than unsigned geometric area $\int_a^b |f(x)|\,dx$.

## Detailed Step-by-Step Solution

---

### Integral 1: $\int \sin(3x)\,dx$

#### A. Method Choice and Structural Recognition
- **Chosen Method**: **$u$-Substitution** (specifically, linear substitution reversing the chain rule).
- **How We Recognize It**: The integrand $\sin(3x)$ is a composite function with outer function $\sin(u)$ and linear inner function $u(x) = 3x$. The derivative of the inner function is a constant, $u'(x) = 3$, which differs from the existing factor $1$ only by a constant multiplier.

#### B. Step-by-Step Calculation
Let the inner argument be $u$:
$$u = 3x \implies \frac{du}{dx} = 3 \implies du = 3\,dx \implies dx = \frac{1}{3}\,du.$$
Substituting $u = 3x$ and $dx = \frac{1}{3}\,du$ into the integral:
$$\begin{aligned}
\int \sin(3x)\,dx &= \int \sin(u) \cdot \frac{1}{3}\,du \\
&= \frac{1}{3} \int \sin u\,du \\
&= \frac{1}{3}(-\cos u) + C \\
&= -\frac{1}{3}\cos(3x) + C, \quad C \in \mathbb{R}.
\end{aligned}$$

---

### Integral 2: $\int x\ln x\,dx$ (on domain $x > 0$)

#### A. Method Choice and Structural Recognition
- **Chosen Method**: **Integration by Parts** ($\int u\,dv = uv - \int v\,du$).
- **How We Recognize It**: The integrand $x\ln x$ is a product of two distinct function types—an algebraic power ($x$) and a logarithm ($\ln x$)—and neither factor is the derivative of an inner composite argument of the other. Furthermore, while $\ln x$ is not an elementary derivative on its own, its derivative $\frac{d}{dx}(\ln x) = \frac{1}{x}$ is purely algebraic! Thus, if we differentiate $u = \ln x$ and integrate $dv = x\,dx$, the new integral $\int v\,du$ becomes a simple polynomial integral without any logarithm.

#### B. Step-by-Step Calculation
Set up the four parts $u, dv, du, v$:
$$\begin{aligned}
u &= \ln x &\implies \quad du &= \frac{1}{x}\,dx, \\
dv &= x\,dx &\implies \quad v &= \int x\,dx = \frac{x^2}{2}.
\end{aligned}$$
Apply the integration-by-parts formula $\int u\,dv = uv - \int v\,du$:
$$\begin{aligned}
\int x\ln x\,dx &= (\ln x)\left(\frac{x^2}{2}\right) - \int \left(\frac{x^2}{2}\right)\left(\frac{1}{x}\,dx\right) \\
&= \frac{x^2}{2}\ln x - \frac{1}{2} \int x\,dx \\
&= \frac{x^2}{2}\ln x - \frac{1}{2}\left(\frac{x^2}{2}\right) + C \\
&= \frac{x^2}{2}\ln x - \frac{x^2}{4} + C = \frac{x^2}{4}(2\ln x - 1) + C, \quad (x > 0, \; C \in \mathbb{R}).
\end{aligned}$$

---

### Integral 3: $\int \frac{x}{\sqrt{x^2+1}}\,dx$

#### A. Method Choice and Structural Recognition
- **Chosen Method**: **$u$-Substitution** (reversing the chain rule), combined with the power rule.
- **How We Recognize It**: Inside the square root in the denominator is the quadratic expression $u(x) = x^2 + 1$. Its derivative is $u'(x) = 2x$. The numerator of the integrand is $x$, which is a constant multiple ($\frac{1}{2}$) of $u'(x) = 2x$. Therefore, the integrand has the chain-rule structure $(x^2+1)^{-1/2} \cdot x = u^{-1/2} \cdot \frac{1}{2}u'(x)$.

#### B. Step-by-Step Calculation
Let the expression inside the square root be $u$:
$$u = x^2 + 1 \implies \frac{du}{dx} = 2x \implies du = 2x\,dx \implies x\,dx = \frac{1}{2}\,du.$$
Rewrite the radical as a fractional power and substitute $u$ and $x\,dx$:
$$\begin{aligned}
\int \frac{x}{\sqrt{x^2+1}}\,dx &= \int (x^2+1)^{-1/2} \cdot (x\,dx) \\
&= \int u^{-1/2} \cdot \left(\frac{1}{2}\,du\right) \\
&= \frac{1}{2} \int u^{-1/2}\,du.
\end{aligned}$$
Apply the power rule $\int u^n\,du = \frac{u^{n+1}}{n+1} + C$ with $n = -\frac{1}{2}$:
$$\begin{aligned}
\frac{1}{2} \int u^{-1/2}\,du &= \frac{1}{2} \cdot \frac{u^{-\frac{1}{2}+1}}{-\frac{1}{2}+1} + C \\
&= \frac{1}{2} \cdot \frac{u^{1/2}}{\frac{1}{2}} + C \\
&= u^{1/2} + C \\
&= \sqrt{x^2+1} + C, \quad C \in \mathbb{R}.
\end{aligned}$$

## Verification and Consistency Checks

We explicitly differentiate each of the three results to verify that we recover the original integrands:

1. **Verification of Integral 1**:
   $$\begin{aligned}
   \frac{d}{dx}\left[-\frac{1}{3}\cos(3x) + C\right] &= -\frac{1}{3} \cdot \bigl(-\sin(3x)\bigr) \cdot \frac{d}{dx}(3x) + 0 \quad \text{(Chain Rule)} \\
   &= \frac{1}{3}\sin(3x) \cdot 3 = \sin(3x). \quad \checkmark
   \end{aligned}$$

2. **Verification of Integral 2 (for $x > 0$)**:
   $$\begin{aligned}
   \frac{d}{dx}\left[\frac{x^2}{2}\ln x - \frac{x^2}{4} + C\right] &= \left[\left(\frac{d}{dx}\frac{x^2}{2}\right)\ln x + \frac{x^2}{2}\left(\frac{d}{dx}\ln x\right)\right] - \frac{2x}{4} + 0 \quad \text{(Product Rule)} \\
   &= x\ln x + \frac{x^2}{2} \cdot \frac{1}{x} - \frac{x}{2} \\
   &= x\ln x + \frac{x}{2} - \frac{x}{2} = x\ln x. \quad \checkmark
   \end{aligned}$$

3. **Verification of Integral 3**:
   $$\begin{aligned}
   \frac{d}{dx}\left[(x^2+1)^{1/2} + C\right] &= \frac{1}{2}(x^2+1)^{\frac{1}{2}-1} \cdot \frac{d}{dx}(x^2+1) + 0 \quad \text{(Chain Rule)} \\
   &= \frac{1}{2}(x^2+1)^{-1/2} \cdot (2x) = \frac{x}{\sqrt{x^2+1}}. \quad \checkmark
   \end{aligned}$$
