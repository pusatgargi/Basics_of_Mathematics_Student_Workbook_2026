# Problem 12: Several Rules at Once

## Problem Statement

For
$$f(x)=(x^2+1)^3e^x$$
compute the derivative. Before calculating, write down a plan: which rule applies to the whole expression and which rule applies to one of its factors. Finally, organize the result by factoring out common factors.

## Theoretical Background and Concepts

When differentiating a complex expression that combines multiple operations (such as powers, sums, products, and compositions), the key is to read the expression from the **outside in** (following the reverse of the order of operations used to evaluate it):
1. **Top-Level Structure (Product Rule)**:
   If the final operation performed when evaluating $f(x)$ is multiplying two expressions $u(x)$ and $v(x)$, then the **Product Rule** governs the entire derivative:
   $$\frac{d}{dx}\big[u(x)v(x)\big] = u'(x)v(x) + u(x)v'(x)$$
2. **Sub-Problem Structure (Chain Rule)**:
   When computing the derivative $u'(x)$ of an individual factor that is itself a composite function $u(x) = g(h(x))$, we apply the **Chain Rule** to that factor:
   $$u'(x) = g'(h(x)) \cdot h'(x)$$
3. **Basic Building-Block Rules**:
   Inside the Chain Rule and Product Rule, we use the **Power Rule** ($\frac{d}{dx}(x^n) = nx^{n-1}$), **Constant Rule** ($\frac{d}{dx}(c) = 0$), and **Natural Exponential Rule** ($\frac{d}{dx}(e^x) = e^x$).

## Detailed Step-by-Step Solution

### Step 1: Differentiation Plan (Before Calculating)

Before taking any derivatives, let us analyze the structure of
$$f(x) = \underbrace{(x^2 + 1)^3}_{u(x)} \cdot \underbrace{e^x}_{v(x)}$$

- **Which rule applies to the whole expression?**
  At the top level, $f(x)$ is the **product** of two functions of $x$: the first factor $u(x) = (x^2 + 1)^3$ and the second factor $v(x) = e^x$. Therefore, the **Product Rule** applies to the whole expression:
  $$f'(x) = u'(x)v(x) + u(x)v'(x)$$

- **Which rule applies to one of its factors?**
  To find $u'(x)$ for the first factor $u(x) = (x^2 + 1)^3$, we notice that $u(x)$ is a **composition** of an outer cubic power $g(w) = w^3$ and an inner polynomial $w = h(x) = x^2 + 1$. Therefore, the **Chain Rule** (combined with the Power Rule) applies to the first factor $(x^2 + 1)^3$, while the **Natural Exponential Rule** applies to the second factor $e^x$.

---

### Step 2: Differentiate the individual factors

1. **First factor $u(x) = (x^2 + 1)^3$ (using the Chain Rule):**
   - Outer derivative: $\frac{d}{dw}(w^3) = 3w^2 = 3(x^2 + 1)^2$.
   - Inner derivative: $\frac{d}{dx}(x^2 + 1) = 2x + 0 = 2x$.
   - Multiplying by the Chain Rule:
     $$u'(x) = 3(x^2 + 1)^2 \cdot (2x) = 6x(x^2 + 1)^2$$

2. **Second factor $v(x) = e^x$ (using the Exponential Rule):**
   $$v'(x) = \frac{d}{dx}\left(e^x\right) = e^x$$

---

### Step 3: Combine using the Product Rule

Substituting $u(x) = (x^2 + 1)^3$, $u'(x) = 6x(x^2 + 1)^2$, $v(x) = e^x$, and $v'(x) = e^x$ into the Product Rule formula $f'(x) = u'(x)v(x) + u(x)v'(x)$ gives:
$$f'(x) = 6x(x^2 + 1)^2 e^x + (x^2 + 1)^3 e^x$$

---

### Step 4: Organize the result by factoring out common factors

Both terms in $6x(x^2 + 1)^2 e^x + (x^2 + 1)^3 e^x$ share the common factors $(x^2 + 1)^2$ and $e^x$:
- From the first term $6x(x^2 + 1)^2 e^x$, factoring out $(x^2 + 1)^2 e^x$ leaves $6x$.
- From the second term $(x^2 + 1)^3 e^x = (x^2 + 1)(x^2 + 1)^2 e^x$, factoring out $(x^2 + 1)^2 e^x$ leaves $(x^2 + 1)$.

Factoring out $(x^2 + 1)^2 e^x$ yields:
$$f'(x) = (x^2 + 1)^2 e^x \big[6x + (x^2 + 1)\big]$$

Writing the quadratic polynomial inside the brackets in standard descending order of powers gives the final factored derivative:
$$f'(x) = (x^2 + 1)^2 (x^2 + 6x + 1) e^x$$

## Verification and Consistency Checks

1. **Alternative Method (Expanding the Cube Before Differentiating):**
   Using the binomial expansion $(x^2 + 1)^3 = x^6 + 3x^4 + 3x^2 + 1$, we can write:
   $$f(x) = \left(x^6 + 3x^4 + 3x^2 + 1\right)e^x$$
   By the Product Rule $\frac{d}{dx}[P(x)e^x] = [P'(x) + P(x)]e^x$:
   $$P'(x) + P(x) = \left(6x^5 + 12x^3 + 6x\right) + \left(x^6 + 3x^4 + 3x^2 + 1\right) = x^6 + 6x^5 + 3x^4 + 12x^3 + 3x^2 + 6x + 1$$
   Now let us expand our factored result $(x^2 + 1)^2(x^2 + 6x + 1)e^x$:
   $$(x^4 + 2x^2 + 1)(x^2 + 6x + 1) = x^6 + 6x^5 + x^4 + 2x^4 + 12x^3 + 2x^2 + x^2 + 6x + 1 = x^6 + 6x^5 + 3x^4 + 12x^3 + 3x^2 + 6x + 1$$
   The two polynomials match coefficient by coefficient! This also illustrates why factoring out $(x^2 + 1)^2 e^x$ is much cleaner than expanding.

2. **Check at $x = 0$:**
   At $x = 0$, our formula gives $f'(0) = (0 + 1)^2(0 + 0 + 1)e^0 = 1$. Since $f(x) = (1 + 3x^2 + \dots)e^x = (1 + O(x^2))(1 + x + O(x^2)) = 1 + x + O(x^2)$, the linear coefficient is indeed $f'(0) = 1$.
