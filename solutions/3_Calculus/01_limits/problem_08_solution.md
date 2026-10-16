# Problem 8: A Square Root in a Function Limit

## Problem Statement

Compute
$$\lim_{x\to4}\frac{\sqrt{x}-2}{x-4}$$
by rationalizing the numerator. Compare the idea with Exercise 3 involving a sequence.

## Theoretical Background and Concepts

When evaluating a function limit $\lim_{x\to x_0} \frac{f(x)}{g(x)}$ that yields the **indeterminate form $\left[\frac{0}{0}\right]$** and involves square roots (radicals), the hidden common factor $(x - x_0)$ is often obscured by the radical sign.

Two closely related algebraic techniques allow us to reveal and cancel the $(x - x_0)$ factor:
1. **Rationalizing the Numerator (or Denominator) via the Conjugate**:
   - The **conjugate** of $\sqrt{A} - B$ is $\sqrt{A} + B$.
   - Multiplying both the numerator and denominator by the conjugate $\sqrt{A} + B$ applies the **difference of squares identity**:
     $$(\sqrt{A} - B)(\sqrt{A} + B) = (\sqrt{A})^2 - B^2 = A - B^2.$$
   - This eliminates the square root from the numerator and explicitly produces the linear factor $(x - x_0)$, which can then be canceled against the denominator for $x \neq x_0$.
2. **Factoring as a Difference of Squares**:
   - Alternatively, for $x \ge 0$, we can view $x - x_0$ itself as a difference of squares: $x - 4 = (\sqrt{x})^2 - 2^2 = (\sqrt{x} - 2)(\sqrt{x} + 2)$, which leads to the exact same simplified expression.

## Detailed Step-by-Step Solution

### Step 1: Check Direct Substitution and Identify the Indeterminate Form

We want to evaluate:
$$L = \lim_{x\to4}\frac{\sqrt{x}-2}{x-4}.$$

Substituting $x = 4$ into the numerator and denominator:
- Numerator: $\sqrt{4} - 2 = 2 - 2 = 0$.
- Denominator: $4 - 4 = 0$.

Thus, the limit has the indeterminate form $\left[\frac{0}{0}\right]$. Notice that the domain of the function is $x \in [0, 4) \cup (4, \infty)$.

### Step 2: Rationalize the Numerator Using the Conjugate

The numerator is $\sqrt{x} - 2$, so its conjugate expression is $\sqrt{x} + 2$. Near $x = 4$, $\sqrt{x} + 2 \approx 4 \neq 0$, so we can multiply both the numerator and the denominator by $\sqrt{x} + 2$ and apply the difference of squares identity $(A - B)(A + B) = A^2 - B^2$:
$$\begin{aligned}
\frac{\sqrt{x}-2}{x-4} &= \frac{(\sqrt{x}-2)(\sqrt{x}+2)}{(x-4)(\sqrt{x}+2)} \\
&= \frac{(\sqrt{x})^2 - 2^2}{(x-4)(\sqrt{x}+2)} \\
&= \frac{x - 4}{(x-4)(\sqrt{x}+2)}.
\end{aligned}$$

### Step 3: Cancel the Common Factor $(x - 4)$ and Evaluate the Limit

Since we are taking the limit as $x \to 4$, we consider only values $x \neq 4$, so $x - 4 \neq 0$. Canceling the common factor $(x - 4)$ from the numerator and denominator gives:
$$\frac{x - 4}{(x-4)(\sqrt{x}+2)} = \frac{1}{\sqrt{x}+2} \quad (\text{for all } x \ge 0, x \neq 4).$$

Now the denominator $\sqrt{x} + 2$ is continuous at $x = 4$ and evaluates to $\sqrt{4} + 2 = 4 \neq 0$. Applying the limit laws and continuity of $\sqrt{x}$ at $x = 4$:
$$\begin{aligned}
\lim_{x\to4}\frac{\sqrt{x}-2}{x-4} &= \lim_{x\to4} \frac{1}{\sqrt{x}+2} \\
&= \frac{1}{\sqrt{4}+2} \\
&= \frac{1}{2 + 2} = \frac{1}{4} = 0.25.
\end{aligned}$$

### Step 4: Comparison with Exercise 3 Involving a Sequence

Let us compare this limit ($\lim_{x\to4}\frac{\sqrt{x}-2}{x-4} = \frac{1}{4}$) with Exercise 3 ($\lim_{n\to\infty}(\sqrt{n^2+5n} - n) = \frac{5}{2}$):

#### Similarities (The Core Algebraic Idea):
1. **Use of the Conjugate and Difference of Squares**: Both exercises rely on the exact same algebraic mechanism—multiplying and dividing by the conjugate $\sqrt{A} + B$ and using $(\sqrt{A} - B)(\sqrt{A} + B) = A - B^2$ to remove the square root where two nearly equal quantities are being subtracted.
2. **Converting a Vanishing/Canceling Difference into a Non-Zero Sum**:
   - In Exercise 3, $\sqrt{n^2+5n} - n$ had two terms whose ratio approached $1$, and conjugation moved the radical to the denominator as $\sqrt{n^2+5n} + n$, where the leading terms added ($1 + 1 = 2$) instead of canceling.
   - In Exercise 8, $\sqrt{x} - 2$ approached $2 - 2 = 0$ as $x \to 4$, and conjugation moved the radical to the denominator as $\sqrt{x} + 2$, where the two terms added ($2 + 2 = 4 \neq 0$) instead of subtracting to zero.

#### Differences (Context and Indeterminate Form):
1. **Type of Indeterminate Form**:
   - Exercise 3 resolved an **$[\infty - \infty]$** indeterminate form at infinity ($n \to \infty$), where squaring canceled the highest-degree terms ($n^2 - n^2 = 0$) and left the sub-leading growth term $5n$.
   - Exercise 8 resolves a **$\left[\frac{0}{0}\right]$** indeterminate form at a finite point ($x \to 4$), where squaring exposes the vanishing linear factor $(x - 4)$ so that it can be canceled with the $(x - 4)$ already present in the denominator.
2. **Discrete vs. Continuous Limit Point**:
   - Exercise 3 studied a discrete sequence as $n \to \infty$, requiring us to factor out the highest power $n$ after conjugation.
   - Exercise 8 studies a real function approaching a finite point $x \to 4$, so once $(x - 4)$ is canceled, we finish immediately by direct substitution $x = 4$.

**Final Answer:**
$$\lim_{x\to4}\frac{\sqrt{x}-2}{x-4} = \frac{1}{4}.$$

## Verification and Consistency Checks

1. **Numerical Table Near $x = 4$**: Let us evaluate $f(x) = \frac{\sqrt{x}-2}{x-4}$ at values of $x$ approaching $4$ from both the left and the right:

   | $x$ | $\sqrt{x} - 2$ | $x - 4$ | $f(x) = \frac{\sqrt{x}-2}{x-4}$ | Compare with $\frac{1}{\sqrt{x}+2}$ |
   | :--- | :--- | :--- | :--- | :--- |
   | $3.9$ | $-0.02515823$ | $-0.1$ | $0.2515823$ | $\frac{1}{1.97484177 + 2} \approx 0.2515823$ |
   | $3.99$ | $-0.00250156$ | $-0.01$ | $0.2501563$ | $\frac{1}{1.99749844 + 2} \approx 0.2501563$ |
   | $3.9999$ | $-0.0000250002$ | $-0.0001$ | $0.2500016$ | $\approx 0.2500016$ |
   | $4.0001$ | $+0.0000249998$ | $+0.0001$ | $0.2499984$ | $\approx 0.2499984$ |
   | $4.01$ | $+0.00249844$ | $+0.01$ | $0.2498439$ | $\approx 0.2498439$ |
   | $4.1$ | $+0.02484567$ | $+0.1$ | $0.2484567$ | $\approx 0.2484567$ |

   Both sides converge smoothly to $0.25 = \frac{1}{4}$.

2. **Derivative Interpretation Check**: Recall the definition of the derivative of $g(x) = \sqrt{x}$ at $x = 4$:
   $$g'(4) = \lim_{x\to 4} \frac{\sqrt{x} - \sqrt{4}}{x - 4} = \lim_{x\to 4} \frac{\sqrt{x} - 2}{x - 4}.$$
   Since $g'(x) = \frac{1}{2\sqrt{x}}$, we have $g'(4) = \frac{1}{2\sqrt{4}} = \frac{1}{4}$, which confirms our limit!
