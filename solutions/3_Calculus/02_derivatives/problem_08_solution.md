# Problem 8: Two Exponential Functions

## Problem Statement

For
$$f(x)=e^{2x-3}+5^x$$
compute the derivative. Explain why the factor $2$ appears in the first term and why $\ln5$ appears in the second.

## Theoretical Background and Concepts

This problem contrasts two different mechanisms that produce constant multiplying factors when differentiating exponential functions:

1. **The Natural Exponential Function and the Chain Rule**:
   The natural exponential function $g(u) = e^u$ has the special property that its derivative with respect to its exponent $u$ is itself:
   $$\frac{d}{du}\left(e^u\right) = e^u$$
   When the exponent is a composite function $u = h(x)$ rather than simply $x$, the **Chain Rule** requires us to multiply by the derivative of the inner function (the exponent):
   $$\frac{d}{dx}\left(e^{h(x)}\right) = e^{h(x)} \cdot h'(x)$$

2. **General Base Exponential Functions ($a^x$ with $a > 0, a \neq 1$)**:
   When the base of an exponential function is a positive constant $a \neq e$, we can rewrite $a^x$ using the identity $a = e^{\ln a}$:
   $$a^x = \left(e^{\ln a}\right)^x = e^{(\ln a)x}$$
   Applying the Chain Rule to $e^{(\ln a)x}$ brings down the constant coefficient $\ln a$ from the exponent:
   $$\frac{d}{dx}\left(a^x\right) = a^x \ln a$$

3. **Sum Rule**: $\frac{d}{dx}[A(x) + B(x)] = A'(x) + B'(x)$.

## Detailed Step-by-Step Solution

### Step 1: Apply the Sum Rule

We are given:
$$f(x) = e^{2x-3} + 5^x$$

By the **Sum Rule**, we differentiate each exponential term separately and add the results:
$$f'(x) = \frac{d}{dx}\left(e^{2x-3}\right) + \frac{d}{dx}\left(5^x\right)$$

---

### Step 2: Differentiate the first term $e^{2x-3}$

The first term $e^{2x-3}$ is a composition $g(h(x))$ where:
- **Outer function:** $g(u) = e^u$, with derivative $g'(u) = e^u$.
- **Inner function (exponent):** $u = h(x) = 2x - 3$, with derivative $h'(x) = \frac{d}{dx}(2x - 3) = 2 - 0 = 2$.

Applying the **Chain Rule**, $\frac{d}{dx}[g(h(x))] = g'(h(x)) \cdot h'(x)$:
$$\frac{d}{dx}\left(e^{2x-3}\right) = e^{2x-3} \cdot \frac{d}{dx}(2x - 3) = e^{2x-3} \cdot 2 = 2e^{2x-3}$$

---

### Step 3: Differentiate the second term $5^x$

The second term $5^x$ is an exponential function with base $a = 5$ and exponent $x$. Applying the **General Exponential Derivative Rule** $\frac{d}{dx}(a^x) = a^x \ln a$:
$$\frac{d}{dx}\left(5^x\right) = 5^x \ln 5$$

Combining both derivatives gives the final formula:
$$f'(x) = 2e^{2x-3} + 5^x \ln 5$$

---

### Step 4: Explain why $2$ appears in the first term and why $\ln 5$ appears in the second

Although both terms in $f'(x)$ acquire an extra constant factor in front of the exponential, the two factors arise for conceptually distinct reasons:

1. **Why the factor $2$ appears in $2e^{2x-3}$:**
   Here, the base is the natural base $e$ (so $\ln e = 1$, producing no logarithmic correction factor), **but** the exponent is a linear function $u = 2x - 3$ instead of $x$. Because $u = 2x - 3$ changes **twice as fast** as $x$ (its derivative is $\frac{du}{dx} = 2$), the **Chain Rule** multiplies the outer derivative $e^{2x-3}$ by the inner derivative $2$. Thus, the factor $2$ comes from the **rate of change of the exponent** $2x - 3$.

2. **Why the factor $\ln 5$ appears in $5^x \ln 5$:**
   Here, the exponent is simply $x$ (whose derivative is $1$), **but** the base is $5$ rather than $e$. Only the natural exponential $e^x$ has slope $1$ at $x = 0$ and equals its own derivative. Since $5 = e^{\ln 5}$, we can rewrite $5^x$ in the natural base as:
   $$5^x = \left(e^{\ln 5}\right)^x = e^{(\ln 5)x}$$
   Written in this form, changing $x$ by $1$ unit scales the natural exponent by $\ln 5 \approx 1.6094$ units. Differentiating $e^{(\ln 5)x}$ via the Chain Rule brings down $\frac{d}{dx}[(\ln 5)x] = \ln 5$, giving $e^{(\ln 5)x} \ln 5 = 5^x \ln 5$. Thus, the factor $\ln 5$ is the **base-conversion scaling factor** that accounts for using base $5$ instead of the natural base $e$.

## Verification and Consistency Checks

1. **Alternative Method (Factoring Laws of Exponents Before Differentiating):**
   Notice that we can rewrite the first term as $e^{2x-3} = e^{-3} \cdot \left(e^2\right)^x$ and use the Constant Multiple Rule:
   $$\frac{d}{dx}\left(e^{2x-3}\right) = e^{-3} \frac{d}{dx}\left(e^{2x}\right) = e^{-3} \left(2e^{2x}\right) = 2e^{2x-3}$$
   Or, even viewing $e^{2x} = (e^2)^x$ as a base-$a$ exponential with base $a = e^2$, the rule $\frac{d}{dx}(a^x) = a^x \ln a$ gives $(e^2)^x \ln(e^2) = e^{2x} \cdot 2$, demonstrating that the two mechanisms are completely consistent with one another!

2. **Numerical Difference Quotient Check at $x = 1.5$:**
   At $x = 1.5$:
   $$f'(1.5) = 2e^{2(1.5)-3} + 5^{1.5}\ln 5 = 2e^0 + 5\sqrt{5}\ln 5 \approx 2 + (11.1803399)(1.6094379) \approx 19.99406$$
   Using $h = 0.0001$:
   $$f(1.5) = e^0 + 5^{1.5} \approx 1 + 11.1803399 = 12.1803399$$
   $$f(1.5001) = e^{0.0002} + 5^{1.5001} \approx 1.00020002 + 11.1821393 = 12.1823393$$
   $$\frac{f(1.5001) - f(1.5)}{0.0001} \approx \frac{0.0019994}{0.0001} = 19.994$$
   This matches $f'(1.5) \approx 19.994$.
