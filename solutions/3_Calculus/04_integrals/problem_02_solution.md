# Problem 2: Powers, Roots, and the Domain

## Problem Statement

Compute
$$\int\left(2\sqrt{x}+\frac{3}{x^2}-x^{1/3}\right)\,dx.$$
First rewrite the terms as powers, determine the domain of the original expression, and verify the result by differentiation.

## Theoretical Background and Concepts

- **Antiderivatives and the Constant of Integration $C$**: An antiderivative $F(x)$ of $f(x)$ on an interval $I$ satisfies $F'(x) = f(x)$ for all $x \in I$. Because $\frac{d}{dx}[C] = 0$, the indefinite integral on a connected interval $I$ is the family $\int f(x)\,dx = F(x) + C$.
- **Power Rule for Integration**: For any real exponent $n \neq -1$, reversing the differentiation power rule gives:
  $$\int x^n\,dx = \frac{x^{n+1}}{n+1} + C.$$
- **Algebraic Laws of Exponents for Radicals and Reciprocals**: Before applying the power rule, radicals and fractions with powers of $x$ in the denominator are rewritten in standard power form $x^n$:
  $$\sqrt[m]{x^k} = x^{k/m}, \qquad \frac{1}{x^k} = x^{-k}.$$
- **Role of the Domain in Integration**: An integrand must be defined on an interval before we talk about its antiderivatives. Moreover, when a domain is split by a discontinuity (such as $x = 0$), the constant $C$ is only guaranteed to be constant on each connected component (interval) of the domain.
- **Broader Integration Framework**: Beyond direct power-rule integration, more general integrands use $u$-substitution (reversing the chain rule $\frac{d}{dx}[F(u(x))] = f(u(x))u'(x)$) and integration by parts (reversing the product rule $\int u\,dv = uv - \int v\,du$). For definite integrals $\int_a^b f(x)\,dx = F(b) - F(a)$ (Newton-Leibniz formula), the result represents net signed area rather than unsigned geometric area $\int_a^b |f(x)|\,dx$.

## Detailed Step-by-Step Solution

### 1. Recognizing the Integration Method
Although the integrand
$$f(x) = 2\sqrt{x} + \frac{3}{x^2} - x^{1/3}$$
contains a square root, a rational fraction, and a fractional power, each term can be expressed as a constant times a power $x^n$ with $n \neq -1$. Therefore, **direct integration via the power rule** (combined with linearity) is the appropriate method once the terms are rewritten using exponent laws.

### 2. Determining the Domain of the Original Expression
We inspect the domain requirements of each of the three terms in $f(x)$:
1. **First term ($2\sqrt{x}$)**: The square root $\sqrt{x}$ is defined in the real numbers if and only if $x \ge 0$, so $x \in [0, \infty)$.
2. **Second term ($\frac{3}{x^2}$)**: Division by zero is undefined, which requires $x^2 \neq 0 \iff x \neq 0$.
3. **Third term ($-x^{1/3}$)**: As a cube root $\sqrt[3]{x}$, it is defined for all $x \in \mathbb{R}$ (and under the strict real fractional power convention $x^r = e^{r\ln x}$, it is defined for $x > 0$).

Taking the intersection of all three conditions ($x \ge 0$ and $x \neq 0$), the domain of the original integrand is the open positive half-line:
$$D_f = (0, \infty) = \{x \in \mathbb{R} : x > 0\}.$$
Because $(0, \infty)$ is a single connected interval, a single arbitrary constant $C \in \mathbb{R}$ describes the entire family of antiderivatives on this domain.

### 3. Rewriting the Terms as Powers of $x$
For $x > 0$, we convert each term into the form $a x^n$:
- $2\sqrt{x} = 2x^{1/2}$
- $\frac{3}{x^2} = 3x^{-2}$
- $-x^{1/3} = -x^{1/3}$

Substituting these into the integral gives:
$$\int\left(2\sqrt{x}+\frac{3}{x^2}-x^{1/3}\right)\,dx = \int\left(2x^{1/2} + 3x^{-2} - x^{1/3}\right)\,dx.$$

### 4. Computing the Antiderivative Term-by-Term
By linearity and the power rule $\int x^n\,dx = \frac{x^{n+1}}{n+1}$:

1. **First term ($n = \frac{1}{2}$)**:
   $$\int 2x^{1/2}\,dx = 2 \cdot \frac{x^{\frac{1}{2} + 1}}{\frac{1}{2} + 1} = 2 \cdot \frac{x^{3/2}}{\frac{3}{2}} = 2 \cdot \frac{2}{3}x^{3/2} = \frac{4}{3}x^{3/2} = \frac{4}{3}x\sqrt{x}.$$

2. **Second term ($n = -2$)**:
   $$\int 3x^{-2}\,dx = 3 \cdot \frac{x^{-2 + 1}}{-2 + 1} = 3 \cdot \frac{x^{-1}}{-1} = -3x^{-1} = -\frac{3}{x}.$$

3. **Third term ($n = \frac{1}{3}$)**:
   $$\int \left(-x^{1/3}\right)\,dx = -\frac{x^{\frac{1}{3} + 1}}{\frac{1}{3} + 1} = -\frac{x^{4/3}}{\frac{4}{3}} = -\frac{3}{4}x^{4/3} = -\frac{3}{4}x\sqrt[3]{x}.$$

### 5. Final Result
Combining all terms and including the constant of integration $C \in \mathbb{R}$ on the domain $x > 0$:
$$\int\left(2\sqrt{x}+\frac{3}{x^2}-x^{1/3}\right)\,dx = \frac{4}{3}x^{3/2} - \frac{3}{x} - \frac{3}{4}x^{4/3} + C = \frac{4}{3}x\sqrt{x} - \frac{3}{x} - \frac{3}{4}x\sqrt[3]{x} + C, \quad (x > 0).$$

## Verification and Consistency Checks

We differentiate our result $F(x) = \frac{4}{3}x^{3/2} - 3x^{-1} - \frac{3}{4}x^{4/3} + C$ term-by-term for $x > 0$:

$$\begin{aligned}
F'(x) &= \frac{d}{dx}\left(\frac{4}{3}x^{3/2} - 3x^{-1} - \frac{3}{4}x^{4/3} + C\right) \\
&= \frac{4}{3} \cdot \frac{d}{dx}\left(x^{3/2}\right) - 3 \cdot \frac{d}{dx}\left(x^{-1}\right) - \frac{3}{4} \cdot \frac{d}{dx}\left(x^{4/3}\right) + \frac{d}{dx}(C) \\
&= \frac{4}{3} \cdot \left(\frac{3}{2}x^{\frac{3}{2}-1}\right) - 3 \cdot \left(-1 \cdot x^{-1-1}\right) - \frac{3}{4} \cdot \left(\frac{4}{3}x^{\frac{4}{3}-1}\right) + 0 \\
&= 2x^{1/2} + 3x^{-2} - x^{1/3} \\
&= 2\sqrt{x} + \frac{3}{x^2} - x^{1/3}.
\end{aligned}$$

The derivative matches the original integrand $f(x)$ identically on its domain $x > 0$. Also notice that $F(x)$ is well-defined and differentiable on $(0, \infty)$, consistent with the domain of $f(x)$.
