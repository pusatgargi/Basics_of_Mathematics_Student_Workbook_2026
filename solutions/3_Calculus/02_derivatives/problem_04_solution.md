# Problem 4: A Quotient and Domain Control

## Problem Statement

For
$$f(x)=\frac{x^2+1}{x-1}$$
determine the domain, compute the derivative, simplify the result, and explain why the restriction $x\neq1$ remains important.

## Theoretical Background and Concepts

When a function is expressed as the ratio of two differentiable functions, $f(x) = \frac{u(x)}{v(x)}$, it is defined wherever the denominator is non-zero ($v(x) \neq 0$). To differentiate $f(x)$, we use the **Quotient Rule**:
$$\frac{d}{dx}\left[\frac{u(x)}{v(x)}\right] = \frac{u'(x)v(x) - u(x)v'(x)}{[v(x)]^2}$$

Notice the order in the numerator: we start with the derivative of the numerator multiplied by the original denominator, $u'(x)v(x)$, and **subtract** the original numerator multiplied by the derivative of the denominator, $u(x)v'(x)$. All of this is divided by the square of the denominator, $[v(x)]^2$.

We also use:
- **Power, Sum/Difference, and Constant Rules**: $\frac{d}{dx}(x^n) = nx^{n-1}$ and $\frac{d}{dx}(c) = 0$.

## Detailed Step-by-Step Solution

### Step 1: Determine the domain of $f$

The rational function
$$f(x) = \frac{x^2 + 1}{x - 1}$$
has a polynomial numerator $u(x) = x^2 + 1$ and a polynomial denominator $v(x) = x - 1$, both of which are defined for all real numbers. The only restriction comes from preventing division by zero:
$$x - 1 \neq 0 \iff x \neq 1$$

Therefore, the domain of $f$ is:
$$D_f = \mathbb{R} \setminus \{1\} = (-\infty, 1) \cup (1, \infty)$$

---

### Step 2: Compute the derivative using the Quotient Rule

Because $f(x)$ is a quotient of $u(x) = x^2 + 1$ and $v(x) = x - 1$, we apply the **Quotient Rule**:
$$f'(x) = \frac{u'(x)v(x) - u(x)v'(x)}{[v(x)]^2}$$

First, we compute the derivatives of the numerator and the denominator using the **Power Rule** and **Constant Rule**:
- Numerator derivative: $u'(x) = \frac{d}{dx}(x^2 + 1) = 2x + 0 = 2x$.
- Denominator derivative: $v'(x) = \frac{d}{dx}(x - 1) = 1 - 0 = 1$.

Substituting $u(x) = x^2 + 1$, $v(x) = x - 1$, $u'(x) = 2x$, and $v'(x) = 1$ into the Quotient Rule formula gives:
$$f'(x) = \frac{(2x)(x - 1) - (x^2 + 1)(1)}{(x - 1)^2}$$

---

### Step 3: Simplify the result

We expand the products in the numerator carefully, paying attention to the minus sign in front of $(x^2 + 1)$:
$$(2x)(x - 1) - (x^2 + 1) = 2x^2 - 2x - x^2 - 1 = x^2 - 2x - 1$$

Thus, the simplified derivative is:
$$f'(x) = \frac{x^2 - 2x - 1}{(x - 1)^2}$$

---

### Step 4: Explain why the restriction $x \neq 1$ remains important

The restriction $x \neq 1$ remains critical for three closely connected reasons:
1. **Algebraic validity of $f'(x)$:** In the derivative formula $f'(x) = \frac{x^2 - 2x - 1}{(x - 1)^2}$, substituting $x = 1$ makes the denominator $(1 - 1)^2 = 0$, which is undefined (division by zero).
2. **Definition of differentiability:** By definition, a function can only have a derivative at points where the function itself is defined and continuous. Since $1 \notin D_f$ (in fact, $f(x)$ has a vertical asymptote at $x = 1$), $f'(1)$ cannot exist.
3. **Splitting of intervals in analysis:** Even if an algebraic manipulation ever cancelled a factor (or when we study the sign of $f'(x)$), the point $x = 1$ splits the domain into two separate intervals, $(-\infty, 1)$ and $(1, \infty)$. For instance, a function whose derivative is positive on $(-\infty, 1)$ and positive on $(1, \infty)$ is increasing on each interval separately, **not** necessarily across the vertical asymptote at $x = 1$.

## Verification and Consistency Checks

1. **Alternative Method (Algebraic Division Before Differentiating):**
   We can rewrite the rational function by polynomial division:
   $$x^2 + 1 = (x^2 - 1) + 2 = (x - 1)(x + 1) + 2$$
   For $x \neq 1$, dividing through by $x - 1$ gives:
   $$f(x) = x + 1 + \frac{2}{x - 1} = x + 1 + 2(x - 1)^{-1}$$
   Differentiating term by term using the Power/Chain Rule:
   $$f'(x) = 1 + 0 + 2(-1)(x - 1)^{-2} = 1 - \frac{2}{(x - 1)^2}$$
   Putting this over a common denominator $(x - 1)^2$:
   $$f'(x) = \frac{(x - 1)^2 - 2}{(x - 1)^2} = \frac{(x^2 - 2x + 1) - 2}{(x - 1)^2} = \frac{x^2 - 2x - 1}{(x - 1)^2}$$
   Both methods yield the exact same derivative!

2. **Numerical Check at $x = 2$:**
   - Using our formula: $f'(2) = \frac{2^2 - 2(2) - 1}{(2 - 1)^2} = \frac{4 - 4 - 1}{1} = -1$.
   - Using the alternative form: $f'(2) = 1 - \frac{2}{(2-1)^2} = 1 - 2 = -1$.
   - Using finite differences with $h = 0.001$: $f(2) = \frac{5}{1} = 5$, and $f(2.001) = \frac{(2.001)^2 + 1}{1.001} = \frac{5.004001}{1.001} \approx 4.999001998$.
     $$\frac{f(2.001) - f(2)}{0.001} \approx \frac{-0.000998002}{0.001} \approx -0.998 \to -1$$
