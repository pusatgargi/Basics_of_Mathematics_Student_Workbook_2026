# Problem 4: Powers and Oscillation

## Problem Statement

Analyze
$$\left(\frac23\right)^n,\qquad \left(\frac32\right)^n,\qquad (-1)^n,\qquad \frac{(-1)^n}{n}.$$
For each sequence, describe the type of behavior and justify your answer.

## Theoretical Background and Concepts

Sequences $(a_n)$ can exhibit several fundamental types of asymptotic behavior as $n \to \infty$:
1. **Monotonic Convergence to a Finite Limit**: The terms move steadily in one direction (either strictly decreasing or strictly increasing) and approach a finite real number $L$.
2. **Monotonic Divergence to Infinity**: The terms grow without bound in one direction ($a_n \to +\infty$ or $a_n \to -\infty$).
3. **Divergence by Oscillation**: The terms alternate or cycle between different values without settling down toward any single number. If a sequence has two subsequences that converge to two different limits $L_1 \neq L_2$, then the sequence **does not have a limit** (it diverges).
4. **Damped Oscillation (Convergent Oscillation)**: The terms alternate in sign (oscillate around a limit $L$), but the amplitude of the oscillation shrinks to $0$ as $n \to \infty$. Such a sequence **converges** to $L$.

Key mathematical tools for justifying these behaviors include:
- **Geometric Sequence Limit Theorem**: For a geometric sequence $a_n = q^n$:
  $$\lim_{n\to\infty} q^n = \begin{cases} 0 & \text{if } |q| < 1, \\ 1 & \text{if } q = 1, \\ +\infty & \text{if } q > 1, \\ \text{does not exist (diverges by oscillation)} & \text{if } q \le -1. \end{cases}$$
- **Bernoulli's Inequality**: For any real $x > -1$ and integer $n \ge 1$, $(1 + x)^n \ge 1 + nx$.
- **The Squeeze Theorem (Sandwich Theorem) / Absolute Value Property**: If $b_n \le a_n \le c_n$ for all $n$ and $\lim_{n\to\infty} b_n = \lim_{n\to\infty} c_n = L$, then $\lim_{n\to\infty} a_n = L$. In particular, since $-|a_n| \le a_n \le |a_n|$, if $\lim_{n\to\infty} |a_n| = 0$, then $\lim_{n\to\infty} a_n = 0$.

## Detailed Step-by-Step Solution

### 1. First Sequence: $a_n = \left(\frac{2}{3}\right)^n$

- **Type of Behavior**: **Monotonically decreasing and convergent to $0$** ($\lim_{n\to\infty} \left(\frac{2}{3}\right)^n = 0$).
- **Justification**:
  1. This is a geometric sequence $q^n$ with base $q = \frac{2}{3}$. Since $0 < \frac{2}{3} < 1$, each successive term is obtained by multiplying the previous term by $\frac{2}{3} < 1$:
     $$a_{n+1} = \left(\frac{2}{3}\right)^{n+1} = \frac{2}{3} a_n < a_n,$$
     and $a_n > 0$ for all $n$. Thus, $(a_n)$ is strictly decreasing and bounded below by $0$.
  2. To prove rigorously that the limit is $0$, write $\frac{2}{3} = \frac{1}{3/2} = \frac{1}{1 + \frac{1}{2}}$. By Bernoulli's inequality, $(1 + \frac{1}{2})^n \ge 1 + \frac{n}{2} > \frac{n}{2}$. Taking reciprocals gives:
     $$0 < \left(\frac{2}{3}\right)^n = \frac{1}{\left(1 + \frac{1}{2}\right)^n} < \frac{2}{n}.$$
     Since $\lim_{n\to\infty} 0 = 0$ and $\lim_{n\to\infty} \frac{2}{n} = 0$, the Squeeze Theorem guarantees that:
     $$\lim_{n\to\infty} \left(\frac{2}{3}\right)^n = 0.$$

---

### 2. Second Sequence: $b_n = \left(\frac{3}{2}\right)^n$

- **Type of Behavior**: **Monotonically increasing and divergent to $+\infty$** ($\lim_{n\to\infty} \left(\frac{3}{2}\right)^n = +\infty$).
- **Justification**:
  1. This is a geometric sequence $q^n$ with base $q = \frac{3}{2} = 1.5 > 1$. Each term is $1.5$ times larger than the preceding term:
     $$b_{n+1} = \frac{3}{2} b_n > b_n > 0,$$
     so the sequence is strictly increasing.
  2. Writing $\frac{3}{2} = 1 + \frac{1}{2}$ and applying Bernoulli's inequality for $n \ge 1$:
     $$\left(\frac{3}{2}\right)^n = \left(1 + \frac{1}{2}\right)^n \ge 1 + \frac{n}{2}.$$
     Since $\lim_{n\to\infty} \left(1 + \frac{n}{2}\right) = +\infty$, and $b_n \ge 1 + \frac{n}{2}$ for all $n \ge 1$, the comparison property for infinite limits implies that $b_n$ grows without bound:
     $$\lim_{n\to\infty} \left(\frac{3}{2}\right)^n = +\infty.$$

---

### 3. Third Sequence: $c_n = (-1)^n$

- **Type of Behavior**: **Bounded, periodic oscillation; divergent (the limit does not exist)**.
- **Justification**:
  1. Writing out the terms for $n = 1, 2, 3, 4, \dots$:
     $$c_1 = -1, \quad c_2 = 1, \quad c_3 = -1, \quad c_4 = 1, \quad \dots$$
     The sequence alternates forever between $-1$ and $+1$ with constant amplitude.
  2. Consider the subsequence of **even indices** ($n = 2k$) and the subsequence of **odd indices** ($n = 2k-1$):
     $$\lim_{k\to\infty} c_{2k} = \lim_{k\to\infty} (-1)^{2k} = \lim_{k\to\infty} 1 = 1,$$
     $$\lim_{k\to\infty} c_{2k-1} = \lim_{k\to\infty} (-1)^{2k-1} = \lim_{k\to\infty} (-1) = -1.$$
  3. A sequence converges to a limit $L$ if and only if *every* subsequence converges to the same limit $L$. Because the even and odd subsequences converge to two distinct values ($1 \neq -1$), the distance between consecutive terms is $|c_{n+1} - c_n| = 2$, so the terms never settle near any single value. Therefore, $\lim_{n\to\infty} (-1)^n$ **does not exist**.

---

### 4. Fourth Sequence: $d_n = \frac{(-1)^n}{n}$

- **Type of Behavior**: **Damped oscillation (alternating sign with decreasing magnitude); convergent to $0$** ($\lim_{n\to\infty} \frac{(-1)^n}{n} = 0$).
- **Justification**:
  1. Writing out the first few terms:
     $$d_1 = -1, \quad d_2 = \frac{1}{2}, \quad d_3 = -\frac{1}{3}, \quad d_4 = \frac{1}{4}, \quad d_5 = -\frac{1}{5}, \quad \dots$$
     The terms alternate between negative (for odd $n$) and positive (for even $n$), jumping back and forth across $0$.
  2. However, unlike $(-1)^n$, the magnitude (distance from $0$) of $d_n$ shrinks toward zero because of the denominator $n$:
     $$|d_n| = \left|\frac{(-1)^n}{n}\right| = \frac{1}{n}.$$
  3. Since $-1 \le (-1)^n \le 1$ for all $n \ge 1$, dividing by $n > 0$ yields the bounding inequality:
     $$-\frac{1}{n} \le \frac{(-1)^n}{n} \le \frac{1}{n}.$$
     Because both outer bounding sequences converge to $0$:
     $$\lim_{n\to\infty} \left(-\frac{1}{n}\right) = 0 \qquad \text{and} \qquad \lim_{n\to\infty} \frac{1}{n} = 0,$$
     the **Squeeze Theorem** guarantees that the middle sequence is trapped between them and must also converge to $0$:
     $$\lim_{n\to\infty} \frac{(-1)^n}{n} = 0.$$
  4. **Key Takeaway**: This example demonstrates that **oscillation does not prevent convergence**, provided the amplitude of the oscillation decays to zero as $n \to \infty$.

## Verification and Consistency Checks

Let us inspect a comparative table of values for all four sequences across several indices $n$:

| $n$ | $a_n = \left(\frac{2}{3}\right)^n$ | $b_n = \left(\frac{3}{2}\right)^n$ | $c_n = (-1)^n$ | $d_n = \frac{(-1)^n}{n}$ |
| :--- | :--- | :--- | :--- | :--- |
| $1$ | $0.66667$ | $1.50000$ | $-1$ | $-1.00000$ |
| $2$ | $0.44444$ | $2.25000$ | $+1$ | $+0.50000$ |
| $3$ | $0.29630$ | $3.37500$ | $-1$ | $-0.33333$ |
| $4$ | $0.19753$ | $5.06250$ | $+1$ | $+0.25000$ |
| $10$ | $0.01734$ | $57.66504$ | $+1$ | $+0.10000$ |
| $20$ | $0.00030$ | $3325.25673$ | $+1$ | $+0.05000$ |
| $21$ | $0.00020$ | $4987.88509$ | $-1$ | $-0.04762$ |
| **Limit ($n\to\infty$)** | **$0$ (Converges)** | **$+\infty$ (Diverges)** | **DNE (Diverges)** | **$0$ (Converges)** |

Also note the reciprocal consistency check between $a_n$ and $b_n$: $a_n \cdot b_n = \left(\frac{2}{3} \cdot \frac{3}{2}\right)^n = 1^n = 1$ for every $n$, which is consistent with $a_n \to 0^+$ while $b_n = \frac{1}{a_n} \to +\infty$.
