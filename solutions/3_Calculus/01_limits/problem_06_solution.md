# Problem 6: From a Sequence to a Function — Limit at Infinity

## Problem Statement

Compute
$$\lim_{x\to\infty}\frac{3x^2-x+1}{5x^2+4x-2}.$$
Compare the method with Exercise 1. Explain what changes when moving from $n$ to a real variable $x$, and what stays the same.

## Theoretical Background and Concepts

A **limit of a function at infinity**, written $\lim_{x\to\infty} f(x) = L$, describes the behavior of $f(x)$ as the continuous real variable $x$ grows arbitrarily large without bound ($x \in \mathbb{R}$, $x \to +\infty$). Formally, $\lim_{x\to\infty} f(x) = L$ means that for every $\varepsilon > 0$, there exists a real threshold $M > 0$ such that for all real numbers $x > M$, we have $|f(x) - L| < \varepsilon$.

Just as with sequences, when $f(x) = \frac{P(x)}{Q(x)}$ is a rational function (a quotient of polynomials), taking $x \to \infty$ produces an **indeterminate form of type $\left[\frac{\infty}{\infty}\right]$**. The algebraic resolution is identical to the sequence case:
1. Factor out the highest power $x^k$ from both the numerator and the denominator (valid for all $x > 0$, and in particular for $x$ sufficiently large so $Q(x) \neq 0$).
2. Apply the **reciprocal power limit for functions**: for any constant $c \in \mathbb{R}$ and any exponent $p > 0$,
   $$\lim_{x\to\infty} \frac{c}{x^p} = 0.$$
3. Apply the standard **Algebraic Limit Laws for Functions** (sum, difference, product, and quotient rules).

Furthermore, the connection between function limits and sequence limits is formalized by the **Heine Definition of a Limit (Sequential Criterion)**: if $\lim_{x\to\infty} f(x) = L$, then for any sequence $(x_n)$ of real numbers satisfying $x_n \to \infty$ (in particular, $x_n = n$), the sequence of outputs $f(x_n)$ also converges to $L$. Geometrically, $\lim_{x\to\infty} f(x) = L$ means the line $y = L$ is a **horizontal asymptote** of the graph of $y = f(x)$ as $x \to +\infty$.

## Detailed Step-by-Step Solution

### Step 1: Identify the Indeterminate Form and Dominant Terms

We want to evaluate:
$$L = \lim_{x\to\infty}\frac{3x^2-x+1}{5x^2+4x-2}.$$

As $x \to \infty$, both the numerator $3x^2 - x + 1 \to +\infty$ and the denominator $5x^2 + 4x - 2 \to +\infty$, yielding the indeterminate form $\left[\frac{\infty}{\infty}\right]$. Both the numerator and denominator are quadratic polynomials (degree $2$), with dominant terms $3x^2$ and $5x^2$, respectively.

### Step 2: Factor Out the Highest Power $x^2$

Since we are considering the limit as $x \to \infty$, we may assume $x > 1$ (so $x \neq 0$ and $5x^2 + 4x - 2 > 0$). Factoring $x^2$ from both the numerator and denominator and canceling $x^2$:
$$\begin{aligned}
\frac{3x^2-x+1}{5x^2+4x-2} &= \frac{x^2\left(3 - \frac{x}{x^2} + \frac{1}{x^2}\right)}{x^2\left(5 + \frac{4x}{x^2} - \frac{2}{x^2}\right)} \\
&= \frac{x^2\left(3 - \frac{1}{x} + \frac{1}{x^2}\right)}{x^2\left(5 + \frac{4}{x} - \frac{2}{x^2}\right)} \\
&= \frac{3 - \frac{1}{x} + \frac{1}{x^2}}{5 + \frac{4}{x} - \frac{2}{x^2}}.
\end{aligned}$$

### Step 3: Apply the Limit Laws as $x \to \infty$

Using the elementary limits $\lim_{x\to\infty} \frac{1}{x} = 0$, $\lim_{x\to\infty} \frac{1}{x^2} = 0$, $\lim_{x\to\infty} \frac{4}{x} = 0$, and $\lim_{x\to\infty} \frac{2}{x^2} = 0$, together with the quotient law for limits (since the denominator approaches $5 \neq 0$), we obtain:
$$\begin{aligned}
\lim_{x\to\infty}\frac{3x^2-x+1}{5x^2+4x-2} &= \lim_{x\to\infty} \frac{3 - \frac{1}{x} + \frac{1}{x^2}}{5 + \frac{4}{x} - \frac{2}{x^2}} \\
&= \frac{\lim_{x\to\infty} 3 - \lim_{x\to\infty}\frac{1}{x} + \lim_{x\to\infty}\frac{1}{x^2}}{\lim_{x\to\infty} 5 + \lim_{x\to\infty}\frac{4}{x} - \lim_{x\to\infty}\frac{2}{x^2}} \\
&= \frac{3 - 0 + 0}{5 + 0 - 0} \\
&= \frac{3}{5} = 0.6.
\end{aligned}$$

### Step 4: Comparison with Exercise 1 — What Changes and What Stays the Same

Let us compare this computation with Exercise 1 ($\lim_{n\to\infty}\frac{4n^2-3n+1}{2n^2+5n-7} = 2$):

#### What Stays the Same:
1. **The Indeterminate Form**: Both limits exhibit the $\left[\frac{\infty}{\infty}\right]$ indeterminate form caused by a quotient of two quadratic polynomials.
2. **The Algebraic Technique (Factoring the Dominant Power)**: In both problems, we factor out the highest power ($n^2$ in Exercise 1, $x^2$ in Exercise 6) from the numerator and denominator and cancel it.
3. **Vanishing Reciprocal Terms**: Both rely on the fact that reciprocal powers ($\frac{c}{n^k}$ or $\frac{c}{x^k}$ for $k > 0$) tend to $0$ as the argument grows without bound.
4. **Dominance of Leading Terms**: In both cases, because the numerator and denominator have equal degree ($2$), the limit equals the ratio of the leading coefficients ($\frac{4}{2} = 2$ in Exercise 1; $\frac{3}{5} = 0.6$ in Exercise 6).

#### What Changes When Moving from $n$ to a Real Variable $x$:
1. **Nature of the Domain (Discrete vs. Continuous)**:
   - In Exercise 1, the variable $n \in \mathbb{N} = \{1, 2, 3, \dots\}$ is **discrete**; it jumps in integer steps, and the graph of the sequence is a collection of isolated points.
   - In Exercise 6, the variable $x \in \mathbb{R}$ is **continuous**; $x$ passes through all real values (including fractions and irrationals) as it moves toward $+\infty$, and the graph of $f(x)$ is a continuous curve for large $x$.
2. **Domain Restrictions and Directions at Infinity**:
   - For a function of a real variable $x$, we must be mindful of points where the denominator $5x^2 + 4x - 2 = 0$ (though for $x \to +\infty$, we only care about $x > M$ beyond the largest root of the denominator).
   - Moreover, a real variable $x$ can also approach $-\infty$ ($\lim_{x\to-\infty} f(x)$), whereas a sequence index $n \in \mathbb{N}$ only goes to $+\infty$.
3. **LogicalGenerality (Heine's Criterion)**:
   - For $\lim_{x\to\infty} f(x) = L$ to hold, $f(x)$ must approach $L$ along *all* real numbers $x \to \infty$, not just integer values. (For instance, $\lim_{n\to\infty} \sin(\pi n) = \lim_{n\to\infty} 0 = 0$, whereas $\lim_{x\to\infty} \sin(\pi x)$ does not exist because $x$ takes non-integer values!) For rational functions, however, the behavior is smooth and monotonic for large $x$, so the continuous limit and discrete limit coincide.

**Final Answer:**
$$\lim_{x\to\infty}\frac{3x^2-x+1}{5x^2+4x-2} = \frac{3}{5}.$$

## Verification and Consistency Checks

Let us evaluate $f(x) = \frac{3x^2-x+1}{5x^2+4x-2}$ at several large real values of $x$ (including non-integer values) to confirm convergence to $\frac{3}{5} = 0.6$:

| $x$ | Numerator $3x^2-x+1$ | Denominator $5x^2+4x-2$ | $f(x)$ | Error $\left|f(x) - 0.6\right|$ |
| :--- | :--- | :--- | :--- | :--- |
| $10.5$ | $3(110.25) - 10.5 + 1 = 321.25$ | $5(110.25) + 42 - 2 = 591.25$ | $\approx 0.543340$ | $0.056660$ |
| $100$ | $29,901$ | $50,398$ | $\approx 0.593297$ | $0.006703$ |
| $1000\pi \approx 3141.59$ | $\approx 29,605,671.8$ | $\approx 49,360,586.5$ | $\approx 0.599784$ | $0.000216$ |
| $10,000$ | $299,990,001$ | $500,039,998$ | $\approx 0.599932$ | $0.000068$ |

We can also check the asymptotic error analytically:
$$f(x) - \frac{3}{5} = \frac{5(3x^2-x+1) - 3(5x^2+4x-2)}{5(5x^2+4x-2)} = \frac{-17x + 11}{25x^2+20x-10} \approx -\frac{17}{25x} = -\frac{0.68}{x}.$$
At $x = 10,000$, this gives $f(10000) - 0.6 \approx -0.000068$, which matches our numerical table!
