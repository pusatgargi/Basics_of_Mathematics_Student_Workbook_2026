# Problem 2: Powers, Roots, and the Domain

## Problem Statement

For
$$f(x)=2\sqrt{x}-\frac{3}{x^2}+x^{3/2}$$
1. rewrite the function using powers,
2. determine the domain,
3. compute the derivative,
4. compare the domain of the function with the domain of its derivative.

## Theoretical Background and Concepts

Many algebraic expressions involving radicals (roots) and fractions with powers in the denominator can be differentiated directly with the **Power Rule** once they are rewritten using rational and negative exponents:
- **Radical to fractional exponent**: $\sqrt[m]{x^k} = x^{k/m}$ (in particular, $\sqrt{x} = x^{1/2}$ for $x \ge 0$).
- **Reciprocal to negative exponent**: $\frac{1}{x^k} = x^{-k}$ for $x \neq 0$.

Once each term is in the form $c \cdot x^n$, we apply:
1. **Sum and Difference Rule**: $\frac{d}{dx}[u(x) \pm v(x)] = u'(x) \pm v'(x)$
2. **Constant Multiple Rule**: $\frac{d}{dx}[c \cdot u(x)] = c \cdot u'(x)$
3. **General Power Rule**: For any real exponent $n \in \mathbb{R}$,
   $$\frac{d}{dx}\left(x^n\right) = n x^{n-1}$$

**Domains and Differentiability**:
The **domain** of a function is the set of all real inputs $x$ for which every part of the formula produces a well-defined real number. When we differentiate a function involving fractional exponents (such as $x^{1/2}$), the exponent decreases by $1$ (becoming $x^{-1/2} = \frac{1}{\sqrt{x}}$), which moves the root into the denominator. Consequently, boundary points where $x = 0$ may belong to the domain of $f$ (if not already excluded), or may fail to belong to the domain of $f'$ because a vertical tangent or division by zero occurs at $x = 0$.

## Detailed Step-by-Step Solution

### Part 1: Rewrite the function using powers

We convert the square root and the fraction into power form $x^n$:
- $\sqrt{x} = x^{1/2}$, so $2\sqrt{x} = 2x^{1/2}$.
- $\frac{3}{x^2} = 3 \cdot \frac{1}{x^2} = 3x^{-2}$.
- $x^{3/2}$ is already written as a power.

Therefore, the function written using powers is:
$$f(x) = 2x^{1/2} - 3x^{-2} + x^{3/2}$$

---

### Part 2: Determine the domain of $f$

To find the natural domain $D_f \subset \mathbb{R}$, we examine the restrictions imposed by each term of $f(x) = 2\sqrt{x} - \frac{3}{x^2} + x^{3/2}$:
1. The term $2\sqrt{x}$ requires the radicand to be non-negative: $x \ge 0$.
2. The term $-\frac{3}{x^2}$ has $x^2$ in the denominator, which requires no division by zero: $x^2 \neq 0 \implies x \neq 0$.
3. The term $x^{3/2} = (\sqrt{x})^3$ requires $x \ge 0$.

Taking the intersection of all conditions ($x \ge 0$ and $x \neq 0$), we obtain $x > 0$. Thus, the domain of $f$ is:
$$D_f = (0, \infty)$$

---

### Part 3: Compute the derivative $f'(x)$

Starting from the power form $f(x) = 2x^{1/2} - 3x^{-2} + x^{3/2}$, we apply the **Sum and Difference Rule** and the **Constant Multiple Rule** to differentiate term by term:
$$f'(x) = 2\frac{d}{dx}\left(x^{1/2}\right) - 3\frac{d}{dx}\left(x^{-2}\right) + \frac{d}{dx}\left(x^{3/2}\right)$$

Now we apply the **Power Rule**, $\frac{d}{dx}(x^n) = nx^{n-1}$, to each power:
1. For $x^{1/2}$ ($n = \frac{1}{2}$):
   $$\frac{d}{dx}\left(x^{1/2}\right) = \frac{1}{2}x^{\frac{1}{2}-1} = \frac{1}{2}x^{-1/2}$$
2. For $x^{-2}$ ($n = -2$):
   $$\frac{d}{dx}\left(x^{-2}\right) = (-2)x^{-2-1} = -2x^{-3}$$
3. For $x^{3/2}$ ($n = \frac{3}{2}$):
   $$\frac{d}{dx}\left(x^{3/2}\right) = \frac{3}{2}x^{\frac{3}{2}-1} = \frac{3}{2}x^{1/2}$$

Substituting these back into $f'(x)$:
$$f'(x) = 2\left(\frac{1}{2}x^{-1/2}\right) - 3\left(-2x^{-3}\right) + \frac{3}{2}x^{1/2}$$

Simplifying the coefficients (notice that $-3(-2) = +6$):
$$f'(x) = x^{-1/2} + 6x^{-3} + \frac{3}{2}x^{1/2}$$

Rewriting $f'(x)$ using radicals and positive exponents in denominators:
$$f'(x) = \frac{1}{\sqrt{x}} + \frac{6}{x^3} + \frac{3}{2}\sqrt{x}$$

---

### Part 4: Compare the domain of the function with the domain of its derivative

Let us determine the domain $D_{f'}$ of $f'(x) = \frac{1}{\sqrt{x}} + \frac{6}{x^3} + \frac{3}{2}\sqrt{x}$:
- The term $\frac{1}{\sqrt{x}}$ requires $x > 0$ (both inside a square root and in a denominator).
- The term $\frac{6}{x^3}$ requires $x \neq 0$.
- The term $\frac{3}{2}\sqrt{x}$ requires $x \ge 0$.

Intersecting these conditions gives:
$$D_{f'} = (0, \infty)$$

**Comparison:**
- The domain of the original function $f$ and the domain of its derivative $f'$ are **identical**:
  $$D_f = D_{f'} = (0, \infty)$$
- **Why does the domain not shrink here?** Normally, differentiating $\sqrt{x}$ produces $\frac{1}{2\sqrt{x}}$, which excludes $x = 0$ even though $\sqrt{x}$ is defined at $x = 0$. In our function $f(x)$, however, the term $-\frac{3}{x^2}$ **already excluded $x = 0$** from the domain of $f$. Therefore, no additional point was lost when differentiating.

## Verification and Consistency Checks

1. **Evaluation at a Test Point ($x = 1$):**
   Using the derivative formula at $x = 1$:
   $$f'(1) = 1^{-1/2} + 6(1)^{-3} + \frac{3}{2}(1)^{1/2} = 1 + 6 + 1.5 = 8.5$$
   Using the symmetric difference quotient around $x = 1$ with $h = 0.001$:
   $$f(1.001) = 2\sqrt{1.001} - \frac{3}{(1.001)^2} + (1.001)^{3/2} \approx 2(1.000499875) - 2.99400898 + 1.001500375 \approx 0.008491145$$
   $$f(0.999) = 2\sqrt{0.999} - \frac{3}{(0.999)^2} + (0.999)^{3/2} \approx 2(0.999499875) - 3.00600901 + 0.998500375 \approx -0.008508885$$
   $$\frac{f(1.001) - f(0.999)}{0.002} \approx \frac{0.01700003}{0.002} \approx 8.500015$$
   This matches $f'(1) = 8.5$.

2. **Sign and Exponent Check:**
   - $2x^{1/2} \xrightarrow{d/dx} x^{-1/2}$ (exponent drops by $1$ from $1/2$ to $-1/2$).
   - $-3x^{-2} \xrightarrow{d/dx} +6x^{-3}$ (exponent drops by $1$ from $-2$ to $-3$, and the negative coefficient multiplied by the negative exponent becomes positive).
   - $x^{3/2} \xrightarrow{d/dx} \frac{3}{2}x^{1/2}$ (exponent drops by $1$ from $3/2$ to $1/2$).
