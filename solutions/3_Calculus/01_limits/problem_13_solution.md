# Problem 13: Fundamental Trigonometric Limit

## Problem Statement

Using
$$\lim_{x\to0}\frac{\sin x}{x}=1,$$
compute
$$\lim_{x\to0}\frac{\sin5x}{x},\qquad \lim_{x\to0}\frac{\sin2x}{\sin3x}.$$
In each case, show how you reduce the expression to the fundamental limit.

## Theoretical Background and Concepts

One of the cornerstones of calculus is the **fundamental trigonometric limit** (where the angle $x$ is measured in radians):
$$\lim_{x\to 0} \frac{\sin x}{x} = 1.$$
Because $\sin 0 = 0$, this limit resolves a fundamental $\left[\frac{0}{0}\right]$ indeterminate form and captures the geometric fact that for very small angles $x$ (in radians), the chord/sine length $\sin x$ is nearly identical to the arc length $x$ ($\sin x \approx x$ as $x \to 0$). Taking the reciprocal also gives:
$$\lim_{x\to 0} \frac{x}{\sin x} = \frac{1}{\lim_{x\to 0} \frac{\sin x}{x}} = \frac{1}{1} = 1.$$

**Generalization via Substitution (Matching the Argument)**:
What matters in the fundamental trigonometric limit is not the letter $x$, but that the **exact same non-zero expression $u(x)$** that sits inside $\sin(u(x))$ also sits in the denominator, and that $u(x) \to 0$:
$$\lim_{u\to 0} \frac{\sin u}{u} = 1.$$
Specifically, if $u = kx$ for any non-zero constant $k \neq 0$, then as $x \to 0$, we also have $u = kx \to 0$, so:
$$\lim_{x\to 0} \frac{\sin(kx)}{kx} = \lim_{u\to 0} \frac{\sin u}{u} = 1.$$
Therefore, whenever we encounter $\sin(kx)$ in a limit as $x \to 0$, our algebraic strategy is to **multiply and divide by $kx$** (or by the missing constant $k$) to create the exact block $\frac{\sin(kx)}{kx}$.

## Detailed Step-by-Step Solution

### Part 1: Evaluating $\lim_{x\to0}\frac{\sin5x}{x}$

#### Step 1.1: Identify the Indeterminate Form and the Argument of Sine
As $x \to 0$, both the numerator $\sin(5x) \to \sin 0 = 0$ and the denominator $x \to 0$, producing the indeterminate form $\left[\frac{0}{0}\right]$.
Notice that the argument of the sine function in the numerator is **$5x$**, whereas the denominator is only **$x$**.

#### Step 1.2: Multiply and Divide by $5$ to Match the Argument
To apply the fundamental limit $\lim_{u\to 0}\frac{\sin u}{u} = 1$ with $u = 5x$, we need $5x$ in the denominator directly beneath $\sin(5x)$. For $x \neq 0$, we multiply both the numerator and denominator by $5$:
$$\frac{\sin 5x}{x} = \frac{5 \cdot \sin 5x}{5x} = 5 \cdot \frac{\sin 5x}{5x}.$$

#### Step 1.3: Apply the Fundamental Limit via Substitution $u = 5x$
Let $u = 5x$. As $x \to 0$, we have $u = 5x \to 0$ (and for $x \neq 0$, $u \neq 0$). Using the constant multiple rule for limits:
$$\begin{aligned}
\lim_{x\to 0} \frac{\sin 5x}{x} &= \lim_{x\to 0} \left(5 \cdot \frac{\sin 5x}{5x}\right) \\
&= 5 \cdot \lim_{x\to 0} \frac{\sin 5x}{5x} \\
&= 5 \cdot \lim_{u\to 0} \frac{\sin u}{u} \\
&= 5 \cdot 1 = 5.
\end{aligned}$$

---

### Part 2: Evaluating $\lim_{x\to0}\frac{\sin2x}{\sin3x}$

#### Step 2.1: Identify the Indeterminate Form
As $x \to 0$, both $\sin(2x) \to 0$ and $\sin(3x) \to 0$, so this is also an indeterminate form of type $\left[\frac{0}{0}\right]$.
Here we have **two** sine expressions: $\sin(2x)$ in the numerator (with argument $2x$) and $\sin(3x)$ in the denominator (with argument $3x$).

#### Step 2.2: Introduce $2x$ and $3x$ to Reduce Both Sine Terms to the Fundamental Pattern
For $x$ near $0$ with $x \neq 0$, we want to pair $\sin(2x)$ with $2x$ and $\sin(3x)$ with $3x$. We can do this by dividing both the numerator and denominator by $x$, and then multiplying and dividing the top by $2$ and the bottom by $3$:
$$\begin{aligned}
\frac{\sin 2x}{\sin 3x} &= \frac{\frac{\sin 2x}{x}}{\frac{\sin 3x}{x}} \\
&= \frac{2 \cdot \frac{\sin 2x}{2x}}{3 \cdot \frac{\sin 3x}{3x}} \\
&= \frac{2}{3} \cdot \frac{\frac{\sin 2x}{2x}}{\frac{\sin 3x}{3x}}.
\end{aligned}$$
*(Equivalently, written as a product: $\frac{\sin 2x}{\sin 3x} = \frac{\sin 2x}{2x} \cdot \frac{3x}{\sin 3x} \cdot \frac{2x}{3x} = \frac{2}{3} \cdot \frac{\sin 2x}{2x} \cdot \frac{1}{\frac{\sin 3x}{3x}}$.)*

#### Step 2.3: Apply the Fundamental Limit to Both Parts
- Let $u = 2x$. As $x \to 0$, $u \to 0$, so:
  $$\lim_{x\to 0} \frac{\sin 2x}{2x} = \lim_{u\to 0} \frac{\sin u}{u} = 1.$$
- Let $v = 3x$. As $x \to 0$, $v \to 0$, so:
  $$\lim_{x\to 0} \frac{\sin 3x}{3x} = \lim_{v\to 0} \frac{\sin v}{v} = 1.$$

Since the denominator limit is $1 \neq 0$, we apply the quotient and constant multiple laws for limits:
$$\begin{aligned}
\lim_{x\to 0} \frac{\sin 2x}{\sin 3x} &= \frac{2}{3} \cdot \frac{\lim_{x\to 0} \frac{\sin 2x}{2x}}{\lim_{x\to 0} \frac{\sin 3x}{3x}} \\
&= \frac{2}{3} \cdot \frac{1}{1} = \frac{2}{3}.
\end{aligned}$$

**Final Answers:**
$$\lim_{x\to0}\frac{\sin5x}{x} = 5, \qquad \lim_{x\to0}\frac{\sin2x}{\sin3x} = \frac{2}{3}.$$

## Verification and Consistency Checks

1. **Small-Angle Approximation Intuition**: For small $x$ (in radians), $\sin(\theta) \approx \theta$. Thus:
   - $\frac{\sin 5x}{x} \approx \frac{5x}{x} = 5$.
   - $\frac{\sin 2x}{\sin 3x} \approx \frac{2x}{3x} = \frac{2}{3} \approx 0.666667$.
2. **Numerical Evaluation Table (with $x$ in radians)**:
   Since both $\frac{\sin 5x}{x}$ and $\frac{\sin 2x}{\sin 3x}$ are **even functions** ($\frac{\sin(-5x)}{-x} = \frac{-\sin 5x}{-x} = \frac{\sin 5x}{x}$), their values at $-x$ and $+x$ are identical:

   | $x$ (radians) | $f_1(x) = \frac{\sin 5x}{x}$ | Error $|f_1(x) - 5|$ | $f_2(x) = \frac{\sin 2x}{\sin 3x}$ | Error $\left|f_2(x) - \frac{2}{3}\right|$ |
   | :--- | :--- | :--- | :--- | :--- |
   | $\pm 0.1$ | $4.79425539$ | $0.20574461$ | $0.67229500$ | $0.00562833$ |
   | $\pm 0.01$ | $4.99791693$ | $0.00208307$ | $0.66672223$ | $0.00005556$ |
   | $\pm 0.001$ | $4.99997917$ | $0.00002083$ | $0.66666722$ | $0.00000056$ |
   | $\pm 0.0001$ | $4.99999979$ | $0.00000021$ | $0.66666667$ | $0.00000001$ |

   Both numerical sequences converge quadratically (error $\propto x^2$) to $5$ and $\frac{2}{3}$, respectively.
