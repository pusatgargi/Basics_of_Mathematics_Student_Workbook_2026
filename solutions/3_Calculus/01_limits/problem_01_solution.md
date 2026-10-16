# Problem 1: Dominant Terms in a Sequence

## Problem Statement

Compute
$$\lim_{n\to\infty}\frac{4n^2-3n+1}{2n^2+5n-7}.$$
Explain why the highest-degree terms determine the result.

## Theoretical Background and Concepts

When studying the **limit of a sequence** $(a_n)$ as $n \to \infty$, we examine whether the terms $a_n$ approach a fixed finite real number $L$ as the index $n$ grows without bound ($n = 1, 2, 3, \dots$). Formally, $\lim_{n\to\infty} a_n = L$ means that for any arbitrarily small positive tolerance $\varepsilon > 0$, there exists an index $N$ such that for all $n > N$, the distance $|a_n - L| < \varepsilon$.

When evaluating the limit of a rational expression in $n$ (a quotient of two polynomials in $n$) as $n \to \infty$:
$$\lim_{n\to\infty} \frac{P(n)}{Q(n)},$$
directly substituting $n \to \infty$ into both the numerator and denominator typically produces an **indeterminate form of type $\frac{\infty}{\infty}$**. An indeterminate form cannot be evaluated by naive arithmetic because the behavior of the quotient depends on the relative growth rates of the numerator and denominator.

To resolve an $\frac{\infty}{\infty}$ indeterminate form for rational expressions, we use the **method of factoring out the dominant (highest-degree) term**:
1. Identify the highest power of $n$ present in the denominator (and numerator).
2. Factor out this highest power $n^k$ from both the numerator and the denominator, or equivalently divide every term in both the numerator and denominator by $n^k$.
3. Use the **fundamental reciprocal power limit**: for any positive exponent $p > 0$ and any constant $c \in \mathbb{R}$,
   $$\lim_{n\to\infty} \frac{c}{n^p} = 0.$$
4. Apply the **Algebraic Limit Laws** (which state that if $\lim_{n\to\infty} a_n = A$ and $\lim_{n\to\infty} b_n = B$, then the limit of a sum, difference, product, or quotient is the corresponding combination of the limits, provided the denominator limit $B \neq 0$).

## Detailed Step-by-Step Solution

### Step 1: Identify the Indeterminate Form and Dominant Terms

We want to evaluate the sequence limit:
$$L = \lim_{n\to\infty}\frac{4n^2-3n+1}{2n^2+5n-7}.$$

As $n \to \infty$, both the numerator $4n^2 - 3n + 1$ and the denominator $2n^2 + 5n - 7$ grow without bound toward $+\infty$. Thus, this limit has the indeterminate form $\left[\frac{\infty}{\infty}\right]$.

Looking at the polynomial in the numerator ($4n^2 - 3n + 1$) and the polynomial in the denominator ($2n^2 + 5n - 7$), both have degree $2$. The highest-degree (dominant) term in the numerator is $4n^2$, and the highest-degree (dominant) term in the denominator is $2n^2$.

### Step 2: Factor Out the Highest Power of $n$

To transform the expression into one where individual terms converge to finite constants, we factor $n^2$ out of both the numerator and the denominator. For $n \ge 1$ (so $n^2 \neq 0$):

1. Factor $n^2$ from the numerator:
   $$4n^2 - 3n + 1 = n^2\left(4 - \frac{3n}{n^2} + \frac{1}{n^2}\right) = n^2\left(4 - \frac{3}{n} + \frac{1}{n^2}\right).$$

2. Factor $n^2$ from the denominator:
   $$2n^2 + 5n - 7 = n^2\left(2 + \frac{5n}{n^2} - \frac{7}{n^2}\right) = n^2\left(2 + \frac{5}{n} - \frac{7}{n^2}\right).$$

3. Substitute these factored forms into the quotient and cancel the common factor $n^2$:
   $$\frac{4n^2-3n+1}{2n^2+5n-7} = \frac{n^2\left(4 - \frac{3}{n} + \frac{1}{n^2}\right)}{n^2\left(2 + \frac{5}{n} - \frac{7}{n^2}\right)} = \frac{4 - \frac{3}{n} + \frac{1}{n^2}}{2 + \frac{5}{n} - \frac{7}{n^2}}.$$

### Step 3: Apply the Limit Laws and Reciprocal Power Rule

Recall the basic limit property that for any constant $c$ and $p > 0$, $\lim_{n\to\infty} \frac{c}{n^p} = 0$. Specifically:
$$\lim_{n\to\infty} \frac{3}{n} = 0, \qquad \lim_{n\to\infty} \frac{1}{n^2} = 0, \qquad \lim_{n\to\infty} \frac{5}{n} = 0, \qquad \lim_{n\to\infty} \frac{7}{n^2} = 0.$$

By the sum, difference, and quotient rules for limits (since the limit of the new denominator is $2 \neq 0$), we take the limit term by term:
$$\begin{aligned}
\lim_{n\to\infty}\frac{4n^2-3n+1}{2n^2+5n-7} &= \lim_{n\to\infty} \frac{4 - \frac{3}{n} + \frac{1}{n^2}}{2 + \frac{5}{n} - \frac{7}{n^2}} \\
&= \frac{\lim_{n\to\infty} 4 - \lim_{n\to\infty}\frac{3}{n} + \lim_{n\to\infty}\frac{1}{n^2}}{\lim_{n\to\infty} 2 + \lim_{n\to\infty}\frac{5}{n} - \lim_{n\to\infty}\frac{7}{n^2}} \\
&= \frac{4 - 0 + 0}{2 + 0 - 0} \\
&= \frac{4}{2} = 2.
\end{aligned}$$

### Step 4: Explanation of Why the Highest-Degree Terms Determine the Result

Why do the highest-degree terms ($4n^2$ and $2n^2$) completely dictate the limit, while the lower-degree terms ($-3n, +1, +5n, -7$) have zero effect on the final answer?

1. **Relative Magnitude for Large $n$**: As $n$ becomes very large, $n^2$ grows much faster than $n$ or a constant $1$. Specifically, the ratio of a linear term to a quadratic term is $\frac{n}{n^2} = \frac{1}{n}$, which shrinks toward $0$ as $n \to \infty$, and the ratio of a constant term to a quadratic term is $\frac{1}{n^2}$, which shrinks toward $0$ even faster.
2. **Negligible Relative Contribution**: When we factor out $n^2$, we explicitly rewrite each polynomial as its dominant term multiplied by $(1 + \text{vanishing error terms})$:
   $$4n^2 - 3n + 1 = 4n^2\left(1 - \frac{3}{4n} + \frac{1}{4n^2}\right), \qquad 2n^2 + 5n - 7 = 2n^2\left(1 + \frac{5}{2n} - \frac{7}{2n^2}\right).$$
   For enormous values of $n$, the factors in parentheses become indistinguishable from $1$. Consequently, the fraction behaves asymptotically like the ratio of its leading terms alone:
   $$\frac{4n^2 - 3n + 1}{2n^2 + 5n - 7} \approx \frac{4n^2}{2n^2} = \frac{4}{2} = 2.$$
   While $-3n$ and $+5n$ grow large in absolute value as $n \to \infty$, their size *relative to $n^2$* vanishes to zero. In a quotient, only the relative proportions survive cancellation of the dominant scale $n^2$.

**Final Answer:**
$$\lim_{n\to\infty}\frac{4n^2-3n+1}{2n^2+5n-7} = 2.$$

## Verification and Consistency Checks

Let us verify this analytical result by evaluating the sequence $a_n = \frac{4n^2-3n+1}{2n^2+5n-7}$ for increasingly large values of $n$:

| $n$ | Numerator $4n^2-3n+1$ | Denominator $2n^2+5n-7$ | Quotient $a_n$ | Distance from limit $|a_n - 2|$ |
| :--- | :--- | :--- | :--- | :--- |
| $10$ | $4(100) - 30 + 1 = 371$ | $2(100) + 50 - 7 = 243$ | $\frac{371}{243} \approx 1.52675$ | $0.47325$ |
| $100$ | $4(10000) - 300 + 1 = 39701$ | $2(10000) + 500 - 7 = 20493$ | $\frac{39701}{20493} \approx 1.937296$ | $0.06270$ |
| $1000$ | $3,997,001$ | $2,004,993$ | $\approx 1.993524$ | $0.00648$ |
| $10000$ | $399,970,001$ | $200,049,993$ | $\approx 1.999350$ | $0.00065$ |

Notice that each time $n$ increases by a factor of $10$, the error $|a_n - 2|$ decreases by approximately a factor of $10$. We can also see this algebraically by computing the exact difference between $a_n$ and $2$:
$$a_n - 2 = \frac{4n^2-3n+1 - 2(2n^2+5n-7)}{2n^2+5n-7} = \frac{-13n + 15}{2n^2+5n-7} \approx -\frac{13}{2n} = -\frac{6.5}{n}.$$
For $n = 10000$, $-\frac{6.5}{10000} = -0.00065$, so $a_{10000} \approx 2 - 0.00065 = 1.99935$, which matches our table and confirms that $a_n \to 2$ as $n \to \infty$.
