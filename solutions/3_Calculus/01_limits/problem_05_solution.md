# Problem 5: The Classical Limit Leading to the Number $e$

## Problem Statement

Compute
$$\lim_{n\to\infty}\left(1+\frac1n\right)^n.$$
Calculate several values for increasing $n$ and compare the observed behavior with the value of the limit. Explain why a few values do not constitute a proof.

## Theoretical Background and Concepts

Consider the sequence
$$e_n = \left(1 + \frac{1}{n}\right)^n \quad \text{for } n = 1, 2, 3, \dots$$
As $n \to \infty$, the base $1 + \frac{1}{n}$ approaches $1$, while the exponent $n$ approaches $+\infty$. This creates the **indeterminate exponential form $[1^\infty]$**:
- On one hand, $1$ raised to any finite power is $1$, which pulls the expression toward $1$.
- On the other hand, a number strictly greater than $1$ raised to larger and larger powers grows without bound, which pushes the expression upward.

In mathematical analysis, Euler's number $e$ is defined via this exact classical limit. To prove that the limit exists and is finite, one uses the **Monotone Convergence Theorem for Sequences**, which states that **every sequence that is monotonically increasing and bounded above converges to a finite limit**. Specifically:
1. Using the **Binomial Theorem**, we can expand $\left(1 + \frac{1}{n}\right)^n$:
   $$\left(1 + \frac{1}{n}\right)^n = \sum_{k=0}^{n} \binom{n}{k} \frac{1}{n^k} = 1 + 1 + \frac{1}{2!}\left(1 - \frac{1}{n}\right) + \frac{1}{3!}\left(1 - \frac{1}{n}\right)\left(1 - \frac{2}{n}\right) + \dots + \frac{1}{n!}\left(1 - \frac{1}{n}\right)\cdots\left(1 - \frac{n-1}{n}\right).$$
2. As $n$ increases to $n+1$, each factor $\left(1 - \frac{j}{n}\right)$ increases and one extra positive term is added, showing that $(e_n)$ is **strictly increasing** ($e_n < e_{n+1}$).
3. Furthermore, since $\left(1 - \frac{j}{n}\right) < 1$ and $k! \ge 2^{k-1}$ for $k \ge 2$, we have:
   $$2 \le e_n < 1 + 1 + \frac{1}{2} + \frac{1}{2^2} + \dots + \frac{1}{2^{n-1}} = 1 + \left(2 - \frac{1}{2^{n-1}}\right) < 3.$$
   Because $e_n$ is strictly increasing and bounded above by $3$, it converges to a finite irrational number denoted by $e \approx 2.718281828459\dots$

## Detailed Step-by-Step Solution

### Step 1: Value of the Classical Limit

By the fundamental theorem for the sequence $e_n = \left(1 + \frac{1}{n}\right)^n$, the sequence resolves the $[1^\infty]$ indeterminate form by converging to Euler's constant $e$:
$$\lim_{n\to\infty}\left(1+\frac1n\right)^n = e \approx 2.718281828\dots$$

### Step 2: Calculating Values for Increasing $n$

Let us compute $e_n = \left(1 + \frac{1}{n}\right)^n$ for several increasing values of $n$, starting from small integers and progressing to large powers of $10$:

- For $n = 1$:
  $$e_1 = \left(1 + \frac{1}{1}\right)^1 = 2^1 = 2.000000$$
- For $n = 2$:
  $$e_2 = \left(1 + \frac{1}{2}\right)^2 = (1.5)^2 = \frac{9}{4} = 2.250000$$
- For $n = 3$:
  $$e_3 = \left(1 + \frac{1}{3}\right)^3 = \left(\frac{4}{3}\right)^3 = \frac{64}{27} \approx 2.370370$$
- For $n = 4$:
  $$e_4 = \left(1 + \frac{1}{4}\right)^4 = (1.25)^4 = \frac{625}{256} \approx 2.441406$$
- For $n = 5$:
  $$e_5 = \left(1 + \frac{1}{5}\right)^5 = (1.2)^5 = 2.488320$$
- For $n = 10$:
  $$e_{10} = \left(1 + \frac{1}{10}\right)^{10} = (1.1)^{10} \approx 2.593742$$
- For $n = 100$:
  $$e_{100} = (1.01)^{100} \approx 2.704814$$
- For $n = 1000$:
  $$e_{1000} = (1.001)^{1000} \approx 2.716924$$
- For $n = 10000$:
  $$e_{10000} = (1.0001)^{10000} \approx 2.718146$$
- For $n = 100000$:
  $$e_{100000} = (1.00001)^{100000} \approx 2.718268$$
- For $n = 1000000$:
  $$e_{1000000} = (1.000001)^{1000000} \approx 2.718280$$

#### Summary Table of Values

| $n$ | Base $1 + \frac{1}{n}$ | Value of $e_n = \left(1 + \frac{1}{n}\right)^n$ | Error $e - e_n$ |
| :--- | :--- | :--- | :--- |
| $1$ | $2.0$ | $2.000000$ | $0.718282$ |
| $2$ | $1.5$ | $2.250000$ | $0.468282$ |
| $3$ | $1.333333\dots$ | $2.370370$ | $0.347911$ |
| $5$ | $1.2$ | $2.488320$ | $0.229962$ |
| $10$ | $1.1$ | $2.593742$ | $0.124539$ |
| $100$ | $1.01$ | $2.704814$ | $0.013468$ |
| $1,000$ | $1.001$ | $2.716924$ | $0.001358$ |
| $10,000$ | $1.0001$ | $2.718146$ | $0.000136$ |
| $100,000$ | $1.00001$ | $2.718268$ | $0.000014$ |
| $\infty$ (Limit) | $1$ | $e \approx 2.718282$ | $0$ |

#### ASCII Sketch of the Sequence Behavior

```text
  e_n
  3.0 +
      |
  e --| - - - - - - - - - - - - - - - - - - - - - - * - - * - - * (Limit e ≈ 2.718)
      |                                       *
  2.5 +                                 *
      |                     *     *
      |               *
  2.0 +         *
      |
      +---------+-----+-----+-----+-----+-----+-----+-----+-----+---> n
                1     2     3     5    10    100  1000  10^4  10^5
```

### Step 3: Comparing Observed Behavior with the Limit

From our calculations and table, we observe several key features:
1. **Strict Monotonic Increase**: As $n$ increases, every computed term $e_n$ is strictly larger than the previous one ($2.000 < 2.250 < 2.370 < \dots < 2.71828\dots$). Thus, $e_n$ approaches the limit $e$ strictly **from below** ($e_n < e$ for all $n \ge 1$).
2. **Slow Rate of Convergence**: Notice that the convergence is relatively slow—at $n = 100$, only the first decimal place ($2.7$) matches $e \approx 2.71828$. Each time $n$ is multiplied by $10$, we gain roughly one additional correct decimal digit, because the error $e - e_n$ is approximately $\frac{e}{2n} \approx \frac{1.359}{n}$.

### Step 4: Why a Few Values Do Not Constitute a Proof

Calculating a finite number of terms—even for $n = 10^6$ or $n = 10^{12}$—**never constitutes a mathematical proof** of a limit for the following fundamental reasons:

1. **A Limit is a Statement About Infinitely Many Terms**: By definition, $\lim_{n\to\infty} a_n = L$ depends exclusively on the "tail" of the sequence—that is, what happens for *all* $n > N$ as $N$ becomes arbitrarily large. Any finite list of values inspects only a tiny initial prefix of the sequence and leaves infinitely many terms unchecked.
2. **Slowly Diverging Sequences Can Mimic Convergence**: A sequence can grow so slowly that numerical values appear to stabilize even though the sequence actually diverges to $+\infty$. For example, the harmonic partial sums $H_n = 1 + \frac{1}{2} + \dots + \frac{1}{n}$ or the sequence $\ln(\ln(n + 10))$ increase by minuscule amounts for large $n$, looking bounded in a finite table, yet they diverge to $+\infty$. Without an analytical upper bound (such as our Binomial Theorem bound $e_n < 3$), numerical inspection alone cannot rule out ultra-slow divergence to $+\infty$.
3. **Late-Stage Behavior Changes**: A sequence could behave smoothly for the first $10^6$ terms and then change behavior dramatically for $n > 10^6$ (for instance, $a_n = \left(1 + \frac{1}{n}\right)^n + 10^{-100} n^2$ looks identical to $e_n$ for $n \le 10^{20}$, yet diverges to $+\infty$).
4. **Finite Precision and Rounding Errors**: On a calculator or computer using floating-point arithmetic, when $n$ is extremely large (e.g., $n = 10^{16}$), $1 + \frac{1}{n}$ rounds to $1.0000000000000000$, and $1^n$ erroneously evaluates to $1$ instead of $e$! Only an analytical proof (showing monotonicity and boundedness) establishes the existence and value of the limit with certainty.

## Verification and Consistency Checks

We can verify the observed error rate analytically using the logarithmic expansion $\ln(1 + x) = x - \frac{x^2}{2} + \frac{x^3}{3} - \dots$ for small $x = \frac{1}{n}$:
$$\ln(e_n) = n \ln\left(1 + \frac{1}{n}\right) = n\left(\frac{1}{n} - \frac{1}{2n^2} + \frac{1}{3n^3} - \dots\right) = 1 - \frac{1}{2n} + \frac{1}{3n^2} - \dots$$
Exponentiating both sides gives:
$$e_n = e^{1 - \frac{1}{2n} + O(1/n^2)} = e \cdot e^{-\frac{1}{2n} + O(1/n^2)} \approx e\left(1 - \frac{1}{2n}\right) = e - \frac{e}{2n}.$$
For $n = 1000$, this formula predicts an error of $e - e_{1000} \approx \frac{2.718282}{2000} \approx 0.001359$, which matches the observed error $0.001358$ in our table to six decimal places!
