# Problem 2: Different Growth Rates

## Problem Statement

Compute
$$\lim_{n\to\infty}\frac{3n+1}{n^2+4},\qquad \lim_{n\to\infty}\frac{2n^3-n}{5n^2+1}.$$
Compare the two cases and formulate a general observation about the degrees of the polynomials in the numerator and denominator.

## Theoretical Background and Concepts

When analyzing a rational sequence of the form
$$a_n = \frac{P(n)}{Q(n)} = \frac{a_p n^p + a_{p-1}n^{p-1} + \dots + a_0}{b_q n^q + b_{q-1}n^{q-1} + \dots + b_0}$$
with leading coefficients $a_p \neq 0$ and $b_q \neq 0$, both the numerator and denominator grow without bound as $n \to \infty$ (assuming $p, q \ge 1$), creating an $\left[\frac{\infty}{\infty}\right]$ indeterminate form.

The outcome of the competition between the numerator and the denominator depends on their **relative growth rates**, which are governed by the degrees $p = \deg(P)$ and $q = \deg(Q)$:
- To compare their growth rates systematically, we can either **factor out the highest power of $n$ from the denominator** ($n^q$) or **factor out the dominant power of $n$ separately from the numerator ($n^p$) and the denominator ($n^q$)**.
- Using the reciprocal power limit $\lim_{n\to\infty} \frac{c}{n^k} = 0$ for $k > 0$, all non-leading terms vanish after factoring, leaving the behavior of $\frac{a_p}{b_q} n^{p-q}$.
- If a sequence grows without bound in the positive direction as $n \to \infty$, we write $\lim_{n\to\infty} a_n = +\infty$ (meaning the sequence **diverges to $+\infty$**).

## Detailed Step-by-Step Solution

### Part 1: Evaluating the First Limit

We want to compute:
$$L_1 = \lim_{n\to\infty}\frac{3n+1}{n^2+4}.$$

#### Step 1.1: Identify Degrees and Indeterminate Form
- The numerator $P(n) = 3n + 1$ is a polynomial of degree $p = 1$.
- The denominator $Q(n) = n^2 + 4$ is a polynomial of degree $q = 2$.
- As $n \to \infty$, both $3n+1 \to \infty$ and $n^2+4 \to \infty$, giving an indeterminate form $\left[\frac{\infty}{\infty}\right]$.

#### Step 1.2: Factor Out the Highest Power of the Denominator ($n^2$)
We factor $n^2$ out of both the numerator and the denominator:
$$\frac{3n+1}{n^2+4} = \frac{n^2\left(\frac{3n}{n^2} + \frac{1}{n^2}\right)}{n^2\left(1 + \frac{4}{n^2}\right)} = \frac{\frac{3}{n} + \frac{1}{n^2}}{1 + \frac{4}{n^2}}.$$

Alternatively, if we factor out the dominant power from the numerator ($n$) and denominator ($n^2$) separately:
$$\frac{3n+1}{n^2+4} = \frac{n\left(3 + \frac{1}{n}\right)}{n^2\left(1 + \frac{4}{n^2}\right)} = \frac{1}{n} \cdot \frac{3 + \frac{1}{n}}{1 + \frac{4}{n^2}}.$$

#### Step 1.3: Apply the Limit Laws
Since $\lim_{n\to\infty} \frac{3}{n} = 0$, $\lim_{n\to\infty} \frac{1}{n^2} = 0$, and $\lim_{n\to\infty} \frac{4}{n^2} = 0$, we apply the quotient rule for limits:
$$\lim_{n\to\infty}\frac{3n+1}{n^2+4} = \lim_{n\to\infty}\frac{\frac{3}{n} + \frac{1}{n^2}}{1 + \frac{4}{n^2}} = \frac{0 + 0}{1 + 0} = \frac{0}{1} = 0.$$

---

### Part 2: Evaluating the Second Limit

We want to compute:
$$L_2 = \lim_{n\to\infty}\frac{2n^3-n}{5n^2+1}.$$

#### Step 2.1: Identify Degrees and Indeterminate Form
- The numerator $P(n) = 2n^3 - n$ is a polynomial of degree $p = 3$.
- The denominator $Q(n) = 5n^2 + 1$ is a polynomial of degree $q = 2$.
- As $n \to \infty$, both $2n^3-n \to \infty$ and $5n^2+1 \to \infty$, which is again of the form $\left[\frac{\infty}{\infty}\right]$.

#### Step 2.2: Factor Out the Highest Power of the Denominator ($n^2$)
Let us factor $n^2$ out of both the numerator and the denominator (or factor $n^3$ from the numerator and $n^2$ from the denominator):
$$\frac{2n^3-n}{5n^2+1} = \frac{n^3\left(2 - \frac{1}{n^2}\right)}{n^2\left(5 + \frac{1}{n^2}\right)} = n \cdot \frac{2 - \frac{1}{n^2}}{5 + \frac{1}{n^2}}.$$

#### Step 2.3: Analyze the Behavior as $n \to \infty$
Let us examine the two factors in the product $n \cdot \frac{2 - \frac{1}{n^2}}{5 + \frac{1}{n^2}}$:
1. The second factor converges to a strictly positive finite constant:
   $$\lim_{n\to\infty} \frac{2 - \frac{1}{n^2}}{5 + \frac{1}{n^2}} = \frac{2 - 0}{5 + 0} = \frac{2}{5} > 0.$$
2. The first factor is $n$, which grows without bound: $\lim_{n\to\infty} n = +\infty$.

Because a sequence that grows to $+\infty$ multiplied by a sequence that converges to a positive number $\frac{2}{5} > 0$ also grows without bound toward $+\infty$, we conclude:
$$\lim_{n\to\infty}\frac{2n^3-n}{5n^2+1} = \left[(+\infty) \cdot \frac{2}{5}\right] = +\infty.$$
(The sequence diverges to $+\infty$.)

---

### Part 3: Comparison and General Observation About Polynomial Degrees

#### Comparison of the Two Cases
- **In the first limit**, the numerator has degree $1$ ($3n+1$) while the denominator has degree $2$ ($n^2+4$). Because the quadratic denominator grows much faster than the linear numerator, the denominator overwhelms the numerator, behaved asymptotically like $\frac{3n}{n^2} = \frac{3}{n}$, and pulls the entire fraction down to $0$.
- **In the second limit**, the numerator has degree $3$ ($2n^3-n$) while the denominator has degree $2$ ($5n^2+1$). Here, the cubic numerator grows much faster than the quadratic denominator. After canceling $n^2$, an extra factor of $n$ remains in the numerator (behaving asymptotically like $\frac{2n^3}{5n^2} = \frac{2}{5}n$), causing the quotient to grow without bound to $+\infty$.

#### General Observation (Degree Rule for Rational Limits at Infinity)
Consider the general rational sequence with leading coefficients $a_p \neq 0$ and $b_q \neq 0$:
$$\lim_{n\to\infty} \frac{a_p n^p + a_{p-1}n^{p-1} + \dots + a_0}{b_q n^q + b_{q-1}n^{q-1} + \dots + b_0} = \lim_{n\to\infty} n^{p-q} \cdot \frac{a_p + \frac{a_{p-1}}{n} + \dots + \frac{a_0}{n^p}}{b_q + \frac{b_{q-1}}{n} + \dots + \frac{b_0}{n^q}}.$$
Comparing the degree of the numerator ($p$) and the degree of the denominator ($q$), there are **three qualitatively distinct cases**:

1. **Degree of numerator $<$ Degree of denominator ($p < q$)**:
   The denominator grows faster than the numerator. Since $p - q < 0$, $n^{p-q} = \frac{1}{n^{q-p}} \to 0$, so the limit is always **$0$** (as in our first limit).
2. **Degree of numerator $=$ Degree of denominator ($p = q$)**:
   The numerator and denominator grow at the same rate. Since $p - q = 0$, $n^{p-q} = 1$, and the limit is a finite non-zero number equal to the **ratio of the leading coefficients**, $\frac{a_p}{b_q}$ (as seen in Exercise 1).
3. **Degree of numerator $>$ Degree of denominator ($p > q$)**:
   The numerator grows faster than the denominator. Since $p - q > 0$, $n^{p-q} \to +\infty$, so the sequence **diverges to $+\infty$ or $-\infty$**, depending on the sign of the ratio of leading coefficients $\frac{a_p}{b_q}$:
   - If $\frac{a_p}{b_q} > 0$, the limit is $+\infty$ (as in our second limit, where $\frac{2}{5} > 0$).
   - If $\frac{a_p}{b_q} < 0$, the limit is $-\infty$.

## Verification and Consistency Checks

Let us evaluate both sequences at $n = 10, 100, 1000$ to verify their contrasting behaviors:

| $n$ | First Sequence $a_n = \frac{3n+1}{n^2+4}$ | Asymptotic Approx. $\frac{3}{n}$ | Second Sequence $b_n = \frac{2n^3-n}{5n^2+1}$ | Asymptotic Approx. $\frac{2}{5}n = 0.4n$ |
| :--- | :--- | :--- | :--- | :--- |
| $10$ | $\frac{31}{104} \approx 0.29808$ | $0.300$ | $\frac{1990}{501} \approx 3.97206$ | $4.0$ |
| $100$ | $\frac{301}{10004} \approx 0.03009$ | $0.030$ | $\frac{1,999,900}{50,001} \approx 39.99720$ | $40.0$ |
| $1000$ | $\frac{3001}{1000004} \approx 0.00300$ | $0.003$ | $\frac{1,999,999,000}{5,000,001} \approx 399.99972$ | $400.0$ |

- For $a_n$, every $10$-fold increase in $n$ reduces $a_n$ by a factor of $10$, confirming $\lim_{n\to\infty} a_n = 0$.
- For $b_n$, every $10$-fold increase in $n$ multiplies $b_n$ by a factor of $10$ (closely tracking $0.4n$), confirming $\lim_{n\to\infty} b_n = +\infty$.
