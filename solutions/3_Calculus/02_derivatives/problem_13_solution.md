# Problem 13: A Multi-Layer Composition

## Problem Statement

For
$$f(x)=e^{\sin(x^2)}$$
compute the derivative. First write the layers
$$x\longrightarrow x^2\longrightarrow \sin(x^2)\longrightarrow e^{\sin(x^2)}$$
and explain why differentiation moves through them in the reverse order.

## Theoretical Background and Concepts

When a function is built by composing three (or more) functions in succession,
$$f(x) = g\big(h(k(x))\big),$$
we can visualize it as a pipeline of **layers** that transform the input $x$ step by step:
$$x \xrightarrow{\;\;k\;\;} u = k(x) \xrightarrow{\;\;h\;\;} v = h(u) \xrightarrow{\;\;g\;\;} y = g(v)$$

To differentiate a multi-layer composition, we apply the **Generalized Chain Rule** repeatedly from the outermost layer to the innermost layer:
$$f'(x) = \frac{dy}{dx} = \frac{dy}{dv} \cdot \frac{dv}{du} \cdot \frac{du}{dx} = g'\big(h(k(x))\big) \cdot h'\big(k(x)\big) \cdot k'(x)$$

In this problem, the three elementary derivatives required for the layers are:
- **Outer layer (Exponential Rule)**: $\frac{d}{dv}\left(e^v\right) = e^v$
- **Middle layer (Sine Rule)**: $\frac{d}{du}(\sin u) = \cos u$
- **Inner layer (Power Rule)**: $\frac{d}{dx}\left(x^2\right) = 2x$

## Detailed Step-by-Step Solution

### Step 1: Write down the layers of the composition

When we **evaluate** $f(x) = e^{\sin(x^2)}$ at a given number $x$, we work from the **inside out** through three layers:
$$x \xrightarrow{\text{Layer 1 (inner): square}} u = x^2 \xrightarrow{\text{Layer 2 (middle): sine}} v = \sin(x^2) \xrightarrow{\text{Layer 3 (outer): exponential}} y = e^{\sin(x^2)}$$

Explicitly, the three component functions are:
1. **Innermost function:** $u = k(x) = x^2$
2. **Middle function:** $v = h(u) = \sin u = \sin(x^2)$
3. **Outermost function:** $y = g(v) = e^v = e^{\sin(x^2)}$

---

### Step 2: Explain why differentiation moves through the layers in the reverse order

Why do we **evaluate** $f(x)$ from inside to outside ($x \to x^2 \to \sin(x^2) \to e^{\sin(x^2)}$), whereas when we **differentiate** $f(x)$, we peel off the layers in the **reverse order** (from outside to inside: exponential first, then sine, then square)?

1. **Structural ("peeling an onion") reason:**
   The expression $f(x) = e^{\sin(x^2)}$ is, as a whole, an **exponential** $e^{(\text{something})}$ whose input happens to be $v = \sin(x^2)$. Before we can reach the inner operations, we must first ask how the outermost operation $g(v) = e^v$ responds to changes in its immediate argument $v = \sin(x^2)$. This gives the outer derivative $g'(v) = e^{\sin(x^2)}$, leaving us with the remaining task of multiplying by $\frac{d}{dx}[\sin(x^2)]$. Next, $\sin(x^2)$ is a **sine** function whose input is $u = x^2$, so differentiating it yields $\cos(x^2)$ times the remaining derivative $\frac{d}{dx}(x^2) = 2x$. Just like unwrapping a nested package, you must open the outer box before you can open the middle box and the inner box.

2. **Rate-of-change (Leibniz chain) reason:**
   In Leibniz notation, the total sensitivity of the final output $y$ to the initial input $x$ is the product of the sensitivities of each stage:
   $$\frac{dy}{dx} = \underbrace{\frac{dy}{dv}}_{\text{outer}} \cdot \underbrace{\frac{dv}{du}}_{\text{middle}} \cdot \underbrace{\frac{du}{dx}}_{\text{inner}}$$
   Each derivative is evaluated at the output produced by all the layers inside it: $\frac{dy}{dv}$ is evaluated at $v = \sin(x^2)$, $\frac{dv}{du}$ is evaluated at $u = x^2$, and $\frac{du}{dx}$ is evaluated at $x$.

---

### Step 3: Compute the derivative layer by layer (from outside to inside)

Applying the **Chain Rule** step by step from the outermost layer to the innermost layer:

1. **Differentiate the outer layer $g(v) = e^v$** (keeping $v = \sin(x^2)$ inside):
   $$f'(x) = \frac{d}{dx}\left(e^{\sin(x^2)}\right) = e^{\sin(x^2)} \cdot \frac{d}{dx}\big[\sin(x^2)\big]$$

2. **Differentiate the middle layer $h(u) = \sin u$** (keeping $u = x^2$ inside):
   $$\frac{d}{dx}\big[\sin(x^2)\big] = \cos(x^2) \cdot \frac{d}{dx}\left(x^2\right)$$
   Substituting this into our expression gives:
   $$f'(x) = e^{\sin(x^2)} \cdot \cos(x^2) \cdot \frac{d}{dx}\left(x^2\right)$$

3. **Differentiate the inner layer $k(x) = x^2$** using the **Power Rule**:
   $$\frac{d}{dx}\left(x^2\right) = 2x$$

Multiplying all three factors together gives the final derivative:
$$f'(x) = 2x \cos(x^2) e^{\sin(x^2)}$$

## Verification and Consistency Checks

1. **Taylor Expansion Check near $x = 0$:**
   Near $x = 0$, we have $\sin(x^2) = x^2 - \frac{x^6}{6} + \dots \approx x^2$, and therefore:
   $$f(x) = e^{\sin(x^2)} = 1 + \sin(x^2) + \frac{1}{2}\sin^2(x^2) + \dots = 1 + x^2 + \frac{1}{2}x^4 + O(x^6)$$
   Differentiating this series term by term gives:
   $$f'(x) = 2x + 2x^3 + O(x^5)$$
   Now let us expand our exact derivative $f'(x) = 2x \cos(x^2) e^{\sin(x^2)}$ near $x = 0$:
   $$2x\left(1 - O(x^4)\right)\left(1 + x^2 + O(x^4)\right) = 2x + 2x^3 + O(x^5)$$
   Both expansions match to third order!

2. **Numerical Check at $x = 1$:**
   At $x = 1$ radian:
   $$f'(1) = 2(1)\cos(1)e^{\sin(1)} \approx 2(0.5403023)(e^{0.8414710}) \approx 1.0806046 \times 2.3197768 \approx 2.50676$$
   Using the symmetric difference quotient with $h = 0.001$:
   $$f(1.001) = e^{\sin(1.002001)} \approx e^{0.8425505} \approx 2.3222823$$
   $$f(0.999) = e^{\sin(0.998001)} \approx e^{0.8403893} \approx 2.3172688$$
   $$\frac{f(1.001) - f(0.999)}{0.002} \approx \frac{0.0050135}{0.002} \approx 2.50675$$
   This matches our exact formula to five significant digits.
