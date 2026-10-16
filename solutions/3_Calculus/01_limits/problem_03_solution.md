# Problem 3: A Square Root and Removing an Indeterminate Form

## Problem Statement

Compute
$$\lim_{n\to\infty}\left(\sqrt{n^2+5n}-n\right).$$
Use the conjugate expression and explain why this transformation removes the difficulty.

## Theoretical Background and Concepts

When evaluating the limit of a difference of two sequences $\lim_{n\to\infty} (A_n - B_n)$ where both $A_n \to +\infty$ and $B_n \to +\infty$, we encounter the **indeterminate form $[\infty - \infty]$**.

It is a common misconception to think that $\infty - \infty = 0$. In reality, $\infty$ is not a real number, and the limit of $A_n - B_n$ depends on how closely $A_n$ and $B_n$ track each other as $n$ grows. Notice too that simply factoring out $n$ from $\sqrt{n^2+5n} - n$ gives:
$$n\left(\sqrt{1 + \frac{5}{n}} - 1\right),$$
which turns $[\infty - \infty]$ into $[\infty \cdot 0]$—still an indeterminate form!

When the expression $A_n - B_n$ involves square roots, the standard algebraic technique to resolve $[\infty - \infty]$ is **multiplying and dividing by the conjugate expression**:
- The **conjugate** of $A - B$ is $A + B$.
- By the **difference of squares identity**,
  $$(A - B)(A + B) = A^2 - B^2.$$
- Multiplying $A - B$ by $\frac{A + B}{A + B} = 1$ transforms the difference into a fraction:
  $$A - B = \frac{(A - B)(A + B)}{A + B} = \frac{A^2 - B^2}{A + B}.$$
  This eliminates the square root in the numerator, allows the leading quadratic terms $n^2$ to cancel out by subtraction, and converts the denominator into a *sum* of two positive terms ($A + B$), which no longer suffers from cancellation!

## Detailed Step-by-Step Solution

### Step 1: Identify the Indeterminate Form

We wish to compute:
$$L = \lim_{n\to\infty}\left(\sqrt{n^2+5n}-n\right).$$

As $n \to \infty$, we have $\sqrt{n^2+5n} \to +\infty$ and $n \to +\infty$. Therefore, the expression is an indeterminate form of type $[\infty - \infty]$. Because the leading term under the radical is $n^2$ and $\sqrt{n^2} = n$, the two terms $\sqrt{n^2+5n}$ and $n$ have the exact same leading growth rate ($n$), so naive inspection cannot tell us what remains after subtracting $n$ from $\sqrt{n^2+5n}$.

### Step 2: Multiply and Divide by the Conjugate Expression

Let $A = \sqrt{n^2+5n}$ and $B = n$. The conjugate of $\sqrt{n^2+5n} - n$ is $\sqrt{n^2+5n} + n$. Since $n \ge 1$, the conjugate $\sqrt{n^2+5n} + n$ is strictly positive (and never zero).

Multiplying and dividing by $\sqrt{n^2+5n} + n$ and applying the difference of squares identity $(A - B)(A + B) = A^2 - B^2$, we obtain:
$$\begin{aligned}
\sqrt{n^2+5n} - n &= \frac{\left(\sqrt{n^2+5n} - n\right)\left(\sqrt{n^2+5n} + n\right)}{\sqrt{n^2+5n} + n} \\
&= \frac{\left(\sqrt{n^2+5n}\right)^2 - n^2}{\sqrt{n^2+5n} + n} \\
&= \frac{(n^2 + 5n) - n^2}{\sqrt{n^2+5n} + n} \\
&= \frac{5n}{\sqrt{n^2+5n} + n}.
\end{aligned}$$

### Step 3: Factor Out the Dominant Power $n$ from the Quotient

Now our expression is $\frac{5n}{\sqrt{n^2+5n} + n}$, which has the form $\left[\frac{\infty}{\infty}\right]$, where both numerator and denominator grow linearly with $n$. We can now apply the standard dominant-term factoring method from Exercise 1!

For $n \ge 1$ (so $n > 0$ and $\sqrt{n^2} = |n| = n$), we factor $n^2$ out of the expression inside the square root in the denominator:
$$\sqrt{n^2+5n} = \sqrt{n^2\left(1 + \frac{5}{n}\right)} = \sqrt{n^2}\sqrt{1 + \frac{5}{n}} = n\sqrt{1 + \frac{5}{n}}.$$

Substituting this into the denominator and factoring out $n$:
$$\sqrt{n^2+5n} + n = n\sqrt{1 + \frac{5}{n}} + n = n\left(\sqrt{1 + \frac{5}{n}} + 1\right).$$

Now substitute this back into the fraction and cancel the common factor $n$:
$$\frac{5n}{\sqrt{n^2+5n} + n} = \frac{5n}{n\left(\sqrt{1 + \frac{5}{n}} + 1\right)} = \frac{5}{\sqrt{1 + \frac{5}{n}} + 1}.$$

### Step 4: Evaluate the Limit

Since $\lim_{n\to\infty} \frac{5}{n} = 0$ and the square root function $\sqrt{u}$ is continuous for $u > 0$, we can pass the limit inside the square root:
$$\begin{aligned}
\lim_{n\to\infty}\left(\sqrt{n^2+5n}-n\right) &= \lim_{n\to\infty} \frac{5}{\sqrt{1 + \frac{5}{n}} + 1} \\
&= \frac{5}{\sqrt{1 + \lim_{n\to\infty}\frac{5}{n}} + 1} \\
&= \frac{5}{\sqrt{1 + 0} + 1} \\
&= \frac{5}{1 + 1} = \frac{5}{2} = 2.5.
\end{aligned}$$

### Step 5: Explanation of Why Conjugation Removes the Difficulty

Why did multiplying by the conjugate resolve the difficulty?
1. **Elimination of the Leading Cancellation via Squaring**: In the original difference $\sqrt{n^2+5n} - n$, the dominant $n^2$ term is trapped inside the square root, preventing us from directly subtracting $n$ from $\sqrt{n^2+5n}$. Using $(A-B)(A+B) = A^2 - B^2$ squares the radical to produce $(n^2 + 5n) - n^2 = 5n$. Thus, the two competing dominant terms ($n^2$ and $n^2$) cancel out **exact-algebraically** in the numerator, exposing the true sub-leading difference term $5n$.
2. **Replacing a Difference of Equal-Order Terms with a Sum**: In the denominator, the conjugate $\sqrt{n^2+5n} + n$ has a **plus** sign instead of a minus sign. When we factor out the dominant power $n$, the leading coefficients **add** ($\sqrt{1 + 0} + 1 = 1 + 1 = 2 \neq 0$) instead of canceling to $0$ ($\sqrt{1+0} - 1 = 0$). Converting a near-zero difference into a non-zero sum in the denominator removes the indeterminacy completely.

**Final Answer:**
$$\lim_{n\to\infty}\left(\sqrt{n^2+5n}-n\right) = \frac{5}{2}.$$

## Verification and Consistency Checks

1. **Numerical Check**: Let us compute $a_n = \sqrt{n^2+5n} - n$ for increasing values of $n$:
   - For $n = 10$: $\sqrt{100 + 50} - 10 = \sqrt{150} - 10 \approx 12.24745 - 10 = 2.24745$.
   - For $n = 100$: $\sqrt{10000 + 500} - 100 = \sqrt{10500} - 100 \approx 102.46951 - 100 = 2.46951$.
   - For $n = 1000$: $\sqrt{1005000} - 1000 \approx 1002.49688 - 1000 = 2.49688$.
   - For $n = 10000$: $\sqrt{100050000} - 10000 \approx 10002.49969 - 10000 = 2.49969$.
   As $n$ increases, $a_n$ clearly approaches $2.5 = \frac{5}{2}$.

2. **Completing the Square Intuition Check**: Notice that
   $$n^2 + 5n = \left(n + \frac{5}{2}\right)^2 - \frac{25}{4}.$$
   For very large $n$, the constant $-\frac{25}{4}$ is tiny compared to $\left(n + \frac{5}{2}\right)^2$, so $\sqrt{n^2+5n} \approx \sqrt{\left(n + \frac{5}{2}\right)^2} = n + \frac{5}{2}$. Subtracting $n$ leaves $\left(n + \frac{5}{2}\right) - n = \frac{5}{2}$, which aligns with our exact limit!
