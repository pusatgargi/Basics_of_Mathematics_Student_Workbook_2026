# Problem 9: A Logarithm and the Chain Rule

## Problem Statement

For
$$f(x)=\ln(x^2+1)$$
compute the derivative. Then determine the sign of $f'(x)$ for $x<0$, $x=0$, and $x>0$, and describe qualitatively how the function behaves around zero.

## Theoretical Background and Concepts

1. **Derivative of the Natural Logarithm**:
   For $u > 0$, the derivative of the natural logarithm $\ln u$ with respect to $u$ is:
   $$\frac{d}{du}(\ln u) = \frac{1}{u}$$

2. **Logarithmic Differentiation with the Chain Rule**:
   When the argument of the natural logarithm is a positive differentiable function $u = h(x) > 0$, the **Chain Rule** gives:
   $$\frac{d}{dx}\big[\ln(h(x))\big] = \frac{1}{h(x)} \cdot h'(x) = \frac{h'(x)}{h(x)}$$
   Notice the clean structure: the derivative of $\ln(h(x))$ is the **derivative of the inside divided by the original inside**.

3. **Monotonicity and the Sign of the Derivative**:
   - On any interval where $f'(x) > 0$, the function $f(x)$ is **strictly increasing**.
   - On any interval where $f'(x) < 0$, the function $f(x)$ is **strictly decreasing**.
   - If $f'(x)$ changes sign from negative (for $x < x_0$) to zero (at $x = x_0$) to positive (for $x > x_0$), then $f(x)$ has a **local (and here global) minimum** at $x = x_0$.

## Detailed Step-by-Step Solution

### Step 1: Check the domain and compute the derivative $f'(x)$

First, note that for every real number $x \in \mathbb{R}$, $x^2 \ge 0$, so $x^2 + 1 \ge 1 > 0$. Because the argument of the natural logarithm is strictly positive for all $x$, the domain of $f(x) = \ln(x^2 + 1)$ is all real numbers, $D_f = \mathbb{R}$.

The function $f(x) = \ln(x^2 + 1)$ is a composition $g(h(x))$ where:
- **Outer function:** $g(u) = \ln u$, whose derivative is $g'(u) = \frac{1}{u}$.
- **Inner function:** $u = h(x) = x^2 + 1$, whose derivative (by the **Power Rule** and **Constant Rule**) is $h'(x) = 2x + 0 = 2x$.

Applying the **Chain Rule**, $f'(x) = g'(h(x)) \cdot h'(x)$:
$$f'(x) = \frac{1}{x^2 + 1} \cdot \frac{d}{dx}(x^2 + 1) = \frac{1}{x^2 + 1} \cdot (2x) = \frac{2x}{x^2 + 1}$$

---

### Step 2: Determine the sign of $f'(x)$ for $x < 0$, $x = 0$, and $x > 0$

Let us analyze the sign of the numerator and denominator of
$$f'(x) = \frac{2x}{x^2 + 1}$$
Since $x^2 \ge 0$ for all $x \in \mathbb{R}$, the denominator $x^2 + 1 \ge 1 > 0$ is **always strictly positive**. Therefore, the sign of $f'(x)$ is determined entirely by the sign of the numerator $2x$:

1. **For $x < 0$:**
   The numerator $2x < 0$ and the denominator $x^2 + 1 > 0$, so:
   $$f'(x) < 0 \quad (\text{negative})$$

2. **For $x = 0$:**
   The numerator is $2(0) = 0$ and the denominator is $0^2 + 1 = 1$, so:
   $$f'(0) = \frac{0}{1} = 0 \quad (\text{zero})$$

3. **For $x > 0$:**
   The numerator $2x > 0$ and the denominator $x^2 + 1 > 0$, so:
   $$f'(x) > 0 \quad (\text{positive})$$

We can summarize this in a sign table:

| Interval / Point | $x < 0$ | $x = 0$ | $x > 0$ |
| :--- | :---: | :---: | :---: |
| Sign of $2x$ | $-$ | $0$ | $+$ |
| Sign of $x^2 + 1$ | $+$ | $+$ | $+$ |
| **Sign of $f'(x)$** | **$-$** | **$0$** | **$+$** |
| **Behavior of $f(x)$** | Strictly decreasing $\searrow$ | Horizontal tangent (Minimum $f(0)=0$) | Strictly increasing $\nearrow$ |

---

### Step 3: Describe qualitatively how the function behaves around zero

Around $x = 0$, the function $f(x) = \ln(x^2 + 1)$ exhibits a smooth, symmetric valley:
1. **Approaching zero from the left ($x < 0$):** Because $f'(x) < 0$, the function is **decreasing** as $x$ increases toward $0$. As $x$ gets closer to $0$, the magnitude of the slope $|f'(x)|$ gets smaller, so the graph becomes progressively flatter.
2. **At $x = 0$:** The function reaches its **minimum value** $f(0) = \ln(0^2 + 1) = \ln(1) = 0$. At the origin $(0, 0)$, the tangent line is **horizontal** ($f'(0) = 0$).
3. **Moving away from zero to the right ($x > 0$):** Because $f'(x) > 0$, the function turns around and becomes **strictly increasing**.
4. **Symmetry:** Because $f(-x) = \ln((-x)^2 + 1) = \ln(x^2 + 1) = f(x)$, the graph is **even** (symmetric with respect to the $y$-axis), shaped very much like the parabola $y = x^2$ near the origin.

## Verification and Consistency Checks

1. **Taylor Expansion Check near $x = 0$:**
   Using the standard expansion $\ln(1 + u) = u - \frac{u^2}{2} + \frac{u^3}{3} - \dots$ for $|u| < 1$ with $u = x^2$:
   $$f(x) = \ln(1 + x^2) = x^2 - \frac{x^4}{2} + \frac{x^6}{3} - \dots$$
   Differentiating term by term gives:
   $$f'(x) = 2x - 2x^3 + 2x^5 - \dots = 2x(1 - x^2 + x^4 - \dots) = \frac{2x}{1 + x^2}$$
   This confirms both our exact derivative formula and the parabolic behavior $f(x) \approx x^2$ around $x = 0$.

2. **Evaluation at Test Points $x = -1$ and $x = 1$:**
   - $f'(-1) = \frac{2(-1)}{(-1)^2 + 1} = \frac{-2}{2} = -1 < 0$ (decreasing at rate $-1$).
   - $f'(1) = \frac{2(1)}{1^2 + 1} = \frac{2}{2} = +1 > 0$ (increasing at rate $+1$).
   Notice that $f'(-x) = -f'(x)$ is odd, which is consistent with $f(x)$ being even.
