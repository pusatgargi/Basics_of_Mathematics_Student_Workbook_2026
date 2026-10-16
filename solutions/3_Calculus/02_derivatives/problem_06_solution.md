# Problem 6: Product Rule and Trigonometry

## Problem Statement

For
$$f(x)=x\sin x+\cos x$$
compute the derivative and simplify the result. Then compute $f'(0)$ and interpret the direction of the tangent line at that point.

## Theoretical Background and Concepts

To differentiate an expression combining algebraic and trigonometric functions through addition and multiplication, we use:
1. **Sum Rule**: The derivative of a sum is the sum of the derivatives:
   $$\frac{d}{dx}\big[A(x) + B(x)\big] = A'(x) + B'(x)$$
2. **Product Rule**: For a product of two differentiable functions $u(x)$ and $v(x)$,
   $$\frac{d}{dx}\big[u(x)v(x)\big] = u'(x)v(x) + u(x)v'(x)$$
3. **Power Rule**: For $u(x) = x = x^1$, $\frac{d}{dx}(x) = 1$.
4. **Derivatives of Basic Trigonometric Functions** (with $x$ measured in radians):
   $$\frac{d}{dx}(\sin x) = \cos x, \qquad \frac{d}{dx}(\cos x) = -\sin x$$

**Geometric Meaning of the Derivative**:
The value $f'(x_0)$ is the slope of the tangent line to the graph of $f$ at $(x_0, f(x_0))$. In particular, when $f'(x_0) = 0$, the tangent line has zero slope, meaning it is **horizontal** (parallel to the $x$-axis).

## Detailed Step-by-Step Solution

### Step 1: Apply the Sum Rule to the whole expression

We are given:
$$f(x) = x\sin x + \cos x$$

Because $f(x)$ is the sum of two terms, $x\sin x$ and $\cos x$, we first apply the **Sum Rule**:
$$f'(x) = \frac{d}{dx}(x\sin x) + \frac{d}{dx}(\cos x)$$

---

### Step 2: Differentiate the first term using the Product Rule

The first term, $x\sin x$, is a product of $u(x) = x$ and $v(x) = \sin x$. Why must we use the **Product Rule** here? Because both factors depend on the variable $x$. Applying $\frac{d}{dx}[u(x)v(x)] = u'(x)v(x) + u(x)v'(x)$:
$$\frac{d}{dx}(x\sin x) = \left[\frac{d}{dx}(x)\right]\sin x + x\left[\frac{d}{dx}(\sin x)\right]$$

Using $\frac{d}{dx}(x) = 1$ (**Power Rule**) and $\frac{d}{dx}(\sin x) = \cos x$ (**Sine Derivative Rule**):
$$\frac{d}{dx}(x\sin x) = 1 \cdot \sin x + x\cos x = \sin x + x\cos x$$

---

### Step 3: Differentiate the second term and simplify

For the second term, $\cos x$, we apply the **Cosine Derivative Rule**:
$$\frac{d}{dx}(\cos x) = -\sin x$$

Now we combine both parts into $f'(x)$ and simplify by cancelling opposite terms ($\sin x$ and $-\sin x$):
$$f'(x) = (\sin x + x\cos x) + (-\sin x) = \sin x + x\cos x - \sin x = x\cos x$$

Thus, the simplified derivative is:
$$f'(x) = x\cos x$$

---

### Step 4: Compute $f'(0)$ and interpret the direction of the tangent line

Substituting $x = 0$ into our simplified derivative $f'(x) = x\cos x$:
$$f'(0) = 0 \cdot \cos(0) = 0 \cdot 1 = 0$$

**Geometric interpretation of the direction of the tangent line at $x = 0$:**
- At $x = 0$, the point on the graph is $(0, f(0)) = (0, 0\sin 0 + \cos 0) = (0, 1)$.
- Since the derivative at $x = 0$ is $f'(0) = 0$, the slope of the tangent line at $(0, 1)$ is **$0$**.
- A line with slope $0$ is **horizontal** (parallel to the $x$-axis), with equation $y = 1$. Geometrically, the graph of $f(x)$ flattens out at $(0, 1)$ (in fact, since $f(x)$ is an even function with $f(x) \approx 1 + \frac{1}{2}x^2$ near $0$, it has a local minimum at $(0, 1)$).

## Verification and Consistency Checks

1. **Taylor / Small-Angle Approximation Check near $x = 0$:**
   Using the standard Maclaurin expansions $\sin x = x - \frac{x^3}{6} + \dots$ and $\cos x = 1 - \frac{x^2}{2} + \dots$:
   $$f(x) = x\left(x - \frac{x^3}{6} + \dots\right) + \left(1 - \frac{x^2}{2} + \dots\right) = 1 + \left(x^2 - \frac{x^2}{2}\right) + \dots = 1 + \frac{1}{2}x^2 + O(x^4)$$
   Differentiating this power series gives:
   $$f'(x) = 0 + x + O(x^3) \approx x$$
   Compare this with our exact formula $f'(x) = x\cos x = x\left(1 - \frac{x^2}{2} + \dots\right) = x + O(x^3)$: they match completely, and at $x = 0$, $f'(0) = 0$.

2. **Symmetry (Parity) Check:**
   Notice that $f(-x) = (-x)\sin(-x) + \cos(-x) = (-x)(-\sin x) + \cos x = x\sin x + \cos x = f(x)$, so $f$ is an **even** function. The derivative of any differentiable even function must be an **odd** function and must vanish at $x = 0$. Indeed, $f'(-x) = (-x)\cos(-x) = -x\cos x = -f'(x)$ is odd, and $f'(0) = 0$.
