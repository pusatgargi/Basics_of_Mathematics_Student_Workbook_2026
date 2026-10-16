# Problem 10: Continuity of a Piecewise Function

## Problem Statement

Find $a$ so that
$$f(x)=\begin{cases}ax+1,&x<2,\\x^2-1,&x\ge2\end{cases}$$
is continuous at $x=2$. Explicitly compare the left-hand limit, right-hand limit, and function value.

## Theoretical Background and Concepts

Intuitively, a function $f$ is **continuous at a point $x_0$** if its graph has no break, jump, or hole at $x_0$—meaning that as $x$ approaches $x_0$ from either side, $f(x)$ approaches the exact height $f(x_0)$ where the function is actually defined.

Formally, a function $f$ is **continuous at an interior point $x_0$** of its domain if and only if the following conditions hold:
1. $f(x_0)$ is defined (i.e., $x_0$ belongs to the domain of $f$).
2. The two-sided limit $\lim_{x\to x_0} f(x)$ exists (which requires the left-hand limit $\lim_{x\to x_0^-} f(x)$ and the right-hand limit $\lim_{x\to x_0^+} f(x)$ to both exist and be equal).
3. The limit equals the function value at $x_0$:
   $$\lim_{x\to x_0} f(x) = f(x_0).$$

For a **piecewise-defined function** whose formula changes at a boundary point $x = x_0$, checking continuity at $x_0$ requires verifying the **agreement of three quantities**:
$$\lim_{x\to x_0^-} f(x) = \lim_{x\to x_0^+} f(x) = f(x_0).$$
- To compute the **left-hand limit** $\lim_{x\to x_0^-} f(x)$, we use the formula valid for $x < x_0$.
- To compute the **right-hand limit** $\lim_{x\to x_0^+} f(x)$, we use the formula valid for $x > x_0$.
- To compute the **function value** $f(x_0)$, we use the branch whose domain condition includes $x = x_0$ (e.g., $x \ge x_0$ or $x \le x_0$).

## Detailed Step-by-Step Solution

We are given the piecewise function:
$$f(x)=\begin{cases}ax+1,&x<2,\\x^2-1,&x\ge2.\end{cases}$$
Let us compute each of the three required quantities at $x_0 = 2$.

### Step 1: Compute the Function Value $f(2)$

To evaluate $f(2)$, we look for the branch that includes $x = 2$. The second branch applies for $x \ge 2$. Substituting $x = 2$ into $x^2 - 1$ gives:
$$f(2) = 2^2 - 1 = 4 - 1 = 3.$$

### Step 2: Compute the Right-Hand Limit $\lim_{x\to 2^+} f(x)$

When $x$ approaches $2$ from the right ($x \to 2^+$), we have $x > 2$. In this region, $f(x)$ is given by the second branch, $f(x) = x^2 - 1$. Since $x^2 - 1$ is a polynomial (and polynomials are continuous everywhere), we can evaluate the limit by direct substitution:
$$\lim_{x\to 2^+} f(x) = \lim_{x\to 2^+} (x^2 - 1) = 2^2 - 1 = 4 - 1 = 3.$$

### Step 3: Compute the Left-Hand Limit $\lim_{x\to 2^-} f(x)$

When $x$ approaches $2$ from the left ($x \to 2^-$), we have $x < 2$. In this region, $f(x)$ is given by the first branch, $f(x) = ax + 1$. Since $ax + 1$ is a linear polynomial for any real constant $a$, we evaluate the limit by substituting $x = 2$:
$$\lim_{x\to 2^-} f(x) = \lim_{x\to 2^-} (ax + 1) = a(2) + 1 = 2a + 1.$$

### Step 4: Explicitly Compare the Three Quantities and Solve for $a$

Let us summarize and compare the three quantities at $x = 2$:
1. **Left-hand limit**: $\lim_{x\to 2^-} f(x) = 2a + 1$
2. **Right-hand limit**: $\lim_{x\to 2^+} f(x) = 3$
3. **Function value**: $f(2) = 3$

Notice that the right-hand limit and the function value **already agree** ($\lim_{x\to 2^+} f(x) = f(2) = 3$) because the branch $x^2 - 1$ covers both $x > 2$ and $x = 2$ ($x \ge 2$), making $f$ automatically **right-continuous** at $x = 2$ for every value of $a$.

For $f(x)$ to be **continuous** at $x = 2$, the two-sided limit $\lim_{x\to 2} f(x)$ must exist and equal $f(2)$, which requires all three quantities to be equal:
$$\lim_{x\to 2^-} f(x) = \lim_{x\to 2^+} f(x) = f(2).$$

Substituting our expressions gives the linear equation:
$$2a + 1 = 3.$$

Solving for $a$:
$$\begin{aligned}
2a &= 3 - 1 \\
2a &= 2 \\
a &= 1.
\end{aligned}$$

Geometrically, when $a = 1$, the left-hand line $y = x + 1$ approaches the point $(2, 3)$ as $x \to 2^-$, seamlessly meeting the right-hand parabola $y = x^2 - 1$ at its starting point $(2, 3)$ without a jump discontinuity. (If $a \neq 1$, there is a jump of size $|(2a+1) - 3| = 2|a - 1|$ at $x = 2$.)

**Final Answer:**
$$a = 1.$$

## Verification and Consistency Checks

Let us substitute $a = 1$ back into the definition of $f(x)$:
$$f(x) = \begin{cases} x + 1, & x < 2, \\ x^2 - 1, & x \ge 2. \end{cases}$$

We verify continuity at $x = 2$ both analytically and numerically:
1. **Analytical Check**:
   - $\lim_{x\to 2^-} f(x) = \lim_{x\to 2^-} (x + 1) = 2 + 1 = 3$.
   - $\lim_{x\to 2^+} f(x) = \lim_{x\to 2^+} (x^2 - 1) = 2^2 - 1 = 3$.
   - $f(2) = 2^2 - 1 = 3$.
   All three values equal $3$, confirming continuity at $x = 2$.

2. **Numerical Table Around $x = 2$ (for $a = 1$)**:

   | $x$ | Branch Used | $f(x)$ | Distance $|f(x) - f(2)|$ |
   | :--- | :--- | :--- | :--- |
   | $1.9$ | $x + 1$ ($x < 2$) | $2.9000$ | $0.1000$ |
   | $1.99$ | $x + 1$ ($x < 2$) | $2.9900$ | $0.0100$ |
   | $1.999$ | $x + 1$ ($x < 2$) | $2.9990$ | $0.0010$ |
   | $\mathbf{2.0}$ | $x^2 - 1$ ($x \ge 2$) | $\mathbf{3.0000}$ | $\mathbf{0}$ |
   | $2.001$ | $x^2 - 1$ ($x \ge 2$) | $3.004001$ | $0.004001$ |
   | $2.01$ | $x^2 - 1$ ($x \ge 2$) | $3.0401$ | $0.0401$ |
   | $2.1$ | $x^2 - 1$ ($x \ge 2$) | $3.4100$ | $0.4100$ |

   The values of $f(x)$ approach $3$ smoothly from both left and right, matching $f(2) = 3$.
