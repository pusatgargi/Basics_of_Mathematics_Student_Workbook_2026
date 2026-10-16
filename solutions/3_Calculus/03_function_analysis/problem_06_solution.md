# Problem 6: A Logarithmic Function

## Problem Statement

Analyze the domain, zero, and monotonicity of
$$f(x)=\ln x-x+1.$$
Explain why the analysis must begin with the domain.

## Theoretical Background and Concepts

When analyzing a function involving logarithmic expressions, the order of steps is critical:

1. **Why the Analysis Must Begin with the Domain**:
   - The natural logarithm $\ln x$ is defined on the real numbers **if and only if $x > 0$**.
   - However, when we differentiate $f(x) = \ln x - x + 1$, the resulting algebraic formula for the derivative,
     $$f'(x) = \frac{1}{x} - 1 = \frac{1 - x}{x},$$
     makes sense algebraically for every $x \neq 0$, including all negative real numbers $x < 0$!
   - If one fails to determine the domain $D_f = (0, \infty)$ before building the sign chart of $f'(x)$, one might falsely include the interval $(-\infty, 0)$, treat $x = 0$ as a point where $f'(x)$ changes sign from $-$ to $+$, or claim that $f$ is decreasing on $(-\infty, 0)$—where the function $f(x)$ **does not even exist**.
   - Furthermore, knowing from the outset that $x > 0$ simplifies the sign analysis of $f'(x) = \frac{1 - x}{x}$, because the denominator $x$ is guaranteed to be strictly positive everywhere on $D_f$.
2. **Uniqueness of Zeros via Strict Monotonicity and Extrema**:
   - If a continuous function $f$ on $(0, \infty)$ is strictly increasing on $(0, c]$ and strictly decreasing on $[c, \infty)$, then $f(c)$ is the **strict global maximum** of $f$ on $(0, \infty)$, meaning $f(x) < f(c)$ for all $x \in (0, \infty) \setminus \{c\}$.
   - In particular, if $f(c) = 0$, then $x = c$ is automatically the **unique zero** of $f$, and $f(x) < 0$ everywhere else on its domain.

## Detailed Step-by-Step Solution

### Step 1: Domain and Why It Must Come First

The terms $-x$ and $+1$ are defined for all $x \in \mathbb{R}$, whereas $\ln x$ requires its argument to be strictly positive:
$$x > 0.$$
Therefore, the domain of $f$ is the open half-line:
$$D_f = (0, \infty).$$

**Explanation of Priority**: Every subsequent step—solving $f(x) = 0$, taking limits at the boundary of the domain, differentiating, and constructing the sign table for $f'(x)$—is restricted exclusively to $x \in (0, \infty)$. Without fixing $D_f = (0, \infty)$ first, the rational expression $f'(x) = \frac{1 - x}{x}$ would misleadingly suggest analyzing $x < 0$, where $\ln x$ is undefined in $\mathbb{R}$.

### Step 2: First Derivative and Monotonicity

For all $x \in (0, \infty)$, $f$ is differentiable and its derivative is:
$$f'(x) = (\ln x)' - (x)' + (1)' = \frac{1}{x} - 1 = \frac{1 - x}{x}.$$

1. **Critical Points**:
   For $x \in (0, \infty)$,
   $$f'(x) = 0 \iff \frac{1 - x}{x} = 0 \iff 1 - x = 0 \iff x = 1.$$
   Since $1 \in (0, \infty)$, $x = 1$ is the unique critical point.
2. **Sign Chart of $f'(x)$ on $D_f = (0, \infty)$**:
   Because $x > 0$ throughout the domain, the denominator of $f'(x) = \frac{1 - x}{x}$ is always positive. Hence, the sign of $f'(x)$ is determined solely by the numerator $1 - x$:
   - On $(0, 1)$: $1 - x > 0 \implies f'(x) > 0$, so $f$ is **strictly increasing** on $(0, 1]$.
   - On $(1, \infty)$: $1 - x < 0 \implies f'(x) < 0$, so $f$ is **strictly decreasing** on $[1, \infty)$.

   | Interval / Point | $x = 0$ (boundary) | $(0, 1)$ | $x = 1$ | $(1, \infty)$ |
   | :---: | :---: | :---: | :---: | :---: |
   | Sign of $x$ | $0$ | $+$ | $+$ | $+$ |
   | Sign of $1 - x$ | $+$ | $+$ | $0$ | $-$ |
   | Sign of $f'(x) = \frac{1 - x}{x}$ | undefined | $+$ | $0$ | $-$ |
   | Behavior of $f(x)$ | V.A. ($\to -\infty$) | $\nearrow$ (strictly increasing) | **Global Max & Zero** $f(1) = 0$ | $\searrow$ (strictly decreasing) |

### Step 3: Global Maximum and Zero of $f(x)$

Evaluating $f(x)$ at the unique critical point $x = 1$:
$$f(1) = \ln 1 - 1 + 1 = 0 - 1 + 1 = 0.$$

Let us combine the monotonicity result with the value $f(1) = 0$:
- For every $x \in (0, 1)$, since $f$ is strictly increasing on $(0, 1]$, we have $f(x) < f(1) = 0$.
- For every $x \in (1, \infty)$, since $f$ is strictly decreasing on $[1, \infty)$, we have $f(x) < f(1) = 0$.

Consequently:
1. $f$ attains its **strict local and global maximum** on $(0, \infty)$ at $x = 1$, with maximum value $f_{\max} = f(1) = 0$.
2. Because $f(x) < 0$ for all $x \neq 1$ and $f(1) = 0$, **$x = 1$ is the unique zero of $f(x)$** on $(0, \infty)$.
3. Geometrically, the graph of $f$ lies entirely in the lower half-plane $y \le 0$ and touches the $x$-axis tangentially at the single point $(1, 0)$.

### Step 4: Boundary Limits and Curvature (Completing the Picture)

- **Right-hand limit at $x = 0^+$**:
  $$\lim_{x \to 0^+} (\ln x - x + 1) = [-\infty - 0 + 1] = -\infty,$$
  so the positive $y$-axis ($x = 0$) is a vertical asymptote.
- **Limit as $x \to +\infty$**:
  $$\lim_{x \to +\infty} (\ln x - x + 1) = \lim_{x \to +\infty} x\left(\frac{\ln x}{x} - 1 + \frac{1}{x}\right) = [+\infty \cdot (0 - 1 + 0)] = -\infty.$$
- **Second Derivative and Concavity**:
  $$f''(x) = -\frac{1}{x^2} < 0 \quad \text{for all } x \in (0, \infty).$$
  Thus, $f$ is **strictly concave** (concave down) on its entire domain $(0, \infty)$.

## Verification and Consistency Checks

1. **Test Points in Each Subinterval of $(0, \infty)$**:
   - In $(0, 1)$, choose $x = \frac{1}{e} \approx 0.368$:
     $$f'\left(\frac{1}{e}\right) = e - 1 \approx 1.718 > 0, \qquad f\left(\frac{1}{e}\right) = -1 - \frac{1}{e} + 1 = -\frac{1}{e} \approx -0.368 < 0.$$
   - In $(1, \infty)$, choose $x = e \approx 2.718$:
     $$f'(e) = \frac{1}{e} - 1 \approx -0.632 < 0, \qquad f(e) = 1 - e + 1 = 2 - e \approx -0.718 < 0.$$
   Both test points confirm the sign of $f'(x)$ and the strict inequality $f(x) < 0$ for $x \neq 1$.
2. **Connection to the Fundamental Logarithm Inequality**:
   Our analysis proves that $\ln x - x + 1 \le 0 \iff \ln x \le x - 1$ for all $x > 0$, with equality if and only if $x = 1$. Geometrically, $y = x - 1$ is the tangent line to the strictly concave curve $y = \ln x$ at $(1, 0)$, so the curve $y = \ln x$ lies strictly below its tangent line everywhere except at the point of tangency $x = 1$.
