# Problem 7: A Trigonometric Composition

## Problem Statement

For
$$f(x)=\sin(x^2+1)$$
compute the derivative. Explicitly identify the outer function, the inner function, and the derivative of the inner function. Finally, determine the sign of $f'(0)$.

## Theoretical Background and Concepts

The function $f(x) = \sin(x^2 + 1)$ is **not** a product of $\sin$ and $(x^2 + 1)$; rather, the polynomial $x^2 + 1$ is the **input (argument)** inside the sine function. In other words, $f(x) = g(h(x))$ is a **composite function**.

To differentiate a composition $f(x) = g(h(x))$, we use the **Chain Rule**:
$$f'(x) = g'(h(x)) \cdot h'(x)$$

Along with the Chain Rule, we need:
- **Derivative of the Sine Function**: $\frac{d}{du}(\sin u) = \cos u$.
- **Power and Constant Rules**: $\frac{d}{dx}(x^2 + 1) = 2x + 0 = 2x$.

## Detailed Step-by-Step Solution

### Step 1: Explicitly identify the inner function, the outer function, and the derivative of the inner function

When evaluating $f(x) = \sin(x^2 + 1)$ at a number $x$, we perform two operations in sequence:
1. **Inner function:** First, we compute the quantity inside the parentheses:
   $$u = h(x) = x^2 + 1$$
2. **Outer function:** Second, we take the sine of that intermediate result $u$:
   $$y = g(u) = \sin u$$
3. **Derivative of the inner function:** Differentiating $h(x) = x^2 + 1$ with respect to $x$ using the **Sum Rule**, **Power Rule** ($\frac{d}{dx}(x^2) = 2x$), and **Constant Rule** ($\frac{d}{dx}(1) = 0$) gives:
   $$h'(x) = \frac{d}{dx}(x^2 + 1) = 2x + 0 = 2x$$

---

### Step 2: Differentiate the outer function and apply the Chain Rule

Next, we differentiate the outer function $g(u) = \sin u$ with respect to its argument $u$:
$$g'(u) = \frac{d}{du}(\sin u) = \cos u$$

Evaluating $g'(u)$ at the unchanged inner function $u = h(x) = x^2 + 1$ yields:
$$g'(h(x)) = \cos(x^2 + 1)$$

Now we apply the **Chain Rule**, $f'(x) = g'(h(x)) \cdot h'(x)$, by multiplying the derivative of the outer function (evaluated at the inner function) by the derivative of the inner function:
$$f'(x) = \cos(x^2 + 1) \cdot (2x) = 2x\cos(x^2 + 1)$$

---

### Step 3: Determine the sign of $f'(0)$

Substituting $x = 0$ into $f'(x) = 2x\cos(x^2 + 1)$:
$$f'(0) = 2(0)\cos(0^2 + 1) = 0 \cdot \cos(1) = 0$$

**Sign of $f'(0)$:**
- Because $f'(0) = 0$, the value $f'(0)$ is **zero (neither positive nor negative)**.
- **Why does $f'(0)$ equal zero even though $\cos(1) > 0$?** The outer derivative at $x = 0$ is $\cos(1) \approx 0.5403 > 0$, which is non-zero, **but** the inner function $h(x) = x^2 + 1$ is stationary at $x = 0$ ($h'(0) = 2(0) = 0$). Because the inner input $u = x^2 + 1$ has zero instantaneous rate of change at $x = 0$, the composite output $\sin(x^2 + 1)$ also has zero instantaneous rate of change at $x = 0$ (a horizontal tangent line).

## Verification and Consistency Checks

1. **Symmetry Check:**
   Notice that $f(-x) = \sin((-x)^2 + 1) = \sin(x^2 + 1) = f(x)$, so $f(x)$ is an **even** function symmetric about the $y$-axis. Any differentiable even function has a horizontal tangent at $x = 0$, confirming that $f'(0) = 0$.
   Moreover, near $x = 0$:
   - For small $x < 0$, $2x < 0$ and $\cos(x^2 + 1) \approx \cos(1) > 0$, so $f'(x) < 0$ (decreasing).
   - For small $x > 0$, $2x > 0$ and $\cos(x^2 + 1) \approx \cos(1) > 0$, so $f'(x) > 0$ (increasing).
   Thus $f(x)$ has a local minimum at $x = 0$.

2. **Numerical Difference Quotient at $x = 1$:**
   At $x = 1$, our formula gives:
   $$f'(1) = 2(1)\cos(1^2 + 1) = 2\cos(2) \approx 2(-0.4161468) \approx -0.8322937$$
   Using a symmetric difference quotient with $h = 0.001$ (in radians):
   $$f(1.001) = \sin((1.001)^2 + 1) = \sin(2.002001) \approx 0.9084640$$
   $$f(0.999) = \sin((0.999)^2 + 1) = \sin(1.998001) \approx 0.9101286$$
   $$\frac{f(1.001) - f(0.999)}{0.002} \approx \frac{-0.0016646}{0.002} = -0.8323$$
   This agrees closely with $2\cos(2) \approx -0.83229$.
