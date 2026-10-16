# Problem 12: Exponential Function Limit

## Problem Statement

Compute
$$\lim_{x\to0}(1+3x)^{1/x}.$$
Connect the result with the limit from Exercise 5 and show the appropriate transformation.

## Theoretical Background and Concepts

In Exercise 5, we studied the classical sequence limit defining Euler's number $e$:
$$\lim_{n\to\infty} \left(1 + \frac{1}{n}\right)^n = e.$$
This fundamental result extends from discrete integer indices $n \to \infty$ to a continuous real variable $t \to \pm\infty$ or $u \to 0$:
$$\lim_{t\to\pm\infty} \left(1 + \frac{1}{t}\right)^t = e \qquad \Longleftrightarrow \qquad \lim_{u\to 0} (1 + u)^{1/u} = e.$$

Notice the structural pattern of the classical limit $\lim_{u\to 0} (1 + u)^{1/u} = e$:
> Whenever a quantity $u(x) \to 0$ (with $u(x) \neq 0$) appears added to $1$ in the base as $1 + u(x)$, and its exact **reciprocal** $\frac{1}{u(x)}$ appears in the exponent, the expression $(1 + u(x))^{1/u(x)}$ approaches $e$:
> $$\lim_{x\to x_0} \big(1 + u(x)\big)^{1/u(x)} = e \quad \text{whenever } \lim_{x\to x_0} u(x) = 0 \text{ and } u(x) \neq 0.$$

More generally, if we have $\lim_{x\to 0} (1 + kx)^{1/x}$ for a non-zero constant $k$, direct evaluation gives the **indeterminate form $[1^\infty]$** (since $1 + kx \to 1$ and $\frac{1}{x} \to \pm\infty$). We can transform $(1 + kx)^{1/x}$ to match the classical pattern in two equivalent ways:
1. **Algebraic Exponent Manipulation**: Multiply and divide the exponent $\frac{1}{x}$ by $k$ so that $\frac{1}{kx}$ matches the reciprocal of $kx$, and use the power rule $a^{b \cdot c} = (a^b)^c$ together with the continuity of the power function $t \mapsto t^k$.
2. **Change of Variable (Substitution)**: Let $u = kx$ (or $t = \frac{1}{kx}$) so that as $x \to 0$, $u \to 0$ (or $t \to \pm\infty$).

## Detailed Step-by-Step Solution

### Step 1: Identify the Indeterminate Form

We wish to compute:
$$L = \lim_{x\to0}(1+3x)^{1/x}.$$

As $x \to 0$:
- The base $1 + 3x$ approaches $1 + 3(0) = 1$.
- The exponent $\frac{1}{x}$ grows without bound in magnitude ($\frac{1}{x} \to +\infty$ as $x \to 0^+$ and $\frac{1}{x} \to -\infty$ as $x \to 0^-$).

Therefore, this limit is an indeterminate form of type $[1^\infty]$.

### Step 2: Connect with Exercise 5 and Transform the Expression

In Exercise 5, we had $\lim_{n\to\infty} \left(1 + \frac{1}{n}\right)^n = e$, whose continuous counterpart for a vanishing increment $u \to 0$ is:
$$\lim_{u\to 0} (1 + u)^{1/u} = e,$$
or equivalently, in terms of $t = \frac{1}{u} \to \pm\infty$:
$$\lim_{t\to\pm\infty} \left(1 + \frac{1}{t}\right)^t = e.$$

In our expression $(1 + 3x)^{1/x}$, the small increment added to $1$ in the base is **$u = 3x$**. To match the classical pattern $(1 + u)^{1/u}$, we need the exponent to contain $\frac{1}{3x}$, the exact reciprocal of $3x$.

We achieve this by rewriting the exponent $\frac{1}{x}$ as $\frac{3}{3x} = \frac{1}{3x} \cdot 3$ and applying the exponent law $a^{b \cdot c} = \left(a^b\right)^c$:
$$(1 + 3x)^{1/x} = (1 + 3x)^{\frac{3}{3x}} = \left[(1 + 3x)^{\frac{1}{3x}}\right]^3.$$

### Step 3: Perform the Change of Variable and Evaluate the Limit

We can write the substitution explicitly in either of two ways:

#### Method A: Substitution $u = 3x$ (Form $\lim_{u\to 0}(1+u)^{1/u} = e$)
Let $u = 3x$. Then $x = \frac{u}{3}$, and as $x \to 0$, we have $u = 3x \to 0$. Substituting $u = 3x$ into our transformed expression gives:
$$(1 + 3x)^{1/x} = \left[(1 + 3x)^{\frac{1}{3x}}\right]^3 = \left[(1 + u)^{1/u}\right]^3.$$

Since the cubing function $y \mapsto y^3$ is continuous everywhere on $\mathbb{R}$, we can pass the limit inside the third power:
$$\begin{aligned}
\lim_{x\to 0} (1 + 3x)^{1/x} &= \lim_{u\to 0} \left[(1 + u)^{1/u}\right]^3 \\
&= \left[\lim_{u\to 0} (1 + u)^{1/u}\right]^3 \\
&= e^3.
\end{aligned}$$

#### Method B: Substitution $t = \frac{1}{3x}$ (Direct Connection to Exercise 5)
Alternatively, let $t = \frac{1}{3x}$, so that $3x = \frac{1}{t}$ and $\frac{1}{x} = 3t$. As $x \to 0^+$ (or $x \to 0^-$), $t \to +\infty$ (or $t \to -\infty$). Then:
$$(1 + 3x)^{1/x} = \left(1 + \frac{1}{t}\right)^{3t} = \left[\left(1 + \frac{1}{t}\right)^t\right]^3.$$
Since $\lim_{t\to\pm\infty} \left(1 + \frac{1}{t}\right)^t = e$ (the continuous generalization of Exercise 5), taking the limit gives:
$$\lim_{x\to 0} (1 + 3x)^{1/x} = \left[\lim_{t\to\pm\infty} \left(1 + \frac{1}{t}\right)^t\right]^3 = e^3.$$

**Final Answer:**
$$\lim_{x\to0}(1+3x)^{1/x} = e^3 \approx 20.085537.$$

## Verification and Consistency Checks

1. **Numerical Check Near $x = 0$**: Let us evaluate $f(x) = (1 + 3x)^{1/x}$ for small negative and positive values of $x$ approaching $0$, and compare with $e^3 \approx 20.0855369$:

   | $x$ | Base $1 + 3x$ | Exponent $1/x$ | $f(x) = (1 + 3x)^{1/x}$ | Distance $|f(x) - e^3|$ |
   | :--- | :--- | :--- | :--- | :--- |
   | $-0.01$ | $0.97$ | $-100$ | $(0.97)^{-100} \approx 21.029385$ | $0.943848$ |
   | $-0.001$ | $0.997$ | $-1,000$ | $(0.997)^{-1000} \approx 20.176308$ | $0.090771$ |
   | $-0.0001$ | $0.9997$ | $-10,000$ | $(0.9997)^{-10000} \approx 20.094579$ | $0.009042$ |
   | $+0.0001$ | $1.0003$ | $+10,000$ | $(1.0003)^{10000} \approx 20.076502$ | $0.009035$ |
   | $+0.001$ | $1.003$ | $+1,000$ | $(1.003)^{1000} \approx 19.995535$ | $0.090002$ |
   | $+0.01$ | $1.03$ | $+100$ | $(1.03)^{100} \approx 19.218632$ | $0.866905$ |

   As $x \to 0$ from both the left and the right, $f(x)$ squeezes toward $e^3 \approx 20.08554$.

2. **Logarithmic Consistency Check**: Taking the natural logarithm of $y = (1 + 3x)^{1/x}$ gives $\ln y = \frac{\ln(1 + 3x)}{x}$. Since $\left.\frac{d}{dx}\ln(1 + 3x)\right|_{x=0} = \left.\frac{3}{1+3x}\right|_{x=0} = 3$, we have $\lim_{x\to 0} \ln y = 3$, and by continuity of the exponential function, $\lim_{x\to 0} y = e^3$.
