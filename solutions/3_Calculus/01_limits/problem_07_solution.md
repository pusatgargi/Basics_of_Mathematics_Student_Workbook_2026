# Problem 7: Limit at a Point and Canceling a Factor

## Problem Statement

Compute
$$\lim_{x\to3}\frac{x^2-4x+3}{x-3}.$$
Explain why the value of the function at $x=3$ is not needed to compute the limit.

## Theoretical Background and Concepts

The **limit of a function at a finite point $x_0$**, written
$$\lim_{x\to x_0} f(x) = L,$$
describes the value that $f(x)$ approaches as the argument $x$ gets arbitrarily close to $x_0$, **without $x$ ever being equal to $x_0$**. Formally (the Cauchy $\varepsilon$-$\delta$ definition), $\lim_{x\to x_0} f(x) = L$ means that for every $\varepsilon > 0$, there exists a $\delta > 0$ such that for all $x$ in the domain of $f$ satisfying
$$0 < |x - x_0| < \delta \quad \Longrightarrow \quad |f(x) - L| < \varepsilon.$$
Notice the strict inequality **$0 < |x - x_0|$**: this explicitly requires $x \neq x_0$.

Consequently, we have the **Local Replacement Principle for Limits**:
> If two functions $f(x)$ and $g(x)$ satisfy $f(x) = g(x)$ for all $x \neq x_0$ in an open interval around $x_0$, then
> $$\lim_{x\to x_0} f(x) = \lim_{x\to x_0} g(x),$$
> provided the limit on the right exists.

When evaluating a rational limit $\lim_{x\to x_0} \frac{P(x)}{Q(x)}$ where both $P(x_0) = 0$ and $Q(x_0) = 0$, direct substitution produces the **indeterminate form $\left[\frac{0}{0}\right]$**. By **Bézout's Theorem (the Factor Theorem for Polynomials)**, if a polynomial $P(x)$ satisfies $P(x_0) = 0$, then $(x - x_0)$ is a factor of $P(x)$. Therefore, both $P(x)$ and $Q(x)$ share the common factor $(x - x_0)$. Factoring both polynomials and canceling $(x - x_0)$ for $x \neq x_0$ removes the $\left[\frac{0}{0}\right]$ indeterminate form and allows us to compute the limit by direct substitution into the simplified expression.

## Detailed Step-by-Step Solution

### Step 1: Check Direct Substitution and Identify the Indeterminate Form

Let $f(x) = \frac{x^2-4x+3}{x-3}$. We wish to compute:
$$\lim_{x\to3}\frac{x^2-4x+3}{x-3}.$$

First, let us check what happens to the numerator and denominator as $x \to 3$:
- Numerator: $\lim_{x\to3} (x^2 - 4x + 3) = 3^2 - 4(3) + 3 = 9 - 12 + 3 = 0$.
- Denominator: $\lim_{x\to3} (x - 3) = 3 - 3 = 0$.

Because both the numerator and denominator approach $0$, this limit is an indeterminate form of type $\left[\frac{0}{0}\right]$. Note also that $x = 3$ is not in the domain of $f(x)$ because division by zero is undefined.

### Step 2: Factor the Numerator and Cancel the Common Factor

Since the quadratic polynomial $P(x) = x^2 - 4x + 3$ vanishes at $x = 3$, $(x - 3)$ must be one of its linear factors. Looking for two numbers whose product is $+3$ and whose sum is $-4$ (namely $-3$ and $-1$), or using Vieta's formulas, we factor the numerator:
$$x^2 - 4x + 3 = (x - 3)(x - 1).$$

Therefore, for all $x \neq 3$, the factor $(x - 3)$ is non-zero ($x - 3 \neq 0$), so we can legitimately divide both the numerator and denominator by $(x - 3)$:
$$\frac{x^2-4x+3}{x-3} = \frac{(x - 3)(x - 1)}{x - 3} = x - 1 \quad (\text{for all } x \neq 3).$$

### Step 3: Evaluate the Limit of the Simplified Expression

Since $f(x) = \frac{x^2-4x+3}{x-3}$ and $g(x) = x - 1$ are identical for every $x \neq 3$, they have the exact same limit as $x \to 3$. Moreover, $g(x) = x - 1$ is a polynomial (hence continuous everywhere, including at $x = 3$), so its limit as $x \to 3$ can be found by direct substitution:
$$\begin{aligned}
\lim_{x\to3}\frac{x^2-4x+3}{x-3} &= \lim_{x\to3}\frac{(x - 3)(x - 1)}{x - 3} \\
&= \lim_{x\to3} (x - 1) \\
&= 3 - 1 = 2.
\end{aligned}$$

### Step 4: Explain Why the Value of the Function at $x=3$ Is Not Needed

Why do we not need $f(3)$ to exist (or to equal any specific number) in order to compute $\lim_{x\to 3} f(x)$?

1. **The Definition of a Limit Excludes the Point $x = 3$ Itself**:
   By definition, $\lim_{x\to 3} f(x)$ asks exclusively how the outputs $f(x)$ behave when $x$ is **arbitrarily close to $3$, but strictly not equal to $3$** ($0 < |x - 3| < \delta$). Because the condition $x = 3$ is never tested in the limit definition, whether $f(3)$ is undefined (as in our function $f(x) = \frac{x^2-4x+3}{x-3}$), or defined to be $100$, or defined to be $2$, has **zero impact** on the values of $f(x)$ for $x \neq 3$.
2. **Validity of Canceling $(x - 3)$**:
   Algebraically, dividing by $(x - 3)$ would be illegal at $x = 3$ (since $\frac{0}{0}$ is undefined). However, because taking the limit as $x \to 3$ guarantees $x \neq 3$, we have $x - 3 \neq 0$ at every point involved in the limit process. Thus $\frac{x-3}{x-3} = 1$ holds everywhere in the punctured neighborhood of $x = 3$.
3. **Geometric Interpretation (Removable Discontinuity / "Hole" in the Graph)**:
   Geometrically, the graph of $y = \frac{x^2-4x+3}{x-3}$ is the straight line $y = x - 1$ with a single missing point (a "puncture" or "hole") at $(3, 2)$. Walking along the line toward $x = 3$ from either side leads directly toward height $y = 2$, regardless of whether the point at $x = 3$ is missing or displaced.

**Final Answer:**
$$\lim_{x\to3}\frac{x^2-4x+3}{x-3} = 2.$$

## Verification and Consistency Checks

Let us evaluate $f(x) = \frac{x^2-4x+3}{x-3}$ at points approaching $x = 3$ from both the left ($x < 3$) and the right ($x > 3$):

| $x$ (Left of $3$) | Numerator $x^2-4x+3$ | Denominator $x-3$ | $f(x)$ | $x$ (Right of $3$) | Numerator $x^2-4x+3$ | Denominator $x-3$ | $f(x)$ |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| $2.9$ | $-0.19$ | $-0.1$ | $1.9$ | $3.1$ | $0.21$ | $0.1$ | $2.1$ |
| $2.99$ | $-0.0199$ | $-0.01$ | $1.99$ | $3.01$ | $0.0201$ | $0.01$ | $2.01$ |
| $2.999$ | $-0.001999$ | $-0.001$ | $1.999$ | $3.001$ | $0.002001$ | $0.001$ | $2.001$ |
| $2.9999$ | $-0.00019999$ | $-0.0001$ | $1.9999$ | $3.0001$ | $0.00020001$ | $0.0001$ | $2.0001$ |

In every case, $f(x) = x - 1$ holds identically, and as $x$ approaches $3$ from either side, $f(x)$ approaches $2$.
