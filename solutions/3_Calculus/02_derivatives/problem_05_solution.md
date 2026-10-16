# Problem 5: The Chain Rule as Working Through Layers

## Problem Statement

For
$$f(x)=(3x^2-2x+1)^5$$
identify the inner and outer functions, compute their derivatives, and combine the result according to the chain rule. Explain the origin of the additional factor.

## Theoretical Background and Concepts

Many functions are built by **composition**—applying one function to the output of another:
$$f(x) = g(h(x))$$
Here, $u = h(x)$ is the **inner function** (computed first when evaluating $f(x)$), and $y = g(u)$ is the **outer function** (computed second, acting on the intermediate result $u$).

To differentiate a composite function without expanding it, we use the **Chain Rule**:
$$\frac{d}{dx}\big[g(h(x))\big] = g'(h(x)) \cdot h'(x) \quad \text{or in Leibniz notation:} \quad \frac{dy}{dx} = \frac{dy}{du} \cdot \frac{du}{dx}$$

In words: **differentiate the outer function (keeping the inner function unchanged inside it), and then multiply by the derivative of the inner function.**

In this problem we also use:
- **Power Rule**: $\frac{d}{du}(u^5) = 5u^4$ and $\frac{d}{dx}(x^n) = nx^{n-1}$.
- **Sum, Difference, Constant Multiple, and Constant Rules** to differentiate the inner polynomial.

## Detailed Step-by-Step Solution

### Step 1: Identify the inner and outer functions

When we evaluate $f(x) = (3x^2 - 2x + 1)^5$ for a given $x$, we work from the inside out:
1. First, we compute the polynomial inside the parentheses. This is the **inner function**:
   $$u = h(x) = 3x^2 - 2x + 1$$
2. Second, we raise that result $u$ to the $5$th power. This is the **outer function**:
   $$y = g(u) = u^5$$

Checking the composition: $g(h(x)) = (h(x))^5 = (3x^2 - 2x + 1)^5 = f(x)$.

---

### Step 2: Compute the derivatives of the outer and inner functions

1. **Derivative of the outer function $g(u) = u^5$ with respect to $u$:**
   Using the **Power Rule**:
   $$g'(u) = \frac{dg}{du} = 5u^{5-1} = 5u^4$$
   Evaluated at the inner function $u = h(x) = 3x^2 - 2x + 1$, this becomes:
   $$g'(h(x)) = 5(3x^2 - 2x + 1)^4$$

2. **Derivative of the inner function $h(x) = 3x^2 - 2x + 1$ with respect to $x$:**
   Using the **Sum/Difference Rule**, **Constant Multiple Rule**, **Power Rule**, and **Constant Rule**:
   $$h'(x) = \frac{dh}{dx} = 3(2x) - 2(1) + 0 = 6x - 2$$

---

### Step 3: Combine the results using the Chain Rule

Applying the **Chain Rule**, $f'(x) = g'(h(x)) \cdot h'(x)$, we multiply the derivative of the outer layer (evaluated at the inner layer) by the derivative of the inner layer:
$$f'(x) = 5(3x^2 - 2x + 1)^4 \cdot (6x - 2)$$

We can also factor $2$ out of $(6x - 2) = 2(3x - 1)$ if desired:
$$f'(x) = 10(3x - 1)(3x^2 - 2x + 1)^4$$

---

### Step 4: Explain the origin of the additional factor $(6x - 2)$

Why can we not simply write $5(3x^2 - 2x + 1)^4$? Where does the extra factor $h'(x) = 6x - 2$ come from?

1. **Rate-of-change (sensitivity) explanation:**
   The expression $5u^4$ tells us how fast the output $y = u^5$ changes **with respect to the intermediate variable $u$** (i.e., $\frac{\Delta y}{\Delta u} \approx 5u^4$). However, we want to know how fast $y$ changes **with respect to $x$** ($\frac{\Delta y}{\Delta x}$).
   When $x$ changes by a tiny amount $\Delta x$, the intermediate quantity $u = 3x^2 - 2x + 1$ does **not** change by $\Delta x$; instead, it changes by approximately
   $$\Delta u \approx h'(x)\,\Delta x = (6x - 2)\,\Delta x.$$
   Then the outer function $y = u^5$ responds to $\Delta u$ by changing by
   $$\Delta y \approx g'(u)\,\Delta u \approx 5u^4 \cdot (6x - 2)\,\Delta x.$$
   Dividing by $\Delta x$ and taking the limit as $\Delta x \to 0$ gives the product of the two rates:
   $$\frac{dy}{dx} = \lim_{\Delta x \to 0} \frac{\Delta y}{\Delta u} \cdot \frac{\Delta u}{\Delta x} = \frac{dy}{du} \cdot \frac{du}{dx} = 5(3x^2 - 2x + 1)^4 (6x - 2).$$
   Thus, the additional factor $(6x - 2)$ is the **scaling factor (rate of change) of the inner layer** with respect to $x$.

## Verification and Consistency Checks

1. **Evaluation at $x = 0$ and Comparison with Binomial Expansion:**
   - Using our Chain Rule formula at $x = 0$:
     $$f'(0) = 5(0 - 0 + 1)^4 (6(0) - 2) = 5(1)^4(-2) = -10$$
   - Let us check the linear and constant terms of $f(x) = (1 + (3x^2 - 2x))^5$ using the binomial expansion $(1 + w)^5 = 1 + 5w + 10w^2 + \dots$:
     $$f(x) = 1 + 5(3x^2 - 2x) + 10(3x^2 - 2x)^2 + \dots = 1 - 10x + 55x^2 + \dots$$
     Differentiating term by term at $x = 0$ immediately gives $f'(0) = -10$, which matches! Furthermore, had we forgotten the inner derivative factor $(6x - 2)$, we would have obtained $5(1)^4 = +5$, which even has the wrong sign!

2. **Evaluation at $x = 1$ via Finite Differences:**
   At $x = 1$:
   $$f'(1) = 5(3(1)^2 - 2(1) + 1)^4 (6(1) - 2) = 5(2)^4(4) = 5(16)(4) = 320$$
   Checking with $h = 0.0001$:
   $$f(1) = 2^5 = 32, \quad f(1.0001) = \big(3(1.0001)^2 - 2(1.0001) + 1\big)^5 = (2.00040003)^5 \approx 32.032016$$
   $$\frac{f(1.0001) - f(1)}{0.0001} \approx \frac{0.032016}{0.0001} = 320.16 \to 320$$
