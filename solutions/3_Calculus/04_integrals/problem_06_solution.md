# Problem 6: When Does a Logarithm Appear from an Integral?

## Problem Statement

Compute
$$\int\frac{2x}{x^2+5}\,dx.$$
Identify the denominator as a candidate for substitution, compare the numerator with its derivative, and explain the source of the logarithm in the result.

## Theoretical Background and Concepts

- **Logarithmic Integration and the Exception to the Power Rule**:
  The standard power rule for integration states that for $n \neq -1$:
  $$\int u^n\,du = \frac{u^{n+1}}{n+1} + C.$$
  When $n = -1$ (i.e., $\int u^{-1}\,du = \int \frac{1}{u}\,du$), the power rule formula would divide by $n + 1 = 0$, which is undefined. This gap is filled by the natural logarithm: since $\frac{d}{du}(\ln|u|) = \frac{1}{u}$ for all $u \neq 0$, reversing this derivative gives:
  $$\int \frac{1}{u}\,du = \ln|u| + C.$$
- **Recognizing $\int \frac{u'(x)}{u(x)}\,dx$ via $u$-Substitution (Reversing the Chain Rule)**:
  By combining the logarithmic derivative with the chain rule, we have:
  $$\frac{d}{dx}\bigl[\ln|u(x)|\bigr] = \frac{1}{u(x)} \cdot u'(x) = \frac{u'(x)}{u(x)}.$$
  Therefore, whenever an integrand is a fraction whose **numerator is the derivative of the denominator** (or a constant multiple of it), setting $u = \text{denominator}$ and $du = u'(x)\,dx$ yields:
  $$\int \frac{u'(x)}{u(x)}\,dx = \int \frac{1}{u}\,du = \ln|u(x)| + C.$$
- **Overview of Related Integration Concepts**: The constant $C \in \mathbb{R}$ represents vertical translations of the antiderivative ($\frac{d}{dx}[C]=0$). While $u$-substitution reverses the chain rule, integration by parts ($\int u\,dv = uv - \int v\,du$) reverses the product rule. In definite integration $\int_a^b f(x)\,dx = F(b)-F(a)$ (Newton-Leibniz), the result represents net signed area rather than unsigned geometric area.

## Detailed Step-by-Step Solution

### 1. Recognizing the Integration Method and Comparing Numerator and Denominator
We examine the rational integrand:
$$f(x) = \frac{2x}{x^2+5}.$$
1. **Candidate for substitution**: Let the denominator be $u(x) = x^2 + 5$.
2. **Comparison with the numerator**: Differentiating the denominator with respect to $x$ gives:
   $$u'(x) = \frac{d}{dx}(x^2 + 5) = 2x.$$
   This is **identical** to the numerator $2x$! Thus, the integrand has the exact logarithmic derivative structure $\frac{u'(x)}{u(x)}$, which indicates **$u$-substitution** with $u$ equal to the denominator.

### 2. Setting Up the Substitution ($u$ and $du$)
Let
$$u = x^2 + 5.$$
Then the differential is:
$$du = \frac{d}{dx}(x^2 + 5)\,dx = 2x\,dx.$$

### 3. Transforming and Computing the Integral
Substituting $u = x^2 + 5$ into the denominator and $du = 2x\,dx$ for the numerator and differential gives:
$$\begin{aligned}
\int \frac{2x}{x^2+5}\,dx &= \int \frac{1}{x^2+5} \cdot (2x\,dx) \\
&= \int \frac{1}{u}\,du \\
&= \ln|u| + C.
\end{aligned}$$

### 4. Explaining the Source of the Logarithm and Back-Substituting
**Why does a logarithm appear?**
After substituting $u = x^2 + 5$, the integral reduces to $\int u^{-1}\,du = \int \frac{1}{u}\,du$. Unlike every other power $u^n$ ($n \neq -1$), the power $u^{-1}$ cannot come from differentiating a power function $u^{n+1}$, because differentiating $u^0 = 1$ gives $0$, not $u^{-1}$. Instead, $\frac{1}{u}$ is the derivative of the natural logarithm $\ln|u|$. Thus, the logarithm appears whenever $u$-substitution reduces a fraction to the reciprocal function $\frac{1}{u}$.

Finally, we substitute $u = x^2 + 5$ back into $\ln|u| + C$:
$$\int \frac{2x}{x^2+5}\,dx = \ln|x^2 + 5| + C.$$
Since $x^2 \ge 0$ for all real $x$, we have $x^2 + 5 \ge 5 > 0$ everywhere on $\mathbb{R}$. Because the argument is strictly positive for all $x \in \mathbb{R}$, the absolute value bars can be replaced with ordinary parentheses:
$$\int \frac{2x}{x^2+5}\,dx = \ln(x^2 + 5) + C, \quad C \in \mathbb{R}.$$

## Verification and Consistency Checks

We verify our antiderivative $F(x) = \ln(x^2 + 5) + C$ by differentiating it with respect to $x$ using the **Chain Rule** and the derivative of the natural logarithm $\frac{d}{du}(\ln u) = \frac{1}{u}$:

$$\begin{aligned}
F'(x) &= \frac{d}{dx}\bigl[\ln(x^2 + 5) + C\bigr] \\
&= \frac{d}{dx}\bigl[\ln(x^2 + 5)\bigr] + \frac{d}{dx}(C) \\
&= \frac{1}{x^2 + 5} \cdot \frac{d}{dx}(x^2 + 5) + 0 \quad \text{(by the Chain Rule)} \\
&= \frac{1}{x^2 + 5} \cdot (2x) \\
&= \frac{2x}{x^2 + 5}.
\end{aligned}$$

The derivative reproduces the exact original integrand $\frac{2x}{x^2+5}$ for all $x \in \mathbb{R}$.
