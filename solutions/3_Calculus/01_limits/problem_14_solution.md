# Problem 14: A $0/0$ Limit with Trigonometry

## Problem Statement

Compute
$$\lim_{x\to0}\frac{1-\cos x}{x^2}.$$
Justify the result without using l'Hôpital's rule, using a trigonometric identity and the fundamental limit.

## Theoretical Background and Concepts

When evaluating trigonometric limits as $x \to 0$ that involve $1 - \cos x$, direct substitution yields $1 - \cos 0 = 1 - 1 = 0$. In the quotient $\frac{1 - \cos x}{x^2}$, both numerator and denominator approach $0$, giving the **indeterminate form $\left[\frac{0}{0}\right]$**.

Notice why $x^2$ (rather than $x$) appears in the denominator: near $x = 0$, $\cos x$ has a horizontal tangent at its peak $\cos 0 = 1$, so $1 - \cos x$ vanishes quadratically in $x$. Without using derivatives or l'Hôpital's rule, we can reduce $\frac{1 - \cos x}{x^2}$ directly to the **fundamental trigonometric limit**
$$\lim_{u\to 0} \frac{\sin u}{u} = 1$$
by using either of two standard trigonometric identities:

1. **Half-Angle / Double-Angle Identity (Power-Reduction Formula)**:
   Recall the cosine double-angle identity $\cos(2\theta) = 1 - 2\sin^2\theta$. Setting $2\theta = x$ (so $\theta = \frac{x}{2}$) and rearranging gives:
   $$1 - \cos x = 2\sin^2\left(\frac{x}{2}\right).$$
   This directly converts the difference $1 - \cos x$ into a square of a sine function!

2. **Trigonometric Conjugation + Pythagorean Identity**:
   Alternatively, multiplying numerator and denominator by the trigonometric conjugate $1 + \cos x$ uses the difference of squares and the Pythagorean identity $\sin^2 x + \cos^2 x = 1$:
   $$(1 - \cos x)(1 + \cos x) = 1 - \cos^2 x = \sin^2 x.$$

Below, we present both methods in full detail so that their equivalence is completely clear.

## Detailed Step-by-Step Solution

### Step 1: Verify the Indeterminate Form

We want to compute:
$$L = \lim_{x\to0}\frac{1-\cos x}{x^2}.$$

As $x \to 0$:
- Numerator: $1 - \cos 0 = 1 - 1 = 0$.
- Denominator: $0^2 = 0$.

Thus, the limit is an indeterminate form of type $\left[\frac{0}{0}\right]$.

---

### Step 2: Method 1 — Using the Half-Angle Identity $1 - \cos x = 2\sin^2\left(\frac{x}{2}\right)$

#### Step 2.1: Apply the Half-Angle Identity
Substitute the trigonometric identity $1 - \cos x = 2\sin^2\left(\frac{x}{2}\right)$ into the numerator:
$$\frac{1 - \cos x}{x^2} = \frac{2\sin^2\left(\frac{x}{2}\right)}{x^2}.$$

#### Step 2.2: Group the Quotient to Match the Fundamental Limit
Notice that $\sin^2\left(\frac{x}{2}\right) = \left(\sin\frac{x}{2}\right)^2$ has argument $\frac{x}{2}$. To match $\left(\frac{\sin(x/2)}{x/2}\right)^2$, we rewrite $x^2$ in the denominator in terms of $\left(\frac{x}{2}\right)^2 = \frac{x^2}{4}$, or equivalently multiply and divide the denominator by $4$:
$$\begin{aligned}
\frac{2\sin^2\left(\frac{x}{2}\right)}{x^2} &= \frac{2\sin^2\left(\frac{x}{2}\right)}{4 \cdot \left(\frac{x}{2}\right)^2} \\
&= \frac{2}{4} \cdot \frac{\sin^2\left(\frac{x}{2}\right)}{\left(\frac{x}{2}\right)^2} \\
&= \frac{1}{2} \cdot \left(\frac{\sin\frac{x}{2}}{\frac{x}{2}}\right)^2.
\end{aligned}$$

#### Step 2.3: Apply the Fundamental Trigonometric Limit
Let $u = \frac{x}{2}$. As $x \to 0$, we have $u = \frac{x}{2} \to 0$. By the fundamental trigonometric limit,
$$\lim_{x\to 0} \frac{\sin\frac{x}{2}}{\frac{x}{2}} = \lim_{u\to 0} \frac{\sin u}{u} = 1.$$
Using the product and power rules for limits:
$$\begin{aligned}
\lim_{x\to0}\frac{1-\cos x}{x^2} &= \lim_{x\to 0} \left[\frac{1}{2} \cdot \left(\frac{\sin\frac{x}{2}}{\frac{x}{2}}\right)^2\right] \\
&= \frac{1}{2} \cdot \left(\lim_{u\to 0} \frac{\sin u}{u}\right)^2 \\
&= \frac{1}{2} \cdot 1^2 = \frac{1}{2}.
\end{aligned}$$

---

### Step 3: Method 2 — Using the Pythagorean Identity $\sin^2 x + \cos^2 x = 1$ (Conjugate Method)

We can also derive the exact same result using the Pythagorean identity $1 - \cos^2 x = \sin^2 x$:
1. Multiply the numerator and denominator of $\frac{1 - \cos x}{x^2}$ by $1 + \cos x$ (which approaches $1 + 1 = 2 \neq 0$ as $x \to 0$):
   $$\begin{aligned}
   \frac{1 - \cos x}{x^2} &= \frac{(1 - \cos x)(1 + \cos x)}{x^2(1 + \cos x)} \\
   &= \frac{1 - \cos^2 x}{x^2(1 + \cos x)} \\
   &= \frac{\sin^2 x}{x^2(1 + \cos x)}.
   \end{aligned}$$
2. Separate the factors to isolate $\left(\frac{\sin x}{x}\right)^2$:
   $$\frac{\sin^2 x}{x^2(1 + \cos x)} = \left(\frac{\sin x}{x}\right)^2 \cdot \frac{1}{1 + \cos x}.$$
3. Since $\lim_{x\to 0} \frac{\sin x}{x} = 1$ and $\lim_{x\to 0} \cos x = \cos 0 = 1$ (as cosine is continuous at $0$), the product rule for limits gives:
   $$\begin{aligned}
   \lim_{x\to 0} \frac{1 - \cos x}{x^2} &= \left(\lim_{x\to 0} \frac{\sin x}{x}\right)^2 \cdot \lim_{x\to 0} \frac{1}{1 + \cos x} \\
   &= 1^2 \cdot \frac{1}{1 + \cos 0} \\
   &= 1 \cdot \frac{1}{1 + 1} = \frac{1}{2}.
   \end{aligned}$$

**Final Answer:**
$$\lim_{x\to0}\frac{1-\cos x}{x^2} = \frac{1}{2}.$$

## Verification and Consistency Checks

1. **Numerical Evaluation Near $x = 0$**:
   Since $f(x) = \frac{1-\cos x}{x^2}$ is an even function ($f(-x) = f(x)$), let us evaluate $f(x)$ for small values of $x$ (in radians):

   | $x$ (radians) | $1 - \cos x$ | $x^2$ | $f(x) = \frac{1-\cos x}{x^2}$ | Error $\left|f(x) - 0.5\right|$ |
   | :--- | :--- | :--- | :--- | :--- |
   | $\pm 0.5$ | $0.12241744$ | $0.25$ | $0.48966975$ | $0.01033025$ |
   | $\pm 0.1$ | $0.0049958347$ | $0.01$ | $0.49958347$ | $0.00041653$ |
   | $\pm 0.01$ | $0.000049999583$ | $0.0001$ | $0.49999583$ | $0.00000417$ |
   | $\pm 0.001$ | $4.99999958 \times 10^{-7}$ | $10^{-6}$ | $0.49999996$ | $0.00000004$ |

   The values converge rapidly to $0.5 = \frac{1}{2}$.

2. **Taylor Expansion Consistency Check**: Recall the Maclaurin series $\cos x = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \dots = 1 - \frac{x^2}{2} + \frac{x^4}{24} - \dots$ Subtracting from $1$ and dividing by $x^2$ gives $\frac{1 - \cos x}{x^2} = \frac{1}{2} - \frac{x^2}{24} + \dots$, which at $x = 0.1$ predicts $0.5 - \frac{0.01}{24} \approx 0.5 - 0.00041667 = 0.49958333$, matching our table to $7$ decimal places!
