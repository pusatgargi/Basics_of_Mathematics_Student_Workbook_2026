# Problem 5: An Exponential Function with a Maximum

## Problem Statement

Analyze the monotonicity and extrema of
$$f(x)=xe^{-x}.$$
Also examine the behavior as $x\to\infty$ and explain how the limit affects the shape of the graph on the right-hand side.

## Theoretical Background and Concepts

Functions formed as products of polynomials and exponentials, $f(x) = P(x)e^{kx}$, occur throughout mathematical analysis, probability, and physics. Analyzing them requires combining local derivative information with global asymptotic limits:

1. **Domain and Positivity of the Exponential Factor**: Both $x$ and $e^{-x}$ are defined and smooth on $\mathbb{R} = (-\infty, \infty)$. Crucially, $e^{-x} > 0$ for every $x \in \mathbb{R}$; it never vanishes and never changes sign.
2. **Product Rule and Factoring the Derivative**: By the product and chain rules,
   $$\frac{d}{dx}\left[P(x)e^{-x}\right] = \left(P'(x) - P(x)\right)e^{-x}.$$
   Because $e^{-x} > 0$ everywhere, the zeros and sign of $f'(x)$ are determined **entirely by the polynomial factor** $P'(x) - P(x)$.
3. **Asymptotic Dominance (Exponential vs. Polynomial Growth)**:
   As $x \to +\infty$, the exponential $e^x$ grows much faster than any power $x^n$ ($n > 0$):
   $$\lim_{x \to +\infty} \frac{x^n}{e^x} = 0.$$
   This can be justified either by L'Hôpital's Rule on the indeterminate form $\left[\frac{\infty}{\infty}\right]$ or by the elementary inequality $e^x > 1 + x + \frac{x^2}{2}$ for $x > 0$.
4. **Interaction Between Monotonicity, Asymptotes, and Curvature**:
   When a smooth function attains a positive maximum at $x = x_0$, decreases for $x > x_0$, remains strictly positive, and approaches a horizontal asymptote $y = 0$ as $x \to +\infty$, its graph cannot remain concave down forever—it must switch from concave ($f''(x) < 0$) near the peak to convex ($f''(x) > 0$) for large $x$, producing an inflection point on $(x_0, \infty)$.

## Detailed Step-by-Step Solution

### Step 1: Domain, Sign, and Intercept

- **Domain**: $D_f = \mathbb{R} = (-\infty, \infty)$.
- **Zero and $y$-Intercept**: Since $e^{-x} > 0$ for all $x \in \mathbb{R}$,
  $$f(x) = xe^{-x} = 0 \iff x = 0.$$
  Thus, $(0, 0)$ is the unique zero and $y$-intercept. Moreover, $f(x) < 0$ for $x \in (-\infty, 0)$ and $f(x) > 0$ for $x \in (0, \infty)$.

### Step 2: First Derivative, Monotonicity, and Extrema

Applying the product rule and chain rule to $f(x) = x \cdot e^{-x}$:
$$f'(x) = (x)' e^{-x} + x \left(e^{-x}\right)' = 1 \cdot e^{-x} + x \left(-e^{-x}\right) = (1 - x)e^{-x}.$$

1. **Critical Points**:
   Setting $f'(x) = 0$:
   $$(1 - x)e^{-x} = 0 \iff 1 - x = 0 \iff x = 1,$$
   because $e^{-x} > 0$ for all $x \in \mathbb{R}$. Thus, $x = 1$ is the unique critical point.
2. **Sign Chart of $f'(x)$ and Monotonicity**:
   Since $e^{-x} > 0$ on $\mathbb{R}$, the sign of $f'(x)$ is identical to the sign of $1 - x$:
   - On $(-\infty, 1)$: $1 - x > 0 \implies f'(x) > 0$, so $f$ is **strictly increasing** on $(-\infty, 1]$.
   - On $(1, \infty)$: $1 - x < 0 \implies f'(x) < 0$, so $f$ is **strictly decreasing** on $[1, \infty)$.

   | Interval / Point | $(-\infty, 1)$ | $x = 1$ | $(1, \infty)$ |
   | :---: | :---: | :---: | :---: |
   | Sign of $1 - x$ | $+$ | $0$ | $-$ |
   | Sign of $e^{-x}$ | $+$ | $+$ | $+$ |
   | Sign of $f'(x) = (1 - x)e^{-x}$ | $+$ | $0$ | $-$ |
   | Behavior of $f(x)$ | $\nearrow$ (strictly increasing) | **Global Max** $f(1) = \frac{1}{e}$ | $\searrow$ (strictly decreasing) |

3. **Local and Global Extrema**:
   At $x = 1$, $f'(x)$ changes sign from positive to negative, so $f$ has a **strict local maximum** at $x = 1$:
   $$f(1) = 1 \cdot e^{-1} = \frac{1}{e} \approx 0.3679.$$
   Because $f$ is strictly increasing for all $x \le 1$ and strictly decreasing for all $x \ge 1$, $f(1) = \frac{1}{e}$ is also the **strict global maximum** of $f$ on $\mathbb{R}$. There is no local or global minimum.

### Step 3: Limits at Infinity and Right-Hand Behavior

1. **Behavior as $x \to +\infty$**:
   We rewrite $f(x)$ as a quotient to make the competition between $x$ and $e^x$ explicit:
   $$\lim_{x \to \infty} xe^{-x} = \lim_{x \to \infty} \frac{x}{e^x}.$$
   This is an indeterminate form of type $\left[\frac{\infty}{\infty}\right]$. Applying L'Hôpital's Rule (or using $e^x > 1 + x + \frac{x^2}{2}$ for $x > 0$, which gives $0 < \frac{x}{e^x} < \frac{2}{x}$ and applying the Squeeze Theorem):
   $$\lim_{x \to \infty} \frac{x}{e^x} = \lim_{x \to \infty} \frac{(x)'}{(e^x)'} = \lim_{x \to \infty} \frac{1}{e^x} = 0^+.$$
   Therefore, the line **$y = 0$ (the positive $x$-axis) is a horizontal asymptote as $x \to +\infty$**, approached from above.

2. **Behavior as $x \to -\infty$**:
   As $x \to -\infty$, we have $x \to -\infty$ and $-x \to +\infty \implies e^{-x} \to +\infty$. This is a determinate product $[-\infty \cdot (+\infty)]$:
   $$\lim_{x \to -\infty} xe^{-x} = -\infty.$$
   There is no horizontal or oblique asymptote as $x \to -\infty$ (since $\lim_{x \to -\infty} \frac{f(x)}{x} = \lim_{x \to -\infty} e^{-x} = +\infty$).

3. **How the Limit as $x \to \infty$ Affects the Shape of the Graph on the Right-Hand Side**:
   - For $x > 1$, $f(x)$ decreases strictly from its peak value $f(1) = \frac{1}{e} \approx 0.368$, yet because $x > 0$ and $e^{-x} > 0$, the graph **never crosses the $x$-axis** for $x > 0$.
   - Instead, the limit $\lim_{x \to \infty} f(x) = 0^+$ forces the graph to flatten out and hug the positive $x$-axis from above as a horizontal asymptote.
   - Furthermore, this asymptotic flattening requires the curvature to change from concave (bending downward at the peak $x = 1$) to convex (bending upward to level off along $y = 0$). Indeed, differentiating a second time:
     $$f''(x) = \left((1 - x)e^{-x}\right)' = -e^{-x} - (1 - x)e^{-x} = (x - 2)e^{-x}.$$
     We see that $f''(x) < 0$ on $(-\infty, 2)$ (concave), $f''(x) > 0$ on $(2, \infty)$ (convex), and $f$ has an **inflection point at $\left(2, \frac{2}{e^2}\right) \approx (2, 0.2707)$** where the downward slope is steepest ($f'(2) = -e^{-2}$) before leveling off toward $y = 0$.

### Step 4: Structured Summary of Features and Graph Sketch

- **Domain**: $\mathbb{R}$
- **Zero / Intercept**: $(0, 0)$ ($f(x) < 0$ on $(-\infty, 0)$, $f(x) > 0$ on $(0, \infty)$)
- **Monotonicity**: Strictly increasing on $(-\infty, 1]$, strictly decreasing on $[1, \infty)$
- **Global Maximum**: $\left(1, \frac{1}{e}\right) \approx (1, 0.368)$
- **Inflection Point**: $\left(2, \frac{2}{e^2}\right) \approx (2, 0.271)$ (concave on $(-\infty, 2)$, convex on $(2, \infty)$)
- **Horizontal Asymptote**: $y = 0$ as $x \to +\infty$ ($\lim_{x \to -\infty} f(x) = -\infty$)

```text
                y
                ^
                |        Local/Global Max
          0.37  + . . . . . * (1, 1/e)
                |         / : \
          0.27  + . . . ./. : . * (2, 2/e^2)  <-- Inflection Point
                |       /   :   : \
                |      /    :   :   \__
                |     /     :   :       \____       y = 0 (Horizontal Asymptote)
  --------------+----*------+---+-------------\_______________________> x
         -1     |   0       1   2       3       4       5       6
               /| (0,0)
              / |
             /  |
            /  -1 +
           /    |
          * (-1, -e)
         /      |
```

## Verification and Consistency Checks

1. **Test Points Across the Intervals**:
   - At $x = 0 \in (-\infty, 1)$: $f'(0) = (1 - 0)e^0 = 1 > 0$ (increasing), and $f(0) = 0 < \frac{1}{e} = f(1)$.
   - At $x = 2 \in (1, \infty)$: $f'(2) = (1 - 2)e^{-2} = -\frac{1}{e^2} \approx -0.135 < 0$ (decreasing), and $f(2) = \frac{2}{e^2} \approx 0.2707 < 0.3679 \approx \frac{1}{e}$.
   - At $x = 4 \in (1, \infty)$: $f(4) = \frac{4}{e^4} \approx 0.0733$, and at $x = 10$: $f(10) = \frac{10}{e^{10}} \approx 0.000454$, confirming rapid positive decay toward $y = 0$ as $x \to +\infty$.
2. **Elementary Inequality Check for the Global Maximum**:
   Using the classic inequality $e^t \ge 1 + t$ for all $t \in \mathbb{R}$ (with equality if and only if $t = 0$) and substituting $t = x - 1$:
   $$e^{x - 1} \ge x \quad \text{for all } x \in \mathbb{R}.$$
   Multiplying both sides by the positive quantity $e^{-x} > 0$ yields
   $$e^{-1} \ge xe^{-x} \iff f(x) \le \frac{1}{e} \quad \text{for all } x \in \mathbb{R},$$
   with equality if and only if $x = 1$. This independently confirms that $\left(1, \frac{1}{e}\right)$ is the unique global maximum.
