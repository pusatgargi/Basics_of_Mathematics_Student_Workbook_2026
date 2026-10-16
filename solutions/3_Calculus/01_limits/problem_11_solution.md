# Problem 11: An n-th Root

## Problem Statement

Compute
$$\lim_{n\to\infty}\sqrt[n]{5^n+2^n}.$$
Explain which term dominates and why the transformation looks different from the case of a quotient of polynomials.

## Theoretical Background and Concepts

When evaluating the limit of an $n$-th root of a sum of exponential terms:
$$a_n = \sqrt[n]{b_1^n + b_2^n + \dots + b_k^n} \quad (\text{where } b_1 > b_2 > \dots > b_k > 0),$$
as $n \to \infty$, the radicand $b_1^n + \dots + b_k^n$ grows to $+\infty$ while the root exponent $\frac{1}{n}$ approaches $0$, creating the **indeterminate exponential form $[\infty^0]$**.

Among exponential sequences $b^n$ with positive bases, the sequence with the **largest base** grows exponentially faster than all others. Specifically, if $b_1 > b_2 > 0$, then the ratio of the smaller exponential to the larger exponential is a geometric sequence with base $q = \frac{b_2}{b_1} \in (0, 1)$, which vanishes as $n \to \infty$:
$$\lim_{n\to\infty} \frac{b_2^n}{b_1^n} = \lim_{n\to\infty} \left(\frac{b_2}{b_1}\right)^n = 0.$$

We have two standard, complementary techniques to evaluate $\lim_{n\to\infty} \sqrt[n]{5^n + 2^n}$:
1. **Factoring Out the Dominant Exponential Term Under the Radical**:
   Factor $5^n$ out of $5^n + 2^n$ inside the $n$-th root, use the radical product property $\sqrt[n]{A \cdot B} = \sqrt[n]{A}\sqrt[n]{B}$ and $\sqrt[n]{5^n} = 5$, and evaluate the remaining factor using $\lim_{n\to\infty} (2/5)^n = 0$.
2. **The Squeeze Theorem (Sandwich Theorem) with $\lim_{n\to\infty} \sqrt[n]{c} = 1$**:
   Bound $5^n + 2^n$ below by the dominant term alone ($5^n$) and above by replacing every smaller term with a copy of the dominant term ($5^n + 5^n = 2 \cdot 5^n$), then take the $n$-th root of the inequality and use the fundamental root limit:
   $$\lim_{n\to\infty} \sqrt[n]{c} = 1 \quad \text{for any constant } c > 0.$$

## Detailed Step-by-Step Solution

### Step 1: Identify the Dominant Term

Inside the $n$-th root $\sqrt[n]{5^n + 2^n}$, we have the sum of two exponential terms: $5^n$ and $2^n$.
- Because the base $5$ is strictly greater than the base $2$ ($5 > 2 > 0$), the term **$5^n$ dominates $2^n$** as $n \to \infty$.
- Indeed, the ratio of $2^n$ to $5^n$ is $\frac{2^n}{5^n} = \left(\frac{2}{5}\right)^n = (0.4)^n$, which decays rapidly to $0$ as $n \to \infty$.

### Step 2: Method 1 — Factoring Out the Dominant Exponential Term

Let us factor the dominant term $5^n$ from the expression inside the $n$-th root and use the radical identities $\sqrt[n]{a \cdot b} = \sqrt[n]{a} \cdot \sqrt[n]{b}$ and $\sqrt[n]{5^n} = 5$:
$$\begin{aligned}
\sqrt[n]{5^n+2^n} &= \sqrt[n]{5^n\left(1 + \frac{2^n}{5^n}\right)} \\
&= \sqrt[n]{5^n\left(1 + \left(\frac{2}{5}\right)^n\right)} \\
&= \sqrt[n]{5^n} \cdot \sqrt[n]{1 + \left(\frac{2}{5}\right)^n} \\
&= 5 \cdot \left(1 + \left(\frac{2}{5}\right)^n\right)^{1/n}.
\end{aligned}$$

Now let us examine the behavior as $n \to \infty$:
- Since $0 < \frac{2}{5} < 1$, we have $\lim_{n\to\infty} \left(\frac{2}{5}\right)^n = 0$, so the base $1 + \left(\frac{2}{5}\right)^n \to 1 + 0 = 1$, while the exponent $\frac{1}{n} \to 0$.
- Because $1^0 = 1$ is a determinate form (not indeterminate!), we have $\lim_{n\to\infty} \left(1 + \left(\frac{2}{5}\right)^n\right)^{1/n} = 1^0 = 1$.
- Therefore:
  $$\lim_{n\to\infty}\sqrt[n]{5^n+2^n} = 5 \cdot 1 = 5.$$

### Step 3: Method 2 — Rigorous Justification via the Squeeze Theorem

To make the step $\left(1 + \left(\frac{2}{5}\right)^n\right)^{1/n} \to 1$ completely elementary using the Squeeze Theorem:
1. For all $n \ge 1$, since $0 < 2^n < 5^n$, we can bound the sum $5^n + 2^n$ from below by dropping $2^n$, and from above by replacing $2^n$ with $5^n$:
   $$5^n < 5^n + 2^n < 5^n + 5^n = 2 \cdot 5^n.$$
2. Since the $n$-th root function $t \mapsto \sqrt[n]{t}$ is strictly increasing for $t > 0$, we take the $n$-th root across the entire inequality:
   $$\sqrt[n]{5^n} < \sqrt[n]{5^n + 2^n} < \sqrt[n]{2 \cdot 5^n},$$
   which simplifies to:
   $$5 < \sqrt[n]{5^n + 2^n} < 5\sqrt[n]{2}.$$
3. Using the known limit $\lim_{n\to\infty} \sqrt[n]{2} = 1$, we evaluate the limits of the lower and upper bounds:
   $$\lim_{n\to\infty} 5 = 5 \qquad \text{and} \qquad \lim_{n\to\infty} 5\sqrt[n]{2} = 5 \cdot 1 = 5.$$
4. By the **Squeeze Theorem**, since $\sqrt[n]{5^n + 2^n}$ is trapped between two sequences that both converge to $5$, we conclude:
   $$\lim_{n\to\infty}\sqrt[n]{5^n+2^n} = 5.$$

### Step 4: Why the Transformation Looks Different from a Quotient of Polynomials

How and why does our transformation here differ from factoring a quotient of polynomials (such as in Exercise 1 or Exercise 2)?

1. **Exponential Growth (Varying Exponent) vs. Power Growth (Varying Base)**:
   - In a polynomial like $4n^2 - 3n + 1$, the base $n$ is the variable and the exponents ($2, 1, 0$) are fixed constants. Dominance is determined by the **largest exponent** ($n^2$), and factoring out $n^2$ leaves reciprocal power terms like $\frac{1}{n}$ and $\frac{1}{n^2}$ that decay algebraically to $0$.
   - In $\sqrt[n]{5^n + 2^n}$, the variable $n$ is in the **exponent**, while the bases ($5$ and $2$) are fixed constants. Dominance is determined by the **largest base** ($5^n$), and factoring out $5^n$ leaves a geometric sequence $\left(\frac{2}{5}\right)^n$ with base $\frac{2}{5} < 1$, which decays *exponentially* to $0$.
2. **Extracting a Factor from an $n$-th Root vs. Canceling in a Quotient**:
   - In a quotient of polynomials $\frac{P(n)}{Q(n)}$, the indeterminate form is $\left[\frac{\infty}{\infty}\right]$, and we factor $n^k$ from both the numerator and denominator so that $\frac{n^k}{n^k} = 1$ **cancels by division**.
   - Here, there is no denominator! Instead, the $n$-th root $\sqrt[n]{\,\cdot\,}$ acts as the counterbalancing operation that tames the exponential growth $5^n$ (resolving the $[\infty^0]$ form). When we factor $5^n$ out of the sum inside the radical, it exits the $n$-th root via the identity $\sqrt[n]{5^n} = \left(5^n\right)^{1/n} = 5$, while the remaining factor $\left(1 + \left(\frac{2}{5}\right)^n\right)^{1/n}$ is crushed to $1$ by both $\left(\frac{2}{5}\right)^n \to 0$ and the $\frac{1}{n}$ exponent.

**Final Answer:**
$$\lim_{n\to\infty}\sqrt[n]{5^n+2^n} = 5.$$

## Verification and Consistency Checks

Let us evaluate $a_n = \sqrt[n]{5^n + 2^n}$ for small to moderate values of $n$ to observe how rapidly $5^n$ dominates $2^n$:

| $n$ | $5^n$ | $2^n$ | $5^n + 2^n$ | $a_n = \sqrt[n]{5^n+2^n}$ | Error $a_n - 5$ |
| :--- | :--- | :--- | :--- | :--- | :--- |
| $1$ | $5$ | $2$ | $7$ | $7.00000000$ | $2.00000000$ |
| $2$ | $25$ | $4$ | $29$ | $\sqrt{29} \approx 5.38516481$ | $0.38516481$ |
| $5$ | $3,125$ | $32$ | $3,157$ | $\sqrt[5]{3157} \approx 5.01019801$ | $0.01019801$ |
| $10$ | $9,765,625$ | $1,024$ | $9,766,649$ | $\sqrt[10]{9766649} \approx 5.00005243$ | $0.00005243$ |
| $20$ | $\approx 9.5367 \times 10^{13}$ | $1,048,576$ | $\approx 9.5367 \times 10^{13}$ | $\approx 5.000000003$ | $2.75 \times 10^{-9}$ |

Notice how remarkably fast the sequence converges to $5$: by $n = 10$, $a_{10}$ is already within $0.000053$ of $5$, because the error is roughly $\frac{5}{n}\left(\frac{2}{5}\right)^n$, which shrinks exponentially!
