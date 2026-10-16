# Problem 9: One-Sided Limits and an Asymptote

## Problem Statement

Analyze the left-hand and right-hand limits of
$$f(x)=\frac1{x-2}$$
as $x\to2$. Does the two-sided limit exist? Interpret the result on a sketch of the graph and identify the vertical asymptote.

## Theoretical Background and Concepts

When a function behaves differently depending on whether the argument $x$ approaches a point $x_0$ from values smaller than $x_0$ or from values larger than $x_0$, we study **one-sided limits**:
1. **Left-Hand Limit ($\lim_{x\to x_0^-} f(x)$)**: The behavior of $f(x)$ as $x$ approaches $x_0$ from the left, meaning $x < x_0$ (so the difference $x - x_0 < 0$ is strictly negative and approaches $0$).
2. **Right-Hand Limit ($\lim_{x\to x_0^+} f(x)$)**: The behavior of $f(x)$ as $x$ approaches $x_0$ from the right, meaning $x > x_0$ (so the difference $x - x_0 > 0$ is strictly positive and approaches $0$).

**Existence Criterion for a Two-Sided Limit**:
The two-sided limit $\lim_{x\to x_0} f(x)$ exists (either as a finite number $L$ or as a single signed infinity $+\infty$ or $-\infty$ in the extended sense) **if and only if** both the left-hand limit and the right-hand limit exist and are equal:
$$\lim_{x\to x_0} f(x) = L \quad \Longleftrightarrow \quad \lim_{x\to x_0^-} f(x) = \lim_{x\to x_0^+} f(x) = L.$$
In standard real analysis, for a limit to exist as a *finite* number, $L$ must be finite; moreover, if $\lim_{x\to x_0^-} f(x) = -\infty$ and $\lim_{x\to x_0^+} f(x) = +\infty$, the two-sided limit does not exist even in the extended real numbers because the two sides diverge in opposite directions.

**Reciprocal of a Vanishing Quantity $\left[\frac{c}{0^\pm}\right]$ and Vertical Asymptotes**:
- When the numerator approaches a non-zero constant $c \neq 0$ and the denominator approaches $0$ with a definite sign ($0^+$ or $0^-$), the fraction is **not** an indeterminate form—its magnitude grows without bound toward $\pm\infty$:
  $$\left[\frac{1}{0^+}\right] = +\infty, \qquad \left[\frac{1}{0^-}\right] = -\infty.$$
- Geometrically, the vertical line $x = x_0$ is called a **vertical asymptote** of the graph of $y = f(x)$ if at least one of the one-sided limits $\lim_{x\to x_0^-} f(x)$ or $\lim_{x\to x_0^+} f(x)$ equals $+\infty$ or $-\infty$.

## Detailed Step-by-Step Solution

### Step 1: Analyze the Left-Hand Limit as $x \to 2^-$

Consider $f(x) = \frac{1}{x-2}$ as $x$ approaches $2$ from the left ($x \to 2^-$):
- Here, $x < 2$, which implies that the denominator satisfies:
  $$x - 2 < 0.$$
- As $x$ gets arbitrarily close to $2$ with $x < 2$, the denominator $x - 2$ approaches $0$ through **strictly negative** values, which we denote symbolically as $x - 2 \to 0^-$.
- The numerator is the positive constant $1 > 0$. Dividing $1$ by a negative number whose magnitude is arbitrarily small produces a negative number whose magnitude is arbitrarily large:
  $$\lim_{x\to 2^-} \frac{1}{x-2} = \left[\frac{1}{0^-}\right] = -\infty.$$

### Step 2: Analyze the Right-Hand Limit as $x \to 2^+$

Now consider $f(x) = \frac{1}{x-2}$ as $x$ approaches $2$ from the right ($x \to 2^+$):
- Here, $x > 2$, which implies that the denominator satisfies:
  $$x - 2 > 0.$$
- As $x$ gets arbitrarily close to $2$ with $x > 2$, the denominator $x - 2$ approaches $0$ through **strictly positive** values, which we denote symbolically as $x - 2 \to 0^+$.
- Dividing the positive constant $1$ by a positive number arbitrarily close to $0$ produces a positive number that grows without bound:
  $$\lim_{x\to 2^+} \frac{1}{x-2} = \left[\frac{1}{0^+}\right] = +\infty.$$

### Step 3: Does the Two-Sided Limit Exist?

Comparing the left-hand and right-hand limits at $x = 2$:
$$\lim_{x\to 2^-} \frac{1}{x-2} = -\infty \qquad \text{and} \qquad \lim_{x\to 2^+} \frac{1}{x-2} = +\infty.$$

**No, the two-sided limit $\lim_{x\to 2} \frac{1}{x-2}$ does not exist.**
- First, neither one-sided limit is a finite real number (both diverge to infinity).
- Second, even in the extended sense of infinite limits, the left-hand and right-hand limits do not agree because one diverges downward to $-\infty$ while the other diverges upward to $+\infty$ ($-\infty \neq +\infty$).

### Step 4: Sketch of the Graph, Geometric Interpretation, and Vertical Asymptote

#### Identification of the Vertical Asymptote
Because $\lim_{x\to 2^-} f(x) = -\infty$ and $\lim_{x\to 2^+} f(x) = +\infty$, the vertical line
$$\mathbf{x = 2}$$
is a **vertical asymptote** of the graph of $f(x) = \frac{1}{x-2}$. (Note also that as $x \to \pm\infty$, $\lim_{x\to\pm\infty} \frac{1}{x-2} = 0$, so the horizontal line $y = 0$ is a horizontal asymptote.)

#### ASCII Sketch of the Graph of $f(x) = \frac{1}{x-2}$

```text
                y
                ^
             +4 |         :  * (2.25, 4)
                |         :
             +2 |         :    * (2.5, 2)
                |         :
             +1 |         :        * (3, 1)
                |         :                * (4, 0.5)
  --------------+---------+--------+-------+---------> x
   * (0, -0.5)  |       1 : 2      3       4
        * (1,-1)|         :
                |    *    :
             -2 | (1.5,-2):
                |         :
             -4 |      *  :
                | (1.75,-4)
                          ^
                  Vertical Asymptote
                       x = 2
```

#### Geometric Interpretation on the Graph
The graph of $f(x) = \frac{1}{x-2}$ is a **rectangular hyperbola** (the standard graph of $y = \frac{1}{x}$ shifted $2$ units to the right) split into two separate branches by the vertical line $x = 2$:
- **Left branch ($x < 2$)**: Lies below the $x$-axis ($f(x) < 0$). As $x$ moves toward $2$ from the left, the curve plunges steeply downward without bound, hugging closer and closer to the vertical line $x = 2$ as $y \to -\infty$.
- **Right branch ($x > 2$)**: Lies above the $x$-axis ($f(x) > 0$). As $x$ moves toward $2$ from the right, the curve shoots steeply upward without bound, hugging closer and closer to the vertical line $x = 2$ as $y \to +\infty$.

## Verification and Consistency Checks

Let us verify the behavior on both sides of $x = 2$ with a concrete table of values:

| Approach from Left ($x \to 2^-$) | $x - 2$ | $f(x) = \frac{1}{x-2}$ | Approach from Right ($x \to 2^+$) | $x - 2$ | $f(x) = \frac{1}{x-2}$ |
| :--- | :--- | :--- | :--- | :--- | :--- |
| $x = 1.9$ | $-0.1$ | $-10$ | $x = 2.1$ | $+0.1$ | $+10$ |
| $x = 1.99$ | $-0.01$ | $-100$ | $x = 2.01$ | $+0.01$ | $+100$ |
| $x = 1.999$ | $-0.001$ | $-1,000$ | $x = 2.001$ | $+0.001$ | $+1,000$ |
| $x = 1.9999$ | $-0.0001$ | $-10,000$ | $x = 2.0001$ | $+0.0001$ | $+10,000$ |

Each time the distance $|x - 2|$ is reduced by a factor of $10$, $|f(x)|$ increases by a factor of $10$, with negative values on the left ($-\infty$) and positive values on the right ($+\infty$). This confirms our analytical conclusions.
