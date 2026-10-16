# Problem 1: Derivative of a Polynomial and the Slope of a Tangent Line

## Problem Statement

For
$$f(x)=3x^5-2x^3+7x-4$$
find $f'(x)$. Then compute $f'(0)$ and $f'(1)$, determine the signs of the obtained values, and explain what they say about the slope of the tangent line to the graph at these two points.

## Theoretical Background and Concepts

The **derivative** of a function $f$ at a point $x$, denoted $f'(x)$, measures the instantaneous rate of change of $f(x)$ with respect to $x$. Geometrically, $f'(x_0)$ is the **slope of the tangent line** to the graph of $y = f(x)$ at the point $(x_0, f(x_0))$:
- If $f'(x_0) > 0$, the tangent line has a positive slope (it rises from left to right), indicating that the function is locally increasing around $x_0$.
- If $f'(x_0) < 0$, the tangent line has a negative slope (it falls from left to right), indicating that the function is locally decreasing around $x_0$.
- If $f'(x_0) = 0$, the tangent line is horizontal.

To differentiate a polynomial, we use four fundamental rules of differentiation:
1. **Sum and Difference Rule**: The derivative of a sum or difference of differentiable functions is the sum or difference of their derivatives:
   $$\frac{d}{dx}[u(x) \pm v(x)] = u'(x) \pm v'(x)$$
2. **Constant Multiple Rule**: A constant factor can be pulled out in front of the derivative:
   $$\frac{d}{dx}[c \cdot u(x)] = c \cdot u'(x)$$
3. **Power Rule**: For any real exponent $n$,
   $$\frac{d}{dx}\left(x^n\right) = n x^{n-1}$$
   In particular, for $n = 1$, $\frac{d}{dx}(x) = 1 \cdot x^0 = 1$.
4. **Constant Rule**: The derivative of a constant $c$ is zero:
   $$\frac{d}{dx}(c) = 0$$

## Detailed Step-by-Step Solution

### Step 1: Compute the derivative $f'(x)$

We are given the polynomial
$$f(x) = 3x^5 - 2x^3 + 7x - 4$$

Because $f(x)$ is a combination of terms added and subtracted together, we first apply the **Sum and Difference Rule** to differentiate term by term:
$$f'(x) = \frac{d}{dx}\left(3x^5\right) - \frac{d}{dx}\left(2x^3\right) + \frac{d}{dx}(7x) - \frac{d}{dx}(4)$$

Next, we apply the **Constant Multiple Rule** to the first three terms to factor out the constant coefficients $3$, $2$, and $7$:
$$f'(x) = 3\frac{d}{dx}\left(x^5\right) - 2\frac{d}{dx}\left(x^3\right) + 7\frac{d}{dx}(x) - \frac{d}{dx}(4)$$

Now we apply the **Power Rule**, $\frac{d}{dx}(x^n) = nx^{n-1}$, to the powers of $x$, and the **Constant Rule**, $\frac{d}{dx}(c) = 0$, to the constant term $4$:
- For $x^5$ ($n = 5$): $\frac{d}{dx}(x^5) = 5x^{5-1} = 5x^4$
- For $x^3$ ($n = 3$): $\frac{d}{dx}(x^3) = 3x^{3-1} = 3x^2$
- For $x = x^1$ ($n = 1$): $\frac{d}{dx}(x^1) = 1 \cdot x^{1-1} = 1 \cdot x^0 = 1$
- For the constant $4$: $\frac{d}{dx}(4) = 0$

Substituting these derivatives back into the expression gives:
$$f'(x) = 3\left(5x^4\right) - 2\left(3x^2\right) + 7(1) - 0$$

Simplifying the coefficients, we obtain the derivative formula:
$$f'(x) = 15x^4 - 6x^2 + 7$$

---

### Step 2: Compute $f'(0)$ and $f'(1)$

1. **At $x = 0$:**
   Substitute $x = 0$ into $f'(x)$:
   $$f'(0) = 15(0)^4 - 6(0)^2 + 7 = 15(0) - 6(0) + 7 = 0 - 0 + 7 = 7$$

2. **At $x = 1$:**
   Substitute $x = 1$ into $f'(x)$:
   $$f'(1) = 15(1)^4 - 6(1)^2 + 7 = 15(1) - 6(1) + 7 = 15 - 6 + 7 = 16$$

---

### Step 3: Determine the signs and explain their geometric meaning

- **At $x = 0$:**
  - **Value and sign:** $f'(0) = 7 > 0$ (positive).
  - **Geometric interpretation:** At the point $(0, f(0)) = (0, -4)$, the tangent line to the graph of $f$ has a **positive slope of $7$**. This means the tangent line slants upward from left to right (rising $7$ units vertically for every $1$ unit of horizontal run), and the function $f(x)$ is strictly increasing as it passes through $x = 0$.

- **At $x = 1$:**
  - **Value and sign:** $f'(1) = 16 > 0$ (positive).
  - **Geometric interpretation:** At the point $(1, f(1)) = (1, 4)$, the tangent line to the graph of $f$ has a **positive slope of $16$**. The tangent line also slants upward from left to right, and because $16 > 7$, the graph is rising even more steeply at $x = 1$ than at $x = 0$.

*(Bonus observation: Completing the square on $f'(x) = 15\left(x^2 - \frac{1}{5}\right)^2 + \frac{32}{5}$ shows that $f'(x) \ge \frac{32}{5} > 0$ for all $x \in \mathbb{R}$, so every tangent line to this curve has positive slope.)*

## Verification and Consistency Checks

1. **Finite-Difference Verification at $x = 0$:**
   Using a small step $h = 0.001$, we compute the difference quotient:
   $$\frac{f(0.001) - f(0)}{0.001} = \frac{\left(3(0.001)^5 - 2(0.001)^3 + 7(0.001) - 4\right) - (-4)}{0.001} = 3(10^{-12}) - 2(10^{-6}) + 7 \approx 6.999998$$
   As $h \to 0$, this approaches $7$, matching $f'(0) = 7$.

2. **Finite-Difference Verification at $x = 1$:**
   At $x = 1$, $f(1) = 3(1) - 2(1) + 7(1) - 4 = 4$. For $h = 0.001$:
   $$f(1.001) = 3(1.001)^5 - 2(1.001)^3 + 7(1.001) - 4 \approx 3(1.00501001) - 2(1.003003001) + 7.007 - 4 \approx 4.016024$$
   Thus:
   $$\frac{f(1.001) - f(1)}{0.001} \approx \frac{4.016024 - 4}{0.001} = 16.024 \to 16 \quad \text{as } h \to 0$$
   This confirms $f'(1) = 16$.

3. **Degree Check:**
   Differentiating a polynomial of degree $5$ yields a polynomial of degree $4$, and the constant term $-4$ vanishes, as expected.
