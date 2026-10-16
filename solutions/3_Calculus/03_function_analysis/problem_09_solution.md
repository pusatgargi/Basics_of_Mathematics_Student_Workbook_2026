# Problem 9: An Oblique Asymptote

## Problem Statement

Analyze the asymptotes of
$$f(x)=\frac{x^2+1}{x-1}.$$
Perform polynomial division and explain why the remainder term vanishes for large $|x|$.

## Theoretical Background and Concepts

A rational function $f(x) = \frac{P(x)}{Q(x)}$ (in lowest terms) exhibits different asymptotic behaviors depending on its denominator and the degrees of $P$ and $Q$:

1. **Vertical Asymptotes**: If $Q(x_0) = 0$ and $P(x_0) \neq 0$, then $\lim_{x \to x_0^\pm} f(x) = \pm\infty$, and the vertical line $x = x_0$ is a vertical asymptote.
2. **Oblique (Slant) Asymptotes**:
   - A line $y = mx + b$ is an **oblique asymptote** of $f$ as $x \to +\infty$ (or $x \to -\infty$) if
     $$\lim_{x \to \pm\infty} \left[f(x) - (mx + b)\right] = 0.$$
   - Geometrically, this means the vertical distance $|f(x) - (mx + b)|$ between the graph of $f$ and the line $y = mx + b$ shrinks to zero as $|x|$ grows without bound.
3. **Polynomial Division and Remainder Decomposition**:
   - Whenever $\deg P = \deg Q + 1$, dividing $P(x)$ by $Q(x)$ yields a linear quotient $mx + b$ and a remainder $R(x)$ with $\deg R < \deg Q$:
     $$f(x) = \frac{P(x)}{Q(x)} = mx + b + \frac{R(x)}{Q(x)}.$$
   - Because $\deg R < \deg Q$, the proper rational remainder term $\frac{R(x)}{Q(x)}$ satisfies $\lim_{x \to \pm\infty} \frac{R(x)}{Q(x)} = 0$, immediately revealing the oblique asymptote $y = mx + b$ as well as whether the graph approaches the asymptote from above ($\frac{R(x)}{Q(x)} > 0$) or from below ($\frac{R(x)}{Q(x)} < 0$).
4. **General Limit Formulas for $m$ and $b$**:
   Even without polynomial division, the slope and intercept of an asymptote $y = mx + b$ are given by:
   $$m = \lim_{x \to \pm\infty} \frac{f(x)}{x}, \qquad b = \lim_{x \to \pm\infty} \left(f(x) - mx\right).$$

## Detailed Step-by-Step Solution

### Step 1: Domain

The denominator vanishes at $x - 1 = 0 \iff x = 1$. Since the numerator $x^2 + 1 \ge 1 > 0$ never vanishes, the fraction is irreducible and the domain is:
$$D_f = \mathbb{R} \setminus \{1\} = (-\infty, 1) \cup (1, \infty).$$

### Step 2: Polynomial Division and Decomposition

We divide the numerator $P(x) = x^2 + 1$ by the denominator $Q(x) = x - 1$. Using the algebraic identity $x^2 - 1 = (x - 1)(x + 1)$:
$$x^2 + 1 = (x^2 - 1) + 2 = (x - 1)(x + 1) + 2.$$
Dividing both sides by $x - 1$ (for $x \neq 1$) gives the exact decomposition:
$$f(x) = \frac{(x - 1)(x + 1) + 2}{x - 1} = \underbrace{x + 1}_{\text{linear part}} + \underbrace{\frac{2}{x - 1}}_{\text{remainder term}}.$$
*(Equivalently, via long division: $x^2 \div x = x$, subtracting $x(x - 1) = x^2 - x$ leaves $x + 1$; then $(x + 1) \div x = 1$, subtracting $1(x - 1) = x - 1$ leaves the constant remainder $2$.)*

### Step 3: Vertical Asymptote at $x = 1$

We examine the one-sided limits of $f(x)$ at the excluded point $x = 1$:
- **Left-hand limit ($x \to 1^-$)**: As $x \to 1^-$, we have $x < 1$, so $x - 1 \to 0^-$ while $x^2 + 1 \to 2 > 0$:
  $$\lim_{x \to 1^-} \frac{x^2 + 1}{x - 1} = \left[\frac{2}{0^-}\right] = -\infty.$$
- **Right-hand limit ($x \to 1^+$)**: As $x \to 1^+$, we have $x > 1$, so $x - 1 \to 0^+$ while $x^2 + 1 \to 2 > 0$:
  $$\lim_{x \to 1^+} \frac{x^2 + 1}{x - 1} = \left[\frac{2}{0^+}\right] = +\infty.$$

Therefore, the vertical line **$x = 1$ is a two-sided vertical asymptote**.

### Step 4: Oblique Asymptote and Why the Remainder Term Vanishes

1. **Absence of Horizontal Asymptotes**:
   Since $\deg(x^2 + 1) = 2 > 1 = \deg(x - 1)$,
   $$\lim_{x \to -\infty} f(x) = \lim_{x \to -\infty} \left(x + 1 + \frac{2}{x - 1}\right) = -\infty, \qquad \lim_{x \to +\infty} f(x) = \lim_{x \to +\infty} \left(x + 1 + \frac{2}{x - 1}\right) = +\infty.$$
   Thus, $f$ has **no horizontal asymptotes**.

2. **Why the Remainder Term $\frac{2}{x - 1}$ Vanishes for Large $|x|$**:
   In the remainder term $r(x) = \frac{2}{x - 1}$, the numerator is the fixed constant $2$ (degree $0$), whereas the denominator $x - 1$ grows unboundedly in magnitude as $|x| \to \infty$ (degree $1$). By the reverse triangle inequality, for $|x| > 1$:
   $$0 < \left|\frac{2}{x - 1}\right| = \frac{2}{|x - 1|} \le \frac{2}{|x| - 1}.$$
   As $|x| \to \infty$, $|x| - 1 \to +\infty$, so a constant divided by an arbitrarily large number approaches $0$:
   $$\lim_{x \to -\infty} \frac{2}{x - 1} = 0 \qquad \text{and} \qquad \lim_{x \to +\infty} \frac{2}{x - 1} = 0.$$

3. **Conclusion for the Oblique Asymptote**:
   Because $f(x) - (x + 1) = \frac{2}{x - 1}$, we have:
   $$\lim_{x \to \pm\infty} \left[f(x) - (x + 1)\right] = \lim_{x \to \pm\infty} \frac{2}{x - 1} = 0.$$
   Therefore, the line **$y = x + 1$ is a two-sided oblique asymptote** as $x \to -\infty$ and as $x \to +\infty$.
   Moreover, the sign of the remainder $\frac{2}{x - 1}$ tells us how the graph approaches $y = x + 1$:
   - For $x > 1$ (including $x \to +\infty$), $\frac{2}{x - 1} > 0 \implies f(x) > x + 1$, so the graph lies **strictly above** the oblique asymptote.
   - For $x < 1$ (including $x \to -\infty$), $\frac{2}{x - 1} < 0 \implies f(x) < x + 1$, so the graph lies **strictly below** the oblique asymptote.

### Step 5: Supporting Derivative Summary and Asymptotic Sketch

Differentiating the decomposed form $f(x) = x + 1 + 2(x - 1)^{-1}$ gives:
$$f'(x) = 1 - \frac{2}{(x - 1)^2} = \frac{(x - 1)^2 - 2}{(x - 1)^2} = \frac{\left(x - 1 - \sqrt{2}\right)\left(x - 1 + \sqrt{2}\right)}{(x - 1)^2}.$$
- Local maximum on $(-\infty, 1)$ at $x = 1 - \sqrt{2} \approx -0.414$, where $f(1 - \sqrt{2}) = 2 - 2\sqrt{2} \approx -0.828$.
- Local minimum on $(1, \infty)$ at $x = 1 + \sqrt{2} \approx 2.414$, where $f(1 + \sqrt{2}) = 2 + 2\sqrt{2} \approx 4.828$.

```text
                        y
                        ^
                      7 +             :           . '
                        |             :   |   . '   /  <-- y = x + 1
                      6 +             :   | .     /
                        |             :    \    /
                      5 +             :     * -' (1+sqrt(2), 2+2sqrt(2))
                        |             :   . '    Local Min
                      4 +             : . '
                        |             :'
                      2 +           . :
                        |         . ' :
  ----------------------+-----. '-----+---+-----------------------> x
             -2        -1 . '*        1   2       3       4
                     . '|-0.83\       :
                 . '    *      \      :
             . '  /    /        |     :
         . '    /     /         |     :
       '      /                 |     :
                                     x = 1
```

## Verification and Consistency Checks

1. **Verification via General Cauchy Limit Formulas**:
   $$m = \lim_{x \to \pm\infty} \frac{f(x)}{x} = \lim_{x \to \pm\infty} \frac{x^2 + 1}{x^2 - x} = \lim_{x \to \pm\infty} \frac{1 + \frac{1}{x^2}}{1 - \frac{1}{x}} = 1,$$
   $$b = \lim_{x \to \pm\infty} \left(f(x) - 1\cdot x\right) = \lim_{x \to \pm\infty} \left(\frac{x^2 + 1 - x(x - 1)}{x - 1}\right) = \lim_{x \to \pm\infty} \frac{x + 1}{x - 1} = 1.$$
   This independently confirms the oblique asymptote $y = x + 1$.
2. **Numerical Convergence Check for Large $|x|$**:
   - At $x = 11$: $f(11) = \frac{122}{10} = 12.2$, while $y_{\text{asymp}}(11) = 11 + 1 = 12$. The difference is $\frac{2}{10} = 0.2 > 0$.
   - At $x = 101$: $f(101) = \frac{10202}{100} = 102.02$, while $y_{\text{asymp}}(101) = 102$. The difference is $\frac{2}{100} = 0.02 > 0$.
   - At $x = -99$: $f(-99) = \frac{9802}{-100} = -98.02$, while $y_{\text{asymp}}(-99) = -98$. The difference is $\frac{2}{-100} = -0.02 < 0$.
   In both directions, $f(x)$ converges rapidly to $x + 1$.
