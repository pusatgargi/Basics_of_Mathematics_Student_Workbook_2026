# Problem 3: A Rational Function

## Problem Statement

Analyze the domain, zeros, asymptotes, and monotonicity of
$$f(x)=\frac{x+1}{x-2}.$$
Finally, sketch a graph consistent with all the information obtained.

## Theoretical Background and Concepts

A linear fractional (homographic) rational function has the general form $f(x) = \frac{ax + b}{cx + d}$ with $c \neq 0$ and $ad - bc \neq 0$. A complete analysis relies on connecting the following concepts:

1. **Domain**: A rational function $\frac{P(x)}{Q(x)}$ is defined everywhere except at the roots of the denominator $Q(x) = 0$. Each root splits the domain into separate open intervals.
2. **Zeros and Intercepts**: $f(x) = 0 \iff P(x) = 0$ and $Q(x) \neq 0$. The $y$-intercept is $(0, f(0))$ whenever $0 \in D_f$.
3. **Asymptotes**:
   - **Vertical Asymptote**: If $\lim_{x \to x_0^-} f(x) = \pm\infty$ or $\lim_{x \to x_0^+} f(x) = \pm\infty$, then the vertical line $x = x_0$ is a vertical asymptote.
   - **Horizontal Asymptote**: If $\lim_{x \to \pm\infty} f(x) = L \in \mathbb{R}$, then the horizontal line $y = L$ is a horizontal asymptote. When a finite horizontal asymptote exists at $+\infty$ (or $-\infty$), no distinct oblique asymptote can exist in that direction.
4. **First Derivative, Monotonicity, and Extrema**:
   - By the quotient rule, $\left(\frac{u}{v}\right)' = \frac{u'v - uv'}{v^2}$. Since the denominator $v(x)^2$ is strictly positive on $D_f$, the sign of $f'(x)$ is determined entirely by the numerator $u'(x)v(x) - u(x)v'(x)$.
   - Monotonicity must be stated **separately on each connected interval** of the domain, because the function is discontinuous across the vertical asymptote.
5. **Second Derivative and Curvature**: The sign of $f''(x)$ determines whether each branch of the hyperbola is convex ($f''(x) > 0$) or concave ($f''(x) < 0$).

## Detailed Step-by-Step Solution

### Step 1: Domain and Algebraic Decomposition

The denominator vanishes when $x - 2 = 0 \iff x = 2$. Therefore, the domain consists of two disjoint open intervals:
$$D_f = \mathbb{R} \setminus \{2\} = (-\infty, 2) \cup (2, \infty).$$
We can also rewrite $f(x)$ by splitting the numerator as $x + 1 = (x - 2) + 3$:
$$f(x) = \frac{(x - 2) + 3}{x - 2} = 1 + \frac{3}{x - 2}.$$
This hyperbola form shows that the graph of $f$ is obtained by shifting the hyperbola $y = \frac{3}{x}$ by $2$ units to the right and $1$ unit upward.

### Step 2: Zeros and $y$-Intercept

- **Zeros ($x$-intercepts)**: For $x \in D_f$,
  $$f(x) = 0 \iff \frac{x + 1}{x - 2} = 0 \iff x + 1 = 0 \iff x = -1.$$
  Since $-1 \neq 2$, the unique zero is $x = -1$, corresponding to the point $(-1, 0)$.
- **$y$-intercept**: Setting $x = 0 \in D_f$ gives:
  $$f(0) = \frac{0 + 1}{0 - 2} = -\frac{1}{2} \implies \left(0, -\frac{1}{2}\right).$$

### Step 3: Limits and Asymptotes

1. **Behavior near $x = 2$ (Vertical Asymptote)**:
   - As $x \to 2^-$ (so $x < 2$ and $x - 2 \to 0^-$ while $x + 1 \to 3 > 0$):
     $$\lim_{x \to 2^-} \frac{x + 1}{x - 2} = \left[\frac{3}{0^-}\right] = -\infty.$$
   - As $x \to 2^+$ (so $x > 2$ and $x - 2 \to 0^+$ while $x + 1 \to 3 > 0$):
     $$\lim_{x \to 2^+} \frac{x + 1}{x - 2} = \left[\frac{3}{0^+}\right] = +\infty.$$
   Hence, the line **$x = 2$ is a two-sided vertical asymptote**.

2. **Behavior as $x \to \pm\infty$ (Horizontal Asymptote)**:
   Using the decomposition $f(x) = 1 + \frac{3}{x - 2}$:
   $$\lim_{x \to -\infty} f(x) = \lim_{x \to -\infty} \left(1 + \frac{3}{x - 2}\right) = 1 + 0 = 1,$$
   $$\lim_{x \to +\infty} f(x) = \lim_{x \to +\infty} \left(1 + \frac{3}{x - 2}\right) = 1 + 0 = 1.$$
   Note that for $x < 2$, $\frac{3}{x - 2} < 0$, so $f(x) < 1$ (the graph approaches $y = 1$ from **below** as $x \to -\infty$). For $x > 2$, $\frac{3}{x - 2} > 0$, so $f(x) > 1$ (the graph approaches $y = 1$ from **above** as $x \to +\infty$).
   Hence, the line **$y = 1$ is a two-sided horizontal asymptote** (and there are no oblique asymptotes).

### Step 4: First Derivative, Monotonicity, and Extrema

Differentiating $f(x) = \frac{x + 1}{x - 2}$ on $D_f$ using the quotient rule:
$$f'(x) = \frac{(x + 1)'(x - 2) - (x + 1)(x - 2)'}{(x - 2)^2} = \frac{1 \cdot (x - 2) - (x + 1) \cdot 1}{(x - 2)^2} = \frac{x - 2 - x - 1}{(x - 2)^2} = -\frac{3}{(x - 2)^2}.$$
Alternatively, differentiating $f(x) = 1 + 3(x - 2)^{-1}$ directly yields $f'(x) = -3(x - 2)^{-2} = -\frac{3}{(x - 2)^2}$.

For every $x \in D_f = (-\infty, 2) \cup (2, \infty)$, the denominator $(x - 2)^2$ is strictly positive, and the numerator is $-3 < 0$. Therefore:
$$f'(x) = -\frac{3}{(x - 2)^2} < 0 \quad \text{for all } x \in (-\infty, 2) \cup (2, \infty).$$

We also compute the second derivative to determine the curvature of each branch:
$$f''(x) = \frac{d}{dx}\left[-3(x - 2)^{-2}\right] = 6(x - 2)^{-3} = \frac{6}{(x - 2)^3}.$$
- On $(-\infty, 2)$: $x - 2 < 0 \implies f''(x) < 0$ (concave).
- On $(2, \infty)$: $x - 2 > 0 \implies f''(x) > 0$ (convex).

We summarize the behavior in the sign chart below:

| Interval / Point | $(-\infty, 2)$ | $x = 2$ | $(2, \infty)$ |
| :---: | :---: | :---: | :---: |
| Sign of $f'(x)$ | $-$ | undefined | $-$ |
| Sign of $f''(x)$ | $-$ | undefined | $+$ |
| Behavior of $f(x)$ | $\searrow$ from $1^-$ to $-\infty$ (concave) | **Vertical Asymptote** | $\searrow$ from $+\infty$ to $1^+$ (convex) |

**Conclusions on Monotonicity and Extrema**:
- $f$ is **strictly decreasing** on the interval $(-\infty, 2)$ and **strictly decreasing** on the interval $(2, \infty)$. *(Note: We do not say $f$ is decreasing on the union $(-\infty, 2) \cup (2, \infty)$ as a single set, because for $-1 < 3$ we have $f(-1) = 0 < 4 = f(3)$.)*
- Since $f'(x) \neq 0$ for all $x \in D_f$, there are **no critical points**, **no local extrema**, and **no inflection points**.

### Step 5: Structured Summary of Features and Graph Sketch

- **Domain**: $(-\infty, 2) \cup (2, \infty)$
- **Zero ($x$-intercept)**: $(-1, 0)$
- **$y$-intercept**: $\left(0, -\frac{1}{2}\right)$
- **Vertical Asymptote**: $x = 2$ ($\lim_{x \to 2^-} f(x) = -\infty$, $\lim_{x \to 2^+} f(x) = +\infty$)
- **Horizontal Asymptote**: $y = 1$ ($\lim_{x \to \pm\infty} f(x) = 1$)
- **Monotonicity**: Strictly decreasing on $(-\infty, 2)$ and strictly decreasing on $(2, \infty)$
- **Extrema / Inflection Points**: None
- **Curvature**: Concave on $(-\infty, 2)$, convex on $(2, \infty)$

```text
                                    y
                                    ^
                                  5 +           :  | (x -> 2+, y -> +inf)
                                    |           :   \
                                  4 +           :    * (3, 4)
                                    |           :      \
                                  3 +           :        \
                                    |           :          * (4, 2.5)
                                  2 +           :            * (5, 2)
                                    |           :              \
     y = 1 - - - - - - - - - - - - -+- - - - - -:- - - - - - - - ' - . _ _ (y -> 1+)
     (y -> 1-) ' ' - - .            |           :
                        * (-4, 0.5) |           :
                          \         |           :
                            ' - . _ |           :
  ----------------------+---------*-+-----+-----+-----+-----+---+---------+----> x
                       -4        -1 0     1     2     3     4   5
                               (-1,0)\    :     :
                                    * (0,-0.5)  :
                                    |  \  :     :
                                 -1 +    \:     :
                                    |     \     :
                                 -2 +     * (1, -2)
                                    |      \    :
                                 -3 +       \   :
                                    |        |  : (x -> 2-, y -> -inf)
                                              x = 2
```

## Verification and Consistency Checks

1. **Test Points on the Left Branch $(-\infty, 2)$**:
   - $f(-4) = \frac{-4 + 1}{-4 - 2} = \frac{-3}{-6} = 0.5$
   - $f(-1) = 0$
   - $f(0) = -0.5$
   - $f(1) = \frac{1 + 1}{1 - 2} = -2$
   Notice that for $-4 < -1 < 0 < 1 < 2$, we have $0.5 > 0 > -0.5 > -2$, all strictly less than the horizontal asymptote $y = 1$, confirming that $f$ is strictly decreasing on $(-\infty, 2)$ and approaches $-\infty$ as $x \to 2^-$.
2. **Test Points on the Right Branch $(2, \infty)$**:
   - $f(3) = \frac{3 + 1}{3 - 2} = 4$
   - $f(5) = \frac{5 + 1}{5 - 2} = 2$
   - $f(8) = \frac{8 + 1}{8 - 2} = 1.5$
   For $2 < 3 < 5 < 8$, we have $4 > 2 > 1.5 > 1$, confirming that $f$ is strictly decreasing on $(2, \infty)$ and approaches $y = 1$ from above as $x \to +\infty$.
3. **Hyperbola Center Symmetry Check**:
   The intersection of the asymptotes is $(2, 1)$. For any $h \neq 0$,
   $$f(2 + h) + f(2 - h) = \left(1 + \frac{3}{h}\right) + \left(1 - \frac{3}{h}\right) = 2 = 2 \cdot 1,$$
   confirming that the two branches of the graph are centrally symmetric about $(2, 1)$ (for instance, $(1, -2)$ and $(3, 4)$ have midpoint $\left(\frac{1+3}{2}, \frac{-2+4}{2}\right) = (2, 1)$).
