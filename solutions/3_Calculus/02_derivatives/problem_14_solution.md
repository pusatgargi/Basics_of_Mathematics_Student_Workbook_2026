# Problem 14: Continuity and Differentiability of a Piecewise Function

## Problem Statement

Investigate the behavior at $x=0$ of
$$f(x)=\begin{cases}x^2,&x\ge0,\\ax,&x<0.\end{cases}$$
For which values of $a$ is the function continuous? For which values do the one-sided derivatives exist and agree? For which value of $a$ is the function differentiable? Explain why continuity alone is not sufficient.

## Theoretical Background and Concepts

When a function is defined piecewise by different formulas on either side of a boundary point $x_0$, we must carefully distinguish between **continuity** (no break or jump in the graph) and **differentiability** (no sharp corner, cusp, or vertical tangent in the graph):

1. **Continuity at $x = x_0$**:
   A function $f$ is continuous at $x = x_0$ if and only if its left-hand limit, right-hand limit, and function value at $x_0$ all exist and are equal:
   $$\lim_{x \to x_0^-} f(x) = \lim_{x \to x_0^+} f(x) = f(x_0)$$

2. **One-Sided Derivatives at $x = x_0$**:
   - The **right-hand derivative** at $x_0$ is:
     $$f'_+(x_0) = \lim_{h \to 0^+} \frac{f(x_0 + h) - f(x_0)}{h}$$
   - The **left-hand derivative** at $x_0$ is:
     $$f'_-(x_0) = \lim_{h \to 0^-} \frac{f(x_0 + h) - f(x_0)}{h}$$

3. **Differentiability at $x = x_0$**:
   A function $f$ is differentiable at $x = x_0$ if and only if the two-sided limit $\lim_{h \to 0} \frac{f(x_0 + h) - f(x_0)}{h}$ exists as a finite real number—which means **both one-sided derivatives $f'_-(x_0)$ and $f'_+(x_0)$ must exist as finite numbers and be equal**:
   $$f'_-(x_0) = f'_+(x_0)$$
   *(Note: If $f$ is differentiable at $x_0$, then $f$ is automatically continuous at $x_0$, but the converse is false!)*

## Detailed Step-by-Step Solution

### Part 1: For which values of $a$ is the function continuous at $x = 0$?

We check the value of the function and both one-sided limits at $x = 0$:
1. **Function value at $x = 0$:** Using the branch for $x \ge 0$,
   $$f(0) = 0^2 = 0$$
2. **Right-hand limit ($x \to 0^+$):** For $x > 0$, $f(x) = x^2$, so:
   $$\lim_{x \to 0^+} f(x) = \lim_{x \to 0^+} x^2 = 0$$
3. **Left-hand limit ($x \to 0^-$):** For $x < 0$, $f(x) = ax$, so:
   $$\lim_{x \to 0^-} f(x) = \lim_{x \to 0^-} (ax) = a \cdot 0 = 0$$

Because $\lim_{x \to 0^-} f(x) = \lim_{x \to 0^+} f(x) = f(0) = 0$ holds regardless of the value of $a$, the function $f$ is **continuous at $x = 0$ (and on all of $\mathbb{R}$) for every real value $a \in \mathbb{R}$**.

---

### Part 2: For which values of $a$ do the one-sided derivatives exist and agree at $x = 0$?

We compute the right-hand and left-hand derivatives at $x = 0$ directly from their limit definitions, using $f(0) = 0$:

1. **Right-hand derivative $f'_+(0)$:**
   For $h > 0$, we have $0 + h = h > 0$, so we use the branch $f(h) = h^2$:
   $$f'_+(0) = \lim_{h \to 0^+} \frac{f(0 + h) - f(0)}{h} = \lim_{h \to 0^+} \frac{h^2 - 0}{h} = \lim_{h \to 0^+} h = 0$$
   Thus, $f'_+(0) = 0$ exists for all $a \in \mathbb{R}$.

2. **Left-hand derivative $f'_-(0)$:**
   For $h < 0$, we have $0 + h = h < 0$, so we use the branch $f(h) = ah$:
   $$f'_-(0) = \lim_{h \to 0^-} \frac{f(0 + h) - f(0)}{h} = \lim_{h \to 0^-} \frac{ah - 0}{h} = \lim_{h \to 0^-} a = a$$
   Thus, $f'_-(0) = a$ exists for all $a \in \mathbb{R}$.

3. **Agreement of the one-sided derivatives:**
   Both one-sided derivatives exist for **all $a \in \mathbb{R}$**, and they **agree** ($f'_-(0) = f'_+(0)$) if and only if:
   $$a = 0$$

---

### Part 3: For which value of $a$ is the function differentiable at $x = 0$?

By definition, $f$ is differentiable at $x = 0$ if and only if the two-sided limit $\lim_{h \to 0} \frac{f(h) - f(0)}{h}$ exists, which happens if and only if $f'_-(0) = f'_+(0)$. From Part 2, this occurs for the **single value**:
$$a = 0$$
For $a = 0$, the function is differentiable at $x = 0$ with derivative $f'(0) = 0$.

---

### Part 4: Explain why continuity alone is not sufficient for differentiability

This function provides a crystal-clear counterexample showing why **continuity does not imply differentiability**:
- For **every** real number $a \in \mathbb{R}$, the two pieces $y = ax$ (for $x < 0$) and $y = x^2$ (for $x \ge 0$) meet at the origin $(0, 0)$ without any gap or jump, so the graph is **continuous for all $a \in \mathbb{R}$**.
- However, continuity only requires that the **positions** ($y$-values) of the two branches match at $x = 0$. Differentiability is a stricter condition: it requires that the **slopes (directions)** of the two branches also match smoothly at $x = 0$ so that there is a single, unique tangent line at the origin.
- When $a \neq 0$, the left branch is a straight line arriving at the origin with slope $a \neq 0$, while the right branch is a parabola leaving the origin horizontally with slope $0$. Because the slope jumps abruptly from $a$ to $0$ at $x = 0$, the graph has a **sharp corner (kink)** at $(0, 0)$, so no unique tangent line exists there. Only when $a = 0$ do both branches meet with the same horizontal slope $0$.

## Verification and Consistency Checks

1. **Concrete Comparison of $a = 1$ vs. $a = 0$:**
   - **Case $a = 1$:** $f(x) = x$ for $x < 0$ and $f(x) = x^2$ for $x \ge 0$. At $x = 0$, both pieces equal $0$ (continuous), but the slope from the left is $1$ ($45^\circ$ line) and the slope from the right is $0$ (horizontal), forming a visible $135^\circ$ corner at $(0,0)$.
   - **Case $a = 0$:** $f(x) = 0$ for $x < 0$ and $f(x) = x^2$ for $x \ge 0$. Here, the negative $x$-axis ($y = 0$, slope $0$) transitions smoothly into the parabola $y = x^2$ (whose tangent at the vertex $(0,0)$ is also $y = 0$, slope $0$).

2. **Derivative Formula for $a = 0$:**
   When $a = 0$, the derivative for all $x \in \mathbb{R}$ is:
   $$f'(x) = \begin{cases} 2x, & x \ge 0, \\ 0, & x < 0, \end{cases}$$
   which is itself continuous at $x = 0$ since $2(0) = 0$ (so for $a = 0$, $f$ is in fact continuously differentiable, $C^1(\mathbb{R})$).
