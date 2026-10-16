# Problem 10: The Tangent Line as an Application of the Derivative

## Problem Statement

For
$$f(x)=x^2-3x+1$$
find the equation of the tangent line at the point with $x=2$. Give the point of tangency, the value $f'(2)$, the equation of the line, and verify that the point lies on the obtained tangent line.

## Theoretical Background and Concepts

The **tangent line** to the graph of a differentiable function $y = f(x)$ at the point where $x = x_0$ is the straight line that passes through the point of tangency $(x_0, f(x_0))$ and has the exact same instantaneous slope as the curve at that point.

1. **Slope of the Tangent Line**:
   The slope $m$ of the tangent line at $x = x_0$ is given by the derivative evaluated at $x_0$:
   $$m = f'(x_0)$$

2. **Equation of the Tangent Line**:
   Using the point-slope form of a line passing through $(x_0, y_0) = (x_0, f(x_0))$ with slope $m = f'(x_0)$, the tangent line equation is:
   $$y - f(x_0) = f'(x_0)(x - x_0) \quad \Longleftrightarrow \quad y = f(x_0) + f'(x_0)(x - x_0)$$

3. **Differentiation Rules Used**:
   To differentiate $f(x) = x^2 - 3x + 1$, we use the **Sum/Difference Rule**, **Constant Multiple Rule**, **Power Rule** ($\frac{d}{dx}(x^n) = nx^{n-1}$), and **Constant Rule** ($\frac{d}{dx}(c) = 0$).

## Detailed Step-by-Step Solution

### Step 1: Find the point of tangency $(2, f(2))$

To find the $y$-coordinate of the point on the graph at $x_0 = 2$, we substitute $x = 2$ into the original function $f(x) = x^2 - 3x + 1$:
$$f(2) = (2)^2 - 3(2) + 1 = 4 - 6 + 1 = -1$$

Therefore, the **point of tangency** is:
$$(x_0, y_0) = (2, -1)$$

---

### Step 2: Compute the derivative $f'(x)$ and its value $f'(2)$

We differentiate $f(x) = x^2 - 3x + 1$ term by term using the **Difference/Sum Rule**, **Power Rule**, **Constant Multiple Rule**, and **Constant Rule**:
$$f'(x) = \frac{d}{dx}\left(x^2\right) - 3\frac{d}{dx}(x) + \frac{d}{dx}(1) = 2x - 3(1) + 0 = 2x - 3$$

Now we evaluate the derivative at $x = 2$ to find the slope of the tangent line:
$$f'(2) = 2(2) - 3 = 4 - 3 = 1$$

Thus, the slope of the tangent line at $x = 2$ is **$m = f'(2) = 1$**.

---

### Step 3: Write the equation of the tangent line

Substituting the point of tangency $(x_0, f(x_0)) = (2, -1)$ and the slope $f'(2) = 1$ into the tangent line formula $y = f(x_0) + f'(x_0)(x - x_0)$:
$$y = -1 + 1 \cdot (x - 2)$$

Simplifying into slope-intercept form ($y = mx + b$):
$$y = -1 + x - 2 \implies y = x - 3$$

---

### Step 4: Verify that the point of tangency lies on the obtained tangent line

We substitute the coordinates of the point of tangency $(x, y) = (2, -1)$ into the tangent line equation $y = x - 3$:
- **Left-hand side:** $y = -1$
- **Right-hand side:** $x - 3 = 2 - 3 = -1$

Since $-1 = -1$, the equation holds true, confirming that the point of tangency $(2, -1)$ lies on the tangent line $y = x - 3$.

## Verification and Consistency Checks

1. **Double-Root (Algebraic Tangency) Verification for a Parabola:**
   A non-vertical line $y = mx + b$ is tangent to a parabola $y = f(x)$ at $x = 2$ if and only if the difference $f(x) - (mx + b)$ has a **double root** at $x = 2$, i.e., factors as $(x - 2)^2$. Let us check the difference between $f(x) = x^2 - 3x + 1$ and our tangent line $y = x - 3$:
   $$f(x) - (x - 3) = (x^2 - 3x + 1) - (x - 3) = x^2 - 4x + 4 = (x - 2)^2$$
   Because $(x - 2)^2 = 0$ has a double root at $x = 2$ (and $(x - 2)^2 \ge 0$ everywhere), the line $y = x - 3$ touches the parabola at $(2, -1)$ without crossing it and lies entirely on or below the parabola. This is an exact algebraic proof that $y = x - 3$ is the tangent line!

2. **Summary of Required Results:**
   - **Point of tangency:** $(2, -1)$
   - **Value of the derivative:** $f'(2) = 1$
   - **Equation of the tangent line:** $y = x - 3$
   - **Point check:** $y(2) = 2 - 3 = -1 = f(2)$ $\checkmark$
