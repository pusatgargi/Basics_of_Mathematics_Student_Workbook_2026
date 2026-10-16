# Problem 11: Derivative from the Definition

## Problem Statement

Using only
$$f'(x)=\lim_{h\to0}\frac{f(x+h)-f(x)}h,$$
find the derivative of $f(x)=x^2$. Compare the result with the power rule and indicate where the limit is used in the calculation.

## Theoretical Background and Concepts

All differentiation rules—including the power rule, product rule, quotient rule, and chain rule—are not arbitrary axioms; they are theorems derived from the **limit definition of the derivative**:
$$f'(x) = \lim_{h \to 0} \frac{f(x + h) - f(x)}{h}$$

1. **The Difference Quotient**:
   For a non-zero increment $h \neq 0$, the ratio
   $$\frac{f(x + h) - f(x)}{h}$$
   is the **difference quotient** of $f$ on the interval between $x$ and $x + h$. Geometrically, it represents the **slope of the secant line** passing through the two points $(x, f(x))$ and $(x + h, f(x + h))$ on the graph of $f$.

2. **Passing to the Limit ($h \to 0$)**:
   We cannot simply plug $h = 0$ directly into the difference quotient $\frac{f(x+h)-f(x)}{h}$ because that produces the indeterminate form $\frac{0}{0}$. Instead, we first simplify the numerator algebraically and cancel the common factor $h$ (which is valid because the limit as $h \to 0$ only considers values $h \neq 0$). Once the division by $h$ is removed, we evaluate the limit as $h \to 0$ to obtain the **instantaneous rate of change** (the slope of the tangent line).

3. **Power Rule for Comparison**:
   For $f(x) = x^n$, the Power Rule states that $f'(x) = nx^{n-1}$.

## Detailed Step-by-Step Solution

### Step 1: Set up the difference quotient for $f(x) = x^2$

We start from the limit definition of the derivative:
$$f'(x) = \lim_{h \to 0} \frac{f(x + h) - f(x)}{h}$$

For $f(x) = x^2$, we evaluate the function at the shifted input $x + h$:
$$f(x + h) = (x + h)^2$$

Substituting $f(x + h) = (x + h)^2$ and $f(x) = x^2$ into the definition gives:
$$f'(x) = \lim_{h \to 0} \frac{(x + h)^2 - x^2}{h}$$

---

### Step 2: Expand and simplify the difference quotient (for $h \neq 0$)

Using the binomial square formula $(x + h)^2 = x^2 + 2xh + h^2$, we expand the numerator:
$$f'(x) = \lim_{h \to 0} \frac{(x^2 + 2xh + h^2) - x^2}{h}$$

The $x^2$ and $-x^2$ terms cancel out in the numerator:
$$f'(x) = \lim_{h \to 0} \frac{2xh + h^2}{h}$$

Next, we factor $h$ out of the numerator:
$$f'(x) = \lim_{h \to 0} \frac{h(2x + h)}{h}$$

Because the limit $\lim_{h \to 0}$ examines values of $h$ approaching $0$ with **$h \neq 0$**, we can divide both the numerator and the denominator by $h$:
$$f'(x) = \lim_{h \to 0} (2x + h)$$

---

### Step 3: Evaluate the limit as $h \to 0$

Now that the indeterminate $\frac{0}{0}$ form has been resolved, the expression $2x + h$ is a continuous linear function of $h$ (treating $x$ as fixed). Taking the limit as $h \to 0$:
$$f'(x) = \lim_{h \to 0} (2x + h) = 2x + 0 = 2x$$

Thus, directly from the definition:
$$f'(x) = 2x$$

---

### Step 4: Compare with the Power Rule and indicate where the limit is used

1. **Comparison with the Power Rule:**
   Applying the **Power Rule**, $\frac{d}{dx}(x^n) = nx^{n-1}$, to $f(x) = x^2$ (where $n = 2$) gives:
   $$f'(x) = 2x^{2-1} = 2x^1 = 2x$$
   The result obtained from the limit definition matches the Power Rule **identically**. In fact, the calculation above *is* the proof of the Power Rule for $n = 2$!

2. **Where is the limit used in the calculation?**
   The limit is used in **two essential ways**:
   - **First (Implicitly during cancellation):** The definition of $\lim_{h \to 0}$ guarantees that $h$ approaches $0$ **without ever equaling $0$** ($h \neq 0$). This is what legally permits us to cancel $\frac{h}{h} = 1$ in the step $\frac{h(2x + h)}{h} = 2x + h$.
   - **Second (Explicitly in the final step):** In the step $\lim_{h \to 0} (2x + h) = 2x$, the limit operator makes the perturbation term $+h$ vanish as $h \to 0$, turning the secant slope $2x + h$ (which still depends on the step size $h$) into the exact tangent slope $2x$.

## Verification and Consistency Checks

1. **Geometric Area Interpretation of $(x + h)^2 - x^2$:**
   Consider a square of side length $x$, whose area is $f(x) = x^2$. Increasing the side length by $h$ produces a larger square of area $(x + h)^2$. The added area $(x + h)^2 - x^2$ consists of:
   - Two thin rectangles of dimensions $x \times h$, contributing area $2xh$, and
   - One tiny corner square of dimensions $h \times h$, contributing area $h^2$.
   Dividing the added area by $h$ gives $2x + h$. As the strip width $h \to 0$, the tiny corner contribution $\frac{h^2}{h} = h$ shrinks to $0$, leaving the instantaneous rate of area growth $2x$.

2. **Numerical Check at $x = 3$:**
   For $x = 3$, the secant slope is $2(3) + h = 6 + h$. For $h = 0.1, 0.01, 0.001$, the difference quotients are $6.1, 6.01, 6.001$, converging to $f'(3) = 6$.
