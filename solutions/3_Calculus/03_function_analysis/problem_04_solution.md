# Problem 4: A Function with Two Vertical Asymptotes

## Problem Statement

Analyze
$$f(x)=\frac1{x^2-1}.$$
Determine the domain, asymptotes, sign, and monotonicity on the intervals of the domain. Explain why each interval must be analyzed separately.

## Theoretical Background and Concepts

When analyzing a rational function whose denominator has multiple distinct real zeros, several theoretical principles must be applied carefully:

1. **Connected Components of the Domain**: If the denominator $Q(x)$ has roots $a_1 < a_2 < \dots < a_k$, the domain $D_f = \mathbb{R} \setminus \{a_1, \dots, a_k\}$ splits into $k + 1$ disjoint open intervals: $(-\infty, a_1)$, $(a_1, a_2)$, $\dots$, $(a_k, \infty)$.
2. **Why Monotonicity Must Be Analyzed on Each Interval Separately**:
   - The standard theorem linking the sign of $f'$ to monotonicity ($f'(x) > 0 \implies f$ is strictly increasing; $f'(x) < 0 \implies f$ is strictly decreasing) is a direct corollary of **Lagrange's Mean Value Theorem**: for $x_1 < x_2$,
     $$f(x_2) - f(x_1) = f'(c)(x_2 - x_1) \quad \text{for some } c \in (x_1, x_2).$$
   - The Mean Value Theorem **requires $f$ to be continuous on the entire closed interval $[x_1, x_2]$ and differentiable on $(x_1, x_2)$**.
   - If $x_1$ and $x_2$ lie in **different** intervals of the domain (separated by a point of discontinuity/vertical asymptote), $[x_1, x_2]$ is not contained in $D_f$, the Mean Value Theorem does not apply, and the inequality $f(x_1) < f(x_2)$ (or $f(x_1) > f(x_2)$) can fail completely across the asymptote even when $f'$ has the same sign on both intervals.
3. **Symmetry, Asymptotes, and Curvature**:
   - If $f(-x) = f(x)$ for all $x \in D_f$, then $f$ is **even** and its graph is symmetric across the $y$-axis; consequently, its derivative $f'(-x) = -f'(x)$ is **odd**.
   - One-sided limits at each excluded point determine the behavior along the vertical asymptotes, while limits as $x \to \pm\infty$ identify horizontal asymptotes.
   - The second derivative $f''(x)$ determines whether each branch is convex ($f''(x) > 0$) or concave ($f''(x) < 0$).

## Detailed Step-by-Step Solution

### Step 1: Domain, Symmetry, and Intercepts

1. **Domain**: The denominator vanishes when
   $$x^2 - 1 = 0 \iff (x + 1)(x - 1) = 0 \iff x = -1 \quad \text{or} \quad x = 1.$$
   Thus, the domain consists of **three disjoint open intervals**:
   $$D_f = \mathbb{R} \setminus \{-1, 1\} = (-\infty, -1) \cup (-1, 1) \cup (1, \infty).$$
2. **Symmetry**: For every $x \in D_f$, we also have $-x \in D_f$ and
   $$f(-x) = \frac{1}{(-x)^2 - 1} = \frac{1}{x^2 - 1} = f(x).$$
   Therefore, $f$ is an **even function** (symmetric about the $y$-axis).
3. **Zeros and $y$-Intercept**:
   - Since the numerator is the constant $1 \neq 0$, $f(x) = 0$ has no solutions; $f$ has **no zeros** ($x$-intercepts).
   - At $x = 0 \in (-1, 1)$, $f(0) = \frac{1}{0^2 - 1} = -1$, so the **$y$-intercept is $(0, -1)$**.

### Step 2: Sign of $f(x)$ on the Intervals of the Domain

Since the numerator $1 > 0$ is always positive, the sign of $f(x) = \frac{1}{(x + 1)(x - 1)}$ coincides with the sign of the quadratic $x^2 - 1 = (x + 1)(x - 1)$:
- On $(-\infty, -1)$: $|x| > 1 \implies x^2 - 1 > 0 \implies f(x) > 0$.
- On $(-1, 1)$: $|x| < 1 \implies x^2 - 1 < 0 \implies f(x) < 0$.
- On $(1, \infty)$: $|x| > 1 \implies x^2 - 1 > 0 \implies f(x) > 0$.

### Step 3: Limits and Asymptotes

1. **Vertical Asymptote at $x = -1$**:
   - As $x \to -1^-$, $x + 1 \to 0^-$ and $x - 1 \to -2 < 0$, so $(x + 1)(x - 1) \to 0^+$:
     $$\lim_{x \to -1^-} \frac{1}{(x + 1)(x - 1)} = \left[\frac{1}{0^- \cdot (-2)}\right] = \left[\frac{1}{0^+}\right] = +\infty.$$
   - As $x \to -1^+$, $x + 1 \to 0^+$ and $x - 1 \to -2 < 0$, so $(x + 1)(x - 1) \to 0^-$:
     $$\lim_{x \to -1^+} \frac{1}{(x + 1)(x - 1)} = \left[\frac{1}{0^+ \cdot (-2)}\right] = \left[\frac{1}{0^-}\right] = -\infty.$$
   Thus, **$x = -1$ is a two-sided vertical asymptote**.

2. **Vertical Asymptote at $x = 1$**:
   - As $x \to 1^-$, $x + 1 \to 2 > 0$ and $x - 1 \to 0^-$, so $(x + 1)(x - 1) \to 0^-$:
     $$\lim_{x \to 1^-} \frac{1}{(x + 1)(x - 1)} = \left[\frac{1}{2 \cdot 0^-}\right] = \left[\frac{1}{0^-}\right] = -\infty.$$
   - As $x \to 1^+$, $x + 1 \to 2 > 0$ and $x - 1 \to 0^+$, so $(x + 1)(x - 1) \to 0^+$:
     $$\lim_{x \to 1^+} \frac{1}{(x + 1)(x - 1)} = \left[\frac{1}{2 \cdot 0^+}\right] = \left[\frac{1}{0^+}\right] = +\infty.$$
   Thus, **$x = 1$ is a two-sided vertical asymptote**.

3. **Horizontal Asymptote as $x \to \pm\infty$**:
   $$\lim_{x \to -\infty} \frac{1}{x^2 - 1} = 0^+, \qquad \lim_{x \to +\infty} \frac{1}{x^2 - 1} = 0^+.$$
   Thus, **$y = 0$ (the $x$-axis) is a two-sided horizontal asymptote**, approached from above on both ends.

### Step 4: First Derivative, Monotonicity, and Extrema

Writing $f(x) = (x^2 - 1)^{-1}$ and differentiating via the chain rule:
$$f'(x) = -1 \cdot (x^2 - 1)^{-2} \cdot (2x) = -\frac{2x}{(x^2 - 1)^2}.$$
- **Critical point**: For $x \in D_f$, $f'(x) = 0 \iff -2x = 0 \iff x = 0$.
- **Sign of $f'(x)$**: Since $(x^2 - 1)^2 > 0$ for all $x \in D_f$, the sign of $f'(x)$ is determined by $-2x$:
  - For $x < 0$ ($x \neq -1$), $-2x > 0 \implies f'(x) > 0$.
  - For $x > 0$ ($x \neq 1$), $-2x < 0 \implies f'(x) < 0$.
- **Second Derivative and Curvature**:
  $$f''(x) = -\frac{2(x^2 - 1)^2 - 2x \cdot 2(x^2 - 1)(2x)}{(x^2 - 1)^4} = \frac{2(3x^2 + 1)}{(x^2 - 1)^3}.$$
  Since $2(3x^2 + 1) > 0$ everywhere, the sign of $f''(x)$ matches the sign of $x^2 - 1$: $f$ is **convex** on $(-\infty, -1)$ and $(1, \infty)$, and **concave** on $(-1, 1)$, with no inflection points.

We summarize the sign of $f(x)$, $f'(x)$, and $f''(x)$ across all intervals:

| Interval / Point | $(-\infty, -1)$ | $x = -1$ | $(-1, 0)$ | $x = 0$ | $(0, 1)$ | $x = 1$ | $(1, \infty)$ |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Sign of $f(x)$ | $+$ | undef. | $-$ | $-1$ | $-$ | undef. | $+$ |
| Sign of $f'(x)$ | $+$ | undef. | $+$ | $0$ | $-$ | undef. | $-$ |
| Sign of $f''(x)$ | $+$ | undef. | $-$ | $-2$ | $-$ | undef. | $+$ |
| Behavior of $f(x)$ | $\nearrow$ ($0^+$ to $+\infty$) | **V.A.** | $\nearrow$ ($-\infty$ to $-1$) | **Local Max** $f(0)=-1$ | $\searrow$ ($-1$ to $-\infty$) | **V.A.** | $\searrow$ ($+\infty$ to $0^+$) |

**Monotonicity and Extrema on the Intervals of the Domain**:
1. On $(-\infty, -1)$: $f'(x) > 0$, so $f$ is **strictly increasing** from $0^+$ to $+\infty$.
2. On $(-1, 1)$:
   - On $(-1, 0]$, $f'(x) \ge 0$ (with $f'(x) > 0$ on $(-1, 0)$), so $f$ is **strictly increasing** from $-\infty$ to $-1$.
   - At $x = 0$, $f'(x)$ changes sign from $+$ to $-$, so $f$ attains a **local maximum** of $f(0) = -1$ at $(0, -1)$.
   - On $[0, 1)$, $f'(x) \le 0$ (with $f'(x) < 0$ on $(0, 1)$), so $f$ is **strictly decreasing** from $-1$ to $-\infty$.
3. On $(1, \infty)$: $f'(x) < 0$, so $f$ is **strictly decreasing** from $+\infty$ to $0^+$.

### Step 5: Why Each Interval Must Be Analyzed Separately

Observe that $f'(x) > 0$ on both $(-\infty, -1)$ and $(-1, 0)$. However, $f$ is **not** increasing on the union $(-\infty, -1) \cup (-1, 0]$!
- If we take $x_1 = -2 \in (-\infty, -1)$ and $x_2 = -\frac{1}{2} \in (-1, 0)$, then $x_1 < x_2$, yet
  $$f(-2) = \frac{1}{(-2)^2 - 1} = \frac{1}{3} > -\frac{4}{3} = \frac{1}{\left(-\frac{1}{2}\right)^2 - 1} = f\left(-\frac{1}{2}\right).$$
- Similarly, $f'(x) < 0$ on both $(0, 1)$ and $(1, \infty)$, yet for $x_1 = \frac{1}{2} < 2 = x_2$, we have $f\left(\frac{1}{2}\right) = -\frac{4}{3} < \frac{1}{3} = f(2)$.

**Reason**: Lagrange's Mean Value Theorem guarantees that $f'(x) > 0 \implies f(x_1) < f(x_2)$ only when $f$ is continuous on the entire closed segment $[x_1, x_2]$. Because $x = -1$ and $x = 1$ are vertical asymptotes where $f$ is undefined and jumps from $+\infty$ to $-\infty$ (or $-\infty$ to $+\infty$), the intervals $(-\infty, -1)$, $(-1, 1)$, and $(1, \infty)$ are disconnected components of $D_f$ and must be analyzed individually.

### Step 6: Structured Summary of Features and Graph Sketch

- **Domain**: $(-\infty, -1) \cup (-1, 1) \cup (1, \infty)$
- **Symmetry**: Even function ($f(-x) = f(x)$)
- **Vertical Asymptotes**: $x = -1$ and $x = 1$
- **Horizontal Asymptote**: $y = 0$
- **Local Extremum**: Local maximum at $(0, -1)$
- **Monotonicity**: Strictly increasing on $(-\infty, -1)$ and $(-1, 0]$; strictly decreasing on $[0, 1)$ and $(1, \infty)$

```text
                      y
                      ^
                    3 +          | :       |       : |
                      |          | :       |       : |
                    2 +          | :       |       : |
                      |         /  :       |       :  \
                    1 +        /   :       |       :   \
                      |      /     :       |       :     \
         _____________     /       :       |       :       \     _____________
  --------------------+---+--------+-------+-------+--------+---+------------> x
             -3      -2           -1       0       1            2       3
                                   :     (0,-1)    :
                   -1 +            :   _ . * . _   :
                      |            :  /    |    \  :
                   -2 +            : |     |     | :
                      |            : |     |     | :
                   -3 +            : |     |     | :
                                  x = -1          x = 1
```

## Verification and Consistency Checks

1. **Even Symmetry Check**:
   - $f(-2) = \frac{1}{3} = f(2)$, and $f'(-2) = \frac{4}{9} = -f'(2)$.
   - $f\left(-\frac{1}{2}\right) = -\frac{4}{3} = f\left(\frac{1}{2}\right)$, and $f'\left(-\frac{1}{2}\right) = \frac{16}{9} = -f'\left(\frac{1}{2}\right)$.
2. **Range and Bound Check on Each Branch**:
   - On $(-\infty, -1)$ and $(1, \infty)$, $x^2 - 1$ takes all values in $(0, \infty)$, so $f(x) = \frac{1}{x^2 - 1}$ takes all values in $(0, \infty)$.
   - On $(-1, 1)$, $0 \le x^2 < 1 \implies -1 \le x^2 - 1 < 0 \implies f(x) = \frac{1}{x^2 - 1} \le -1$, confirming that $f(0) = -1$ is the maximum value on the middle branch $(-1, 1)$ and that the range of $f$ is $(-\infty, -1] \cup (0, \infty)$.
