# Problem 13: A Logarithm and an Asymptote

## Problem Statement

Perform a complete analysis of
$$f(x)=\frac{\ln x}{x},\qquad x>0.$$
Find the maximum and the behavior at the ends of the domain. Explain which information is necessary for a correct sketch.

## Theoretical Background and Concepts

Analyzing $f(x) = \frac{\ln x}{x}$ on $(0, \infty)$ combines logarithmic properties, asymptotic growth hierarchies, and first- and second-derivative tests:

1. **Domain and Sign**: The natural logarithm $\ln x$ is defined on $(0, \infty)$, with $\ln x < 0$ on $(0, 1)$, $\ln 1 = 0$, and $\ln x > 0$ on $(1, \infty)$. Since the denominator $x$ is strictly positive on $(0, \infty)$, $f(x) = \frac{\ln x}{x}$ has the exact same sign and zero as $\ln x$.
2. **Behavior at the Ends of the Domain ($x \to 0^+$ and $x \to +\infty$)**:
   - **Near $x = 0^+$**: As $x \to 0^+$, $\ln x \to -\infty$ and $\frac{1}{x} \to +\infty$. This is **not** an indeterminate form; it is a determinate product $[-\infty \cdot (+\infty)] = -\infty$, producing a vertical asymptote at $x = 0$.
   - **As $x \to +\infty$**: Both $\ln x \to +\infty$ and $x \to +\infty$, giving an indeterminate form $\left[\frac{\infty}{\infty}\right]$. By L'Hôpital's Rule (reflecting the fact that $\ln x$ grows much more slowly than any positive power $x^\alpha$), $\lim_{x \to +\infty} \frac{\ln x}{x} = 0^+$, producing a horizontal asymptote $y = 0$.
3. **Why Both Derivatives and Both Limits Are Necessary for a Correct Sketch**:
   - Knowing only the intercept $(1, 0)$ and the maximum $\left(e, \frac{1}{e}\right)$ does not tell us whether $f(x)$ approaches a finite value or $-\infty$ as $x \to 0^+$, nor whether $f(x)$ crosses the $x$-axis again or levels off along $y = 0$ as $x \to +\infty$.
   - Furthermore, the second derivative $f''(x)$ reveals the inflection point at $x = e^{3/2}$, showing where the curve stops bending downward from its peak and starts bending upward to hug the horizontal asymptote $y = 0$.

## Detailed Step-by-Step Solution

### Step 1: Domain, Zero, and Sign of $f(x)$

- **Domain**: By definition of $\ln x$ and the condition $x \neq 0$, the domain is:
  $$D_f = (0, \infty).$$
  The function is continuous and infinitely differentiable on $(0, \infty)$. Since $0 \notin D_f$, there is no $y$-intercept.
- **Zero ($x$-intercept)**:
  $$f(x) = \frac{\ln x}{x} = 0 \iff \ln x = 0 \iff x = 1.$$
  Thus, $(1, 0)$ is the unique $x$-intercept.
- **Sign of $f(x)$**: Because $x > 0$ on $D_f$:
  - On $(0, 1)$: $\ln x < 0 \implies f(x) < 0$.
  - On $(1, \infty)$: $\ln x > 0 \implies f(x) > 0$.

### Step 2: Behavior at the Ends of the Domain (Asymptotes)

1. **Left End of the Domain ($x \to 0^+$, Vertical Asymptote)**:
   Writing $f(x) = \ln x \cdot \frac{1}{x}$, as $x \to 0^+$ we have $\ln x \to -\infty$ and $\frac{1}{x} \to +\infty$:
   $$\lim_{x \to 0^+} \frac{\ln x}{x} = \lim_{x \to 0^+} \left(\ln x \cdot \frac{1}{x}\right) = [-\infty \cdot (+\infty)] = -\infty.$$
   Therefore, the line **$x = 0$ (the $y$-axis) is a vertical asymptote** (specifically, the negative $y$-axis).

2. **Right End of the Domain ($x \to +\infty$, Horizontal Asymptote)**:
   As $x \to +\infty$, $\lim_{x \to +\infty} \frac{\ln x}{x}$ has the indeterminate form $\left[\frac{\infty}{\infty}\right]$. Applying L'Hôpital's Rule:
   $$\lim_{x \to +\infty} \frac{\ln x}{x} = \lim_{x \to +\infty} \frac{(\ln x)'}{(x)'} = \lim_{x \to +\infty} \frac{\frac{1}{x}}{1} = 0^+.$$
   Therefore, the line **$y = 0$ (the positive $x$-axis) is a horizontal asymptote as $x \to +\infty$**, approached from above since $f(x) > 0$ for all $x > 1$.

### Step 3: First Derivative, Monotonicity, and Maximum

Differentiating $f(x) = \frac{\ln x}{x}$ using the quotient rule on $(0, \infty)$:
$$f'(x) = \frac{(\ln x)' \cdot x - \ln x \cdot (x)'}{x^2} = \frac{\frac{1}{x} \cdot x - \ln x \cdot 1}{x^2} = \frac{1 - \ln x}{x^2}.$$

1. **Critical Point**:
   Since $x^2 > 0$ for all $x > 0$:
   $$f'(x) = 0 \iff 1 - \ln x = 0 \iff \ln x = 1 \iff x = e \approx 2.718.$$
2. **Sign of $f'(x)$ and Monotonicity**:
   Because $\ln x$ is strictly increasing on $(0, \infty)$ and $x^2 > 0$:
   - On $(0, e)$: $\ln x < 1 \implies 1 - \ln x > 0 \implies f'(x) > 0$, so $f$ is **strictly increasing** on $(0, e]$.
   - On $(e, \infty)$: $\ln x > 1 \implies 1 - \ln x < 0 \implies f'(x) < 0$, so $f$ is **strictly decreasing** on $[e, \infty)$.
3. **Local and Global Maximum**:
   At $x = e$, $f'(x)$ changes sign from $+$ to $-$, so $f$ attains its **strict local and global maximum** on $(0, \infty)$:
   $$f_{\max} = f(e) = \frac{\ln e}{e} = \frac{1}{e} \approx 0.3679 \implies \left(e, \frac{1}{e}\right).$$
   Combining the global maximum $\frac{1}{e}$ with $\lim_{x \to 0^+} f(x) = -\infty$ and continuity on $(0, \infty)$, the **range** of $f$ is $\left(-\infty, \frac{1}{e}\right]$.

### Step 4: Second Derivative, Convexity/Concavity, and Inflection Point

Differentiating $f'(x) = \frac{1 - \ln x}{x^2}$ via the quotient rule:
$$f''(x) = \frac{\left(-\frac{1}{x}\right)x^2 - (1 - \ln x)(2x)}{x^4} = \frac{-x - 2x + 2x\ln x}{x^4} = \frac{2\ln x - 3}{x^3}.$$

1. **Inflection Point Candidate ($f''(x) = 0$)**:
   $$2\ln x - 3 = 0 \iff \ln x = \frac{3}{2} \iff x = e^{3/2} = e\sqrt{e} \approx 4.4817.$$
2. **Sign of $f''(x)$ and Curvature**:
   Since $x^3 > 0$ on $(0, \infty)$:
   - On $\left(0, e^{3/2}\right)$: $\ln x < \frac{3}{2} \implies f''(x) < 0 \implies f$ is **strictly concave** ($\cap$).
   - On $\left(e^{3/2}, \infty\right)$: $\ln x > \frac{3}{2} \implies f''(x) > 0 \implies f$ is **strictly convex** ($\cup$).
   - At $x = e^{3/2}$, $f''(x)$ changes sign from $-$ to $+$, giving a unique **inflection point**:
     $$I = \left(e^{3/2}, f\left(e^{3/2}\right)\right) = \left(e^{3/2}, \frac{3}{2e^{3/2}}\right) \approx (4.48, 0.335).$$

### Step 5: Master Table, Explanation of Necessary Information, and Sketch

| Interval / Point | $x \to 0^+$ | $(0, 1)$ | $x = 1$ | $(1, e)$ | $x = e$ | $\left(e, e^{3/2}\right)$ | $x = e^{3/2}$ | $\left(e^{3/2}, \infty\right)$ | $x \to \infty$ |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| $f(x)$ | $-\infty$ | $-$ | $0$ | $+$ | $\frac{1}{e}$ | $+$ | $\frac{3}{2e^{3/2}}$ | $+$ | $0^+$ |
| $f'(x)$ | $+\infty$ | $+$ | $+1$ | $+$ | $0$ | $-$ | $-\frac{1}{2e^3}$ | $-$ | $0^-$ |
| $f''(x)$ | $-\infty$ | $-$ | $-3$ | $-$ | $-\frac{1}{e^3}$ | $-$ | $0$ | $+$ | $0^+$ |
| Shape | **V.A.** | $\nearrow \cap$ | **Zero** | $\nearrow \cap$ | **Global Max** | $\searrow \cap$ | **Inflection** | $\searrow \cup$ | **H.A.** |

**Which Information Is Necessary for a Correct Sketch**:
To draw an accurate qualitative and quantitative graph of $f(x) = \frac{\ln x}{x}$, five pieces of information are indispensable:
1. **The domain $(0, \infty)$ and vertical asymptote $\lim_{x \to 0^+} f(x) = -\infty$**, which confine the graph to the right of the $y$-axis and show it plunging steeply downward near $x = 0$.
2. **The unique zero $(1, 0)$** (with slope $f'(1) = 1$), showing where the curve crosses from the fourth quadrant into the first quadrant.
3. **The global maximum at $\left(e, \frac{1}{e}\right)$** and the monotonicity intervals (increasing on $(0, e]$, decreasing on $[e, \infty)$), which determine the single peak of the curve.
4. **The horizontal asymptote $\lim_{x \to \infty} f(x) = 0^+$**, which ensures the decreasing branch for $x > e$ stays positive and approaches the $x$-axis rather than crossing it or diverging to $-\infty$.
5. **The inflection point at $\left(e^{3/2}, \frac{3}{2e^{3/2}}\right)$**, which marks the transition from concave ($\cap$) to convex ($\cup$) required for the curve to level off along $y = 0$.

```text
            y
            ^
      0.37  +                         * (e, 1/e) [Global Max]
            |                     _ - ' \
      0.33  +                    /       * (e^(3/2), 3/(2e^(3/2))) [Inflection Point]
            |                   /         \
      0.20  +                  /           ' - . _
            |                 /                    ' - - . _
      0.10  +                /                               ' - - - - (y -> 0+)
  ----------+---------------*-----------+-----------+-----------+----------> x
            0               1         e=2.72       4.5          8
            | (x -> 0+)    / (1, 0)
            |             /
     -0.50  +            /
            |           /
     -1.00  +          /
            |         /
     -2.00  +        /
            |       |
            |      |
            |      |  (y -> -inf along x = 0)
```

## Verification and Consistency Checks

1. **Test Points Across the Domain**:
   - At $x = \frac{1}{e} \approx 0.368 \in (0, 1)$: $f\left(\frac{1}{e}\right) = -e \approx -2.718 < 0$, and $f'\left(\frac{1}{e}\right) = 2e^2 \approx 14.78 > 0$ (steeply increasing).
   - At $x = 1$: $f(1) = 0$, $f'(1) = 1 > 0$, and $f''(1) = -3 < 0$ (increasing and concave).
   - At $x = e^2 \approx 7.389 \in \left(e^{3/2}, \infty\right)$: $f(e^2) = \frac{2}{e^2} \approx 0.2707 \in \left(0, \frac{1}{e}\right)$, $f'(e^2) = -\frac{1}{e^4} < 0$ (decreasing), and $f''(e^2) = \frac{1}{e^6} > 0$ (convex).
2. **Application to Comparing $e^\pi$ and $\pi^e$**:
   Because $f(x) = \frac{\ln x}{x}$ achieves its strict global maximum at $x = e$ and is strictly decreasing on $[e, \infty)$, for $\pi > e$ we immediately have $f(e) > f(\pi) \iff \frac{\ln e}{e} > \frac{\ln \pi}{\pi} \iff \pi \ln e > e \ln \pi \iff e^\pi > \pi^e$.
