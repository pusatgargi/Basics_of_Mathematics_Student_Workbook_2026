# Problem 10: Complete Function Analysis

## Problem Statement

Perform a complete analysis of
$$f(x)=\frac{x}{x^2+1}.$$
Include the domain, symmetry, zeros, limits, monotonicity, extrema, and convexity. Finally, produce a sketch based only on this information.

## Theoretical Background and Concepts

A complete function analysis synthesizes algebraic, asymptotic, and differential properties into a unified portrait of a function $f$:

1. **Domain and Continuity**: Determine where $f(x)$ is defined and continuous. For a rational function $\frac{P(x)}{Q(x)}$ whose denominator $Q(x)$ never vanishes on $\mathbb{R}$, the domain is all of $\mathbb{R}$ and there are no vertical asymptotes.
2. **Symmetry (Parity)**:
   - $f$ is **even** if $f(-x) = f(x)$ (symmetric across the $y$-axis).
   - $f$ is **odd** if $f(-x) = -f(x)$ (point-symmetric about the origin $(0, 0)$). For an odd twice-differentiable function, $f'$ is even and $f''$ is odd, so extrema and inflection points occur in symmetric pairs $(x_0, f(x_0))$ and $(-x_0, -f(x_0))$.
3. **Zeros, Sign, and Asymptotes**: Zeros mark where the graph crosses the $x$-axis; limits as $x \to \pm\infty$ determine horizontal or oblique asymptotes.
4. **First Derivative ($f'$)**: Identifies critical points ($f'(x) = 0$), intervals of strict increase ($f'(x) > 0$) and strict decrease ($f'(x) < 0$), and local/global extrema.
5. **Second Derivative ($f''$)**: Identifies intervals of strict convexity ($f''(x) > 0$, $\cup$) and strict concavity ($f''(x) < 0$, $\cap$), as well as inflection points where $f''$ changes sign.

## Detailed Step-by-Step Solution

### Step 1: Domain and Continuity

Since $x^2 \ge 0$ for all $x \in \mathbb{R}$, the denominator satisfies $x^2 + 1 \ge 1 > 0$ and never vanishes. Therefore:
$$D_f = \mathbb{R} = (-\infty, \infty),$$
and $f$ is continuous and infinitely differentiable on all of $\mathbb{R}$.

### Step 2: Symmetry (Parity)

For every $x \in \mathbb{R}$, we have $-x \in \mathbb{R}$ and:
$$f(-x) = \frac{-x}{(-x)^2 + 1} = -\frac{x}{x^2 + 1} = -f(x).$$
Thus, $f$ is an **odd function**, and its graph is symmetric with respect to the origin $(0, 0)$.

### Step 3: Zeros and Sign of $f(x)$

- **Zero and $y$-intercept**:
  $$f(x) = 0 \iff \frac{x}{x^2 + 1} = 0 \iff x = 0.$$
  Thus, $(0, 0)$ is the unique $x$-intercept and $y$-intercept.
- **Sign of $f(x)$**: Since $x^2 + 1 > 0$ everywhere, the sign of $f(x)$ matches the sign of $x$:
  - $f(x) < 0$ on $(-\infty, 0)$,
  - $f(x) > 0$ on $(0, \infty)$.

### Step 4: Limits and Asymptotes

- **Vertical Asymptotes**: None, because $D_f = \mathbb{R}$ and $f$ is continuous everywhere.
- **Horizontal Asymptote (Limits as $x \to \pm\infty$)**:
  Dividing numerator and denominator by $x^2$ for $x \neq 0$:
  $$\lim_{x \to -\infty} \frac{x}{x^2 + 1} = \lim_{x \to -\infty} \frac{\frac{1}{x}}{1 + \frac{1}{x^2}} = \frac{0}{1 + 0} = 0^-,$$
  $$\lim_{x \to +\infty} \frac{x}{x^2 + 1} = \lim_{x \to +\infty} \frac{\frac{1}{x}}{1 + \frac{1}{x^2}} = \frac{0}{1 + 0} = 0^+.$$
  Hence, **$y = 0$ (the $x$-axis) is a two-sided horizontal asymptote**, approached from below as $x \to -\infty$ and from above as $x \to +\infty$.

### Step 5: First Derivative, Monotonicity, and Extrema

Applying the quotient rule to $f(x) = \frac{x}{x^2 + 1}$:
$$f'(x) = \frac{1 \cdot (x^2 + 1) - x \cdot (2x)}{(x^2 + 1)^2} = \frac{1 - x^2}{(x^2 + 1)^2} = -\frac{(x - 1)(x + 1)}{(x^2 + 1)^2}.$$

1. **Critical Points**:
   $$f'(x) = 0 \iff 1 - x^2 = 0 \iff x = -1 \quad \text{or} \quad x = 1.$$
2. **Sign of $f'(x)$ and Monotonicity**:
   Because $(x^2 + 1)^2 > 0$ for all $x \in \mathbb{R}$, the sign of $f'(x)$ is determined by the downward-opening quadratic $1 - x^2 = -(x - 1)(x + 1)$:
   - On $(-\infty, -1)$: $1 - x^2 < 0 \implies f'(x) < 0 \implies f$ is **strictly decreasing** on $(-\infty, -1]$.
   - On $(-1, 1)$: $1 - x^2 > 0 \implies f'(x) > 0 \implies f$ is **strictly increasing** on $[-1, 1]$.
   - On $(1, \infty)$: $1 - x^2 < 0 \implies f'(x) < 0 \implies f$ is **strictly decreasing** on $[1, \infty)$.
3. **Local and Global Extrema**:
   - At $x = -1$: $f'(x)$ changes sign from $-$ to $+$, so $f$ has a **local minimum** at $x = -1$:
     $$f(-1) = \frac{-1}{(-1)^2 + 1} = -\frac{1}{2}.$$
     Since $f(x) < 0$ on $(-\infty, 0)$ with $\lim_{x \to -\infty} f(x) = 0$ and $f(x) \ge 0$ on $[0, \infty)$, $f(-1) = -\frac{1}{2}$ is also the **global minimum** on $\mathbb{R}$.
   - At $x = 1$: $f'(x)$ changes sign from $+$ to $-$, so $f$ has a **local and global maximum** at $x = 1$:
     $$f(1) = \frac{1}{1^2 + 1} = \frac{1}{2}.$$
   - The **range (image)** of $f$ is $\left[-\frac{1}{2}, \frac{1}{2}\right]$.

### Step 6: Second Derivative, Convexity/Concavity, and Inflection Points

Differentiating $f'(x) = \frac{1 - x^2}{(x^2 + 1)^2}$ via the quotient rule and factoring out $2x(x^2 + 1)$:
$$f''(x) = \frac{(-2x)(x^2 + 1)^2 - (1 - x^2) \cdot 2(x^2 + 1)(2x)}{(x^2 + 1)^4} = \frac{2x\left[-(x^2 + 1) - 2(1 - x^2)\right]}{(x^2 + 1)^3} = \frac{2x(x^2 - 3)}{(x^2 + 1)^3}.$$
Factoring the numerator completely:
$$f''(x) = \frac{2x\left(x - \sqrt{3}\right)\left(x + \sqrt{3}\right)}{(x^2 + 1)^3}.$$

1. **Candidate Points for Inflection ($f''(x) = 0$)**:
   $$2x\left(x - \sqrt{3}\right)\left(x + \sqrt{3}\right) = 0 \iff x = -\sqrt{3} \approx -1.732, \quad x = 0, \quad \text{or} \quad x = \sqrt{3} \approx 1.732.$$
2. **Sign of $f''(x)$ and Curvature**:
   Since $(x^2 + 1)^3 > 0$ everywhere, the sign of $f''(x)$ matches the cubic $2x(x - \sqrt{3})(x + \sqrt{3})$:
   - On $(-\infty, -\sqrt{3})$: $f''(x) < 0 \implies f$ is **strictly concave** ($\cap$).
   - On $(-\sqrt{3}, 0)$: $f''(x) > 0 \implies f$ is **strictly convex** ($\cup$).
   - On $(0, \sqrt{3})$: $f''(x) < 0 \implies f$ is **strictly concave** ($\cap$).
   - On $(\sqrt{3}, \infty)$: $f''(x) > 0 \implies f$ is **strictly convex** ($\cup$).
3. **Inflection Points**:
   Because $f''(x)$ changes sign across all three roots, $f$ has **three inflection points**:
   $$I_1 = \left(-\sqrt{3}, -\frac{\sqrt{3}}{4}\right) \approx (-1.73, -0.43), \qquad I_2 = (0, 0), \qquad I_3 = \left(\sqrt{3}, \frac{\sqrt{3}}{4}\right) \approx (1.73, 0.43).$$

### Step 7: Combined Master Table and Graph Sketch

| Interval / Point | $(-\infty, -\sqrt{3})$ | $-\sqrt{3}$ | $(-\sqrt{3}, -1)$ | $-1$ | $(-1, 0)$ | $0$ | $(0, 1)$ | $1$ | $(1, \sqrt{3})$ | $\sqrt{3}$ | $(\sqrt{3}, \infty)$ |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| $f'(x)$ | $-$ | $-$ | $-$ | $0$ | $+$ | $+1$ | $+$ | $0$ | $-$ | $-$ | $-$ |
| $f''(x)$ | $-$ | $0$ | $+$ | $+\frac{1}{2}$ | $+$ | $0$ | $-$ | $-\frac{1}{2}$ | $-$ | $0$ | $+$ |
| $f(x)$ | $\searrow \cap$ | **I.P.** $-\frac{\sqrt{3}}{4}$ | $\searrow \cup$ | **Min** $-\frac{1}{2}$ | $\nearrow \cup$ | **I.P. & Zero** $0$ | $\nearrow \cap$ | **Max** $\frac{1}{2}$ | $\searrow \cap$ | **I.P.** $\frac{\sqrt{3}}{4}$ | $\searrow \cup$ |

- **Domain**: $\mathbb{R}$; **Range**: $\left[-\frac{1}{2}, \frac{1}{2}\right]$; **Symmetry**: Odd
- **Horizontal Asymptote**: $y = 0$ as $x \to \pm\infty$
- **Global Minimum**: $\left(-1, -\frac{1}{2}\right)$; **Global Maximum**: $\left(1, \frac{1}{2}\right)$
- **Inflection Points**: $\left(-\sqrt{3}, -\frac{\sqrt{3}}{4}\right)$, $(0, 0)$, and $\left(\sqrt{3}, \frac{\sqrt{3}}{4}\right)$

```text
                            y
                            ^
                            |            Global Max
                      0.50  + . . . . . . . * (1, 1/2)
                            |            /  :  \    Inflection Point I3
                      0.43  +           /   :    * (sqrt(3), sqrt(3)/4)
                            |          /    :   :  \___
                            |         /     :   :       \______     y = 0
  --------------------------+--------*------+---+---------------\---------> x
         -3       -sqrt(3) -1       0       1  sqrt(3)          3
          _______/  :   :     \     | (0,0)
  y = 0          \__:   :      \    |  Inflection Point I2
                    *   :       \   |
      (-sqrt(3), -sqrt(3)/4)     * .+. . . -0.50
      Inflection Point I1    (-1, -1/2)
                             Global Min
```

## Verification and Consistency Checks

1. **Test Points for $f'(x)$ and $f''(x)$**:
   - At $x = 0$: $f'(0) = 1 > 0$ (tangent line at the origin is $y = x$) and $f''(0) = 0$.
   - At $x = \pm 1$: $f'(\pm 1) = 0$, $f''(-1) = \frac{-2(-2)}{2^3} = \frac{1}{2} > 0$ (confirms minimum at $x = -1$), and $f''(1) = -\frac{1}{2} < 0$ (confirms maximum at $x = 1$).
   - At $x = 2 \in (\sqrt{3}, \infty)$: $f(2) = \frac{2}{5} = 0.4$, $f'(2) = -\frac{3}{25} < 0$ (decreasing), and $f''(2) = \frac{4(1)}{125} = \frac{4}{125} > 0$ (convex).
2. **AM-GM Inequality Check on the Global Extrema**:
   By $(|x| - 1)^2 \ge 0$, we have $x^2 + 1 \ge 2|x|$ for all $x \in \mathbb{R}$, with equality if and only if $|x| = 1 \iff x = \pm 1$. Dividing by $2(x^2 + 1) > 0$ yields
   $$|f(x)| = \frac{|x|}{x^2 + 1} \le \frac{1}{2} \iff -\frac{1}{2} \le f(x) \le \frac{1}{2},$$
   independently confirming the global minimum $-\frac{1}{2}$ at $x = -1$ and global maximum $\frac{1}{2}$ at $x = 1$.
