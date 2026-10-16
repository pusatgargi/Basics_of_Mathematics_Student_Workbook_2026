# Problem 15: The Difference Quotient as a Check of the Derivative

## Problem Statement

Choose one function from the problem set and a point $x_0$ at which the derivative exists. Compute $f'(x_0)$ exactly, and then calculate
$$\frac{f(x_0+h)-f(x_0)}h$$
for $h=1$, $0.1$, and $0.01$. Compare the values with $f'(x_0)$ and explain why the difference quotient approaching a single number is consistent with the definition of the derivative, while a few computations do not replace a limit argument.

## Theoretical Background and Concepts

1. **The Limit Definition of the Derivative at a Point $x_0$**:
   The derivative of $f$ at $x_0$ is defined as the limit of the **difference quotient** as the increment $h$ approaches $0$:
   $$f'(x_0) = \lim_{h \to 0} \frac{f(x_0 + h) - f(x_0)}{h}$$
   Geometrically:
   - For each fixed $h \neq 0$, the difference quotient $\frac{f(x_0 + h) - f(x_0)}{h}$ is the **slope of the secant line** through $(x_0, f(x_0))$ and $(x_0 + h, f(x_0 + h))$.
   - The derivative $f'(x_0)$ is the **slope of the tangent line** at $(x_0, f(x_0))$, which the secant slopes approach as $h \to 0$.

2. **Numerical Sanity Checks vs. Mathematical Proof**:
   Evaluating the difference quotient for small values such as $h = 1, 0.1, 0.01$ is an excellent **practical check** to catch differentiation errors (if you made a sign error or forgot a Chain Rule factor, the difference quotient for $h = 0.01$ will immediately disagree with your formula). However, testing finitely many values of $h$ is only **empirical observation**, not a rigorous proof of the limit.

## Detailed Step-by-Step Solution

### Step 1: Choose a function from the problem set and compute $f'(x_0)$

Let us choose the quadratic function from **Problem 10**:
$$f(x) = x^2 - 3x + 1$$
and the point:
$$x_0 = 2$$
*(We also show a second example in the Verification section using $f(x) = x^2$ from Problem 11 at $x_0 = 1$ for comparison.)*

First, we compute the value of the function at $x_0 = 2$:
$$f(2) = (2)^2 - 3(2) + 1 = 4 - 6 + 1 = -1$$

Next, we compute the exact derivative $f'(x)$ using the **Sum/Difference Rule**, **Power Rule**, **Constant Multiple Rule**, and **Constant Rule**:
$$f'(x) = \frac{d}{dx}\left(x^2\right) - 3\frac{d}{dx}(x) + \frac{d}{dx}(1) = 2x - 3$$

Evaluating $f'(x)$ at $x_0 = 2$ gives the exact derivative:
$$f'(2) = 2(2) - 3 = 1$$

---

### Step 2: Calculate the difference quotient for $h = 1$, $0.1$, and $0.01$

First, notice that for any $h \neq 0$ at $x_0 = 2$:
$$f(2 + h) = (2 + h)^2 - 3(2 + h) + 1 = (4 + 4h + h^2) - (6 + 3h) + 1 = -1 + h + h^2$$

Now let us compute the numerical values of the difference quotient $\frac{f(2 + h) - f(2)}{h}$ for the three required step sizes:

1. **For $h = 1$:**
   - $x_0 + h = 2 + 1 = 3$
   - $f(3) = 3^2 - 3(3) + 1 = 9 - 9 + 1 = 1$
   - Difference quotient:
     $$\frac{f(2 + 1) - f(2)}{1} = \frac{1 - (-1)}{1} = \frac{2}{1} = 2$$

2. **For $h = 0.1$:**
   - $x_0 + h = 2 + 0.1 = 2.1$
   - $f(2.1) = (2.1)^2 - 3(2.1) + 1 = 4.41 - 6.3 + 1 = -0.89$
   - Difference quotient:
     $$\frac{f(2.1) - f(2)}{0.1} = \frac{-0.89 - (-1)}{0.1} = \frac{0.11}{0.1} = 1.1$$

3. **For $h = 0.01$:**
   - $x_0 + h = 2 + 0.01 = 2.01$
   - $f(2.01) = (2.01)^2 - 3(2.01) + 1 = 4.0401 - 6.03 + 1 = -0.9899$
   - Difference quotient:
     $$\frac{f(2.01) - f(2)}{0.01} = \frac{-0.9899 - (-1)}{0.01} = \frac{0.0101}{0.01} = 1.01$$

---

### Step 3: Compare the values with $f'(x_0) = 1$

Let us organize our results in a table:

| Step size $h$ | $x_0 + h$ | $f(x_0 + h)$ | Difference quotient $\frac{f(2+h)-f(2)}{h}$ | Exact derivative $f'(2)$ | Approximation error $\left|\frac{f(2+h)-f(2)}{h} - f'(2)\right|$ |
| :---: | :---: | :---: | :---: | :---: | :---: |
| $1$ | $3$ | $1$ | $2$ | $1$ | $1$ |
| $0.1$ | $2.1$ | $-0.89$ | $1.1$ | $1$ | $0.1$ |
| $0.01$ | $2.01$ | $-0.9899$ | $1.01$ | $1$ | $0.01$ |

As $h$ decreases by a factor of $10$ (from $1$ to $0.1$ to $0.01$), the sequence of difference quotients
$$2 \longrightarrow 1.1 \longrightarrow 1.01$$
gets progressively closer to the exact derivative $f'(2) = 1$, and the error shrinks proportionally to $h$ ($1 \to 0.1 \to 0.01$).

---

### Step 4: Explain why this is consistent with the definition of the derivative, and why a few computations do not replace a limit argument

1. **Why approaching a single number is consistent with the definition of the derivative:**
   By definition, $f'(x_0) = \lim_{h \to 0} \frac{f(x_0 + h) - f(x_0)}{h}$ means that we can make the difference quotient $\frac{f(x_0 + h) - f(x_0)}{h}$ as close as we wish to $f'(x_0)$ by choosing $h \neq 0$ sufficiently close to $0$. Algebraically, for $f(x) = x^2 - 3x + 1$ at $x_0 = 2$:
   $$\frac{f(2 + h) - f(2)}{h} = \frac{(-1 + h + h^2) - (-1)}{h} = \frac{h(1 + h)}{h} = 1 + h \quad (h \neq 0)$$
   Seeing the numerical values $1 + 1 = 2$, $1 + 0.1 = 1.1$, and $1 + 0.01 = 1.01$ approach $1$ as $h$ gets smaller directly reflects this limit behavior.

2. **Why a few numerical computations do NOT replace a limit argument:**
   - **Only positive discrete steps were tested:** Evaluating $h = 1, 0.1, 0.01$ checks only **three positive numbers** ($h > 0$). A true two-sided limit $\lim_{h \to 0}$ requires the difference quotient to approach the **same** value for **all** paths $h \to 0$, including **negative values** ($h \to 0^-$). For example, the piecewise function $f(x)$ in Problem 14 with $a = 1$ gives difference quotients $1, 0.1, 0.01 \to 0$ at $x_0 = 0$ for $h = 1, 0.1, 0.01 > 0$, even though the derivative $f'(0)$ **does not exist** (because for $h < 0$, the difference quotient equals $1$)!
   - **Behavior at much smaller scales can change:** A function can behave nicely at $h = 1, 0.1, 0.01$ and yet oscillate wildly or jump at scales smaller than $0.01$ (for example, adding a term like $10^{-6}\sin(\pi/h)$ vanishes at $h = 1, 0.1, 0.01$ but prevents the limit as $h \to 0$ from existing).
   - **Rounding vs. exactness:** Numerical evaluations for transcendental functions (like $\sin x$, $e^x$, $\ln x$) only yield decimal approximations (such as $1.609\dots$ for $\ln 5$) and suffer from floating-point cancellation error when $h$ is extremely small, whereas a limit argument proves the **exact** symbolic value for **every** $h \to 0$.

## Verification and Consistency Checks

1. **Checking Negative Step Sizes ($h < 0$) at $x_0 = 2$:**
   Using $h = -1, -0.1, -0.01$ in $\frac{f(2+h)-f(2)}{h} = 1 + h$:
   - For $h = -1$: $\frac{f(1) - f(2)}{-1} = \frac{-1 - (-1)}{-1} = 0$
   - For $h = -0.1$: $\frac{f(1.9) - f(2)}{-0.1} = \frac{-1.09 - (-1)}{-0.1} = 0.9$
   - For $h = -0.01$: $\frac{f(1.99) - f(2)}{-0.01} = \frac{-1.0099 - (-1)}{-0.01} = 0.99$
   Both from the right ($2, 1.1, 1.01$) and from the left ($0, 0.9, 0.99$), the difference quotients squeeze toward $f'(2) = 1$.

2. **Second Quick Example ($f(x) = x^2$ from Problem 11 at $x_0 = 1$):**
   Here $f'(x) = 2x$, so $f'(1) = 2$, and $\frac{(1+h)^2 - 1^2}{h} = 2 + h$:
   - $h = 1 \implies \frac{4 - 1}{1} = 3$
   - $h = 0.1 \implies \frac{1.21 - 1}{0.1} = 2.1$
   - $h = 0.01 \implies \frac{1.0201 - 1}{0.01} = 2.01 \longrightarrow 2 = f'(1)$.
