# Problem 3: The Product Rule — Why Is It Needed?

## Problem Statement

For
$$f(x)=(x^2+1)e^x$$
compute the derivative. Then compare the correct result with the incorrect idea
$$f'(x)\stackrel{?}{=}(2x)e^x$$
and explain which term is missing.

## Theoretical Background and Concepts

When a function is formed by multiplying two differentiable functions $u(x)$ and $v(x)$, its derivative is **not** simply the product of the individual derivatives $u'(x)v'(x)$. Instead, because both factors change simultaneously as $x$ changes, we must apply the **Product Rule** (Leibniz Rule):
$$\frac{d}{dx}\big[u(x) \cdot v(x)\big] = u'(x)v(x) + u(x)v'(x)$$

Intuitively, if you think of $u(x)$ and $v(x)$ as the side lengths of a rectangle with area $A(x) = u(x)v(x)$, a small change $\Delta x$ causes the width to grow by $\Delta u$ and the height to grow by $\Delta v$. The new area increases by **two** main strips:
1. A strip of width $\Delta u$ and height $v(x)$ (giving the rate $u'(x)v(x)$), and
2. A strip of width $u(x)$ and height $\Delta v$ (giving the rate $u(x)v'(x)$).

In addition to the Product Rule, we use:
- **Power and Constant Rules**: $\frac{d}{dx}(x^2 + 1) = 2x + 0 = 2x$.
- **Natural Exponential Rule**: The function $e^x$ is its own derivative:
  $$\frac{d}{dx}\left(e^x\right) = e^x$$

## Detailed Step-by-Step Solution

### Step 1: Identify the factors and apply the Product Rule

The given function is a product of two functions of $x$:
$$f(x) = \underbrace{(x^2 + 1)}_{u(x)} \cdot \underbrace{e^x}_{v(x)}$$

Because both $u(x) = x^2 + 1$ and $v(x) = e^x$ depend on $x$, we must apply the **Product Rule**:
$$f'(x) = u'(x)v(x) + u(x)v'(x) = \left[\frac{d}{dx}(x^2 + 1)\right] e^x + (x^2 + 1)\left[\frac{d}{dx}\left(e^x\right)\right]$$

---

### Step 2: Differentiate each individual factor

1. **Derivative of the first factor $u(x) = x^2 + 1$:**
   Using the **Sum Rule**, **Power Rule**, and **Constant Rule**:
   $$u'(x) = \frac{d}{dx}\left(x^2\right) + \frac{d}{dx}(1) = 2x + 0 = 2x$$

2. **Derivative of the second factor $v(x) = e^x$:**
   Using the **Exponential Rule**:
   $$v'(x) = \frac{d}{dx}\left(e^x\right) = e^x$$

---

### Step 3: Combine and simplify

Substituting $u'(x) = 2x$ and $v'(x) = e^x$ into the Product Rule formula gives:
$$f'(x) = (2x)e^x + (x^2 + 1)e^x$$

We can factor out the common factor $e^x$ to write the derivative in a clean, compact form:
$$f'(x) = (x^2 + 2x + 1)e^x = (x + 1)^2 e^x$$

---

### Step 4: Compare with the incorrect formula and explain the missing term

The proposed incorrect formula is:
$$f'_{\text{incorrect}}(x) = (2x)e^x$$

Comparing this with the unfactored correct derivative
$$f'(x) = (2x)e^x + (x^2 + 1)e^x,$$
we see that:
- **Which term is missing?** The term **$(x^2 + 1)e^x$** (which represents $u(x)v'(x)$) is completely missing.
- **Why did the mistake happen?** The incorrect formula either:
  1. Treated $e^x$ as if it were a constant coefficient (differentiating only $x^2 + 1 \to 2x$ and copying $e^x$), or
  2. Applied the nonexistent "rule" $(uv)' = u'v'$, which—because $\frac{d}{dx}(e^x) = e^x$ happens to equal itself—accidentally produced $u'(x)v'(x) = (2x)e^x$.
- **Why is $(x^2+1)e^x$ essential?** As $x$ changes, $f(x) = (x^2+1)e^x$ changes for **two** independent reasons: the polynomial factor $(x^2+1)$ changes at rate $2x$ (scaled by the current value of $e^x$), **and** the exponential factor $e^x$ changes at rate $e^x$ (scaled by the current value of $x^2+1$). Ignoring the second contribution leaves out the growth of the exponential factor itself.

## Verification and Consistency Checks

1. **Concrete Counterexample at $x = 0$:**
   Let us check the slope of $f(x) = (x^2 + 1)e^x$ at $x = 0$:
   - The **incorrect formula** claims $f'_{\text{incorrect}}(0) = 2(0)e^0 = 0$ (a horizontal tangent).
   - The **correct formula** gives $f'(0) = (0 + 1)^2 e^0 = 1$.
   - Let us check $f(x)$ near $x = 0$ directly: at $x = 0$, $f(0) = (0+1)e^0 = 1$. At $x = 0.01$,
     $$f(0.01) = (0.0001 + 1)e^{0.01} \approx 1.0001 \times 1.01005017 \approx 1.01015$$
     The difference quotient is:
     $$\frac{f(0.01) - f(0)}{0.01} \approx \frac{1.01015 - 1}{0.01} = 1.015 \to 1 \quad \text{as } h \to 0$$
     Near $x = 0$, $x^2 + 1 \approx 1$, so $f(x) \approx 1 \cdot e^x$, which clearly has slope $1$ at $x = 0$, not $0$! The missing term $(x^2+1)e^x$ is the **entire** derivative at $x = 0$.

2. **Sign Analysis:**
   Since $f'(x) = (x + 1)^2 e^x$, and both $(x+1)^2 \ge 0$ and $e^x > 0$ for all $x \in \mathbb{R}$, the function $f(x)$ is non-decreasing everywhere, with a single horizontal inflection point at $x = -1$.
