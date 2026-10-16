# Problem 15: Observation Versus Proof

## Problem Statement

Choose one sequence and one function from this set. For the sequence, compute several values for increasingly large $n$. For the function, prepare a table of values with arguments approaching the limit point from the left and right. Sketch the behavior of both objects.

Compare the observation with the analytical result and explain why a finite number of calculations or a sketch does not constitute a proof that the limit exists.

## Theoretical Background and Concepts

In mathematics, **numerical observation and graphical visualization** play a vital heuristic role: they build intuition, suggest conjectures about whether a limit exists and what its value might be, and serve as sanity checks against algebraic errors. However, **observation is not proof**.

Let us recall the formal definitions of the two types of limits studied in this set:
1. **Limit of a Sequence ($\lim_{n\to\infty} a_n = L$)**:
   For *every* $\varepsilon > 0$ (no matter how tiny), there exists a threshold index $N \in \mathbb{N}$ such that for **all** integers $n > N$ (an infinite number of terms!), $|a_n - L| < \varepsilon$.
2. **Limit of a Function at a Point ($\lim_{x\to x_0} f(x) = L$)**:
   For *every* $\varepsilon > 0$, there exists a neighborhood radius $\delta > 0$ such that for **all** real numbers $x$ satisfying $0 < |x - x_0| < \delta$ (an uncountably infinite continuum of points on both the left and the right of $x_0$), $|f(x) - L| < \varepsilon$.

Because both definitions make universal claims ("for every $\varepsilon > 0$" and "for all $n > N$" or "for all $x$ in $0 < |x - x_0| < \delta$"), a finite table of values or a finite-resolution sketch can only ever inspect a finite sample of points. Establishing a limit with certainty requires an **analytical proof** based on algebraic transformations, inequalities (such as the Squeeze Theorem), or theorems of analysis.

## Detailed Step-by-Step Solution

### Step 1: Selection of One Sequence and One Function from the Set

From this problem set, we choose:
1. **Sequence (from Exercise 3)**:
   $$a_n = \sqrt{n^2 + 5n} - n \quad \text{as } n \to \infty,$$
   whose analytical limit we proved in Exercise 3 (via conjugation: $a_n = \frac{5n}{\sqrt{n^2+5n}+n} = \frac{5}{\sqrt{1+5/n}+1}$) to be:
   $$\lim_{n\to\infty} a_n = \frac{5}{2} = 2.5.$$
2. **Function (from Exercise 8)**:
   $$f(x) = \frac{\sqrt{x} - 2}{x - 4} \quad \text{as } x \to 4,$$
   whose analytical limit we proved in Exercise 8 (via rationalizing the numerator: $f(x) = \frac{1}{\sqrt{x}+2}$ for $x \neq 4$) to be:
   $$\lim_{x\to 4} f(x) = \frac{1}{4} = 0.25.$$

---

### Step 2: Numerical Investigation and Sketch for the Sequence $a_n = \sqrt{n^2+5n} - n$

#### Table of Values for Increasingly Large $n$

Let us compute $a_n = \sqrt{n^2+5n} - n$ across several orders of magnitude of $n$:

| $n$ | $n^2 + 5n$ | $\sqrt{n^2+5n}$ | $a_n = \sqrt{n^2+5n} - n$ | Distance from Analytical Limit $|2.5 - a_n|$ |
| :--- | :--- | :--- | :--- | :--- |
| $1$ | $6$ | $2.44948974$ | $1.44948974$ | $1.05051026$ |
| $2$ | $14$ | $3.74165739$ | $1.74165739$ | $0.75834261$ |
| $5$ | $50$ | $7.07106781$ | $2.07106781$ | $0.42893219$ |
| $10$ | $150$ | $12.24744871$ | $2.24744871$ | $0.25255129$ |
| $50$ | $2,750$ | $52.44044241$ | $2.44044241$ | $0.05955759$ |
| $100$ | $10,500$ | $102.46950766$ | $2.46950766$ | $0.03049234$ |
| $1,000$ | $1,005,000$ | $1002.49688279$ | $2.49688279$ | $0.00311721$ |
| $10,000$ | $100,050,000$ | $10002.49968758$ | $2.49968758$ | $0.00031242$ |
| $100,000$ | $10,000,500,000$ | $100002.49996875$ | $2.49996875$ | $0.00003125$ |

#### ASCII Sketch of the Sequence $a_n = \sqrt{n^2+5n} - n$

```text
  a_n
  2.5 + - - - - - - - - - - - - - - - - - - - - - - * - - * - - *  (Horizontal Asymptote L = 2.5)
      |                                       *
  2.25+                                 *
      |                           *
  2.0 +                     *
      |               *
  1.5 +         *
      |
      +---------+-----+-----+-----+-----+-----+-----+-----+-----+---> n (log scale)
                1     2     5    10    50   100  1000  10^4  10^5
```

---

### Step 3: Numerical Investigation and Sketch for the Function $f(x) = \frac{\sqrt{x}-2}{x-4}$ as $x \to 4$

#### Table of Values Approaching $x = 4$ from the Left ($x \to 4^-$) and Right ($x \to 4^+$)

| Left Approach ($x < 4$) | $f(x) = \frac{\sqrt{x}-2}{x-4}$ | Error $|f(x) - 0.25|$ | Right Approach ($x > 4$) | $f(x) = \frac{\sqrt{x}-2}{x-4}$ | Error $|f(x) - 0.25|$ |
| :--- | :--- | :--- | :--- | :--- | :--- |
| $x = 3.5$ | $0.25834261$ | $0.00834261$ | $x = 4.5$ | $0.24264069$ | $0.00735931$ |
| $x = 3.9$ | $0.25158234$ | $0.00158234$ | $x = 4.1$ | $0.24845673$ | $0.00154327$ |
| $x = 3.99$ | $0.25015635$ | $0.00015635$ | $x = 4.01$ | $0.24984385$ | $0.00015615$ |
| $x = 3.999$ | $0.25001563$ | $0.00001563$ | $x = 4.001$ | $0.24998438$ | $0.00001562$ |
| $x = 3.9999$ | $0.25000156$ | $0.00000156$ | $x = 4.0001$ | $0.24999844$ | $0.00000156$ |

*(Note: At $x = 4$ itself, $f(4) = \frac{0}{0}$ is undefined, so there is a removable puncture/hole at $(4, 0.25)$.)*

#### ASCII Sketch of the Function $f(x) = \frac{\sqrt{x}-2}{x-4}$ Near $x = 4$

```text
  f(x)
  0.30 +  * (2.25, 0.286)
       |       * (3.0, 0.268)
       |            * (3.5, 0.258)
  0.25 + - - - - - - - - o (4, 0.25) [Open circle: hole at x = 4, limit L = 0.25]
       |                      * (4.5, 0.243)
       |                           * (5.0, 0.236)
  0.20 +                                * (6.25, 0.222)
       |
       +--------+--------+--------+--------+--------+---> x
                2        3        4        5        6
```

---

### Step 4: Comparison of Observations with Analytical Results

1. **For the Sequence $a_n = \sqrt{n^2+5n} - n$**:
   - **Observation**: The computed terms increase monotonically from $a_1 \approx 1.4495$ toward $2.5$, with the distance $2.5 - a_n$ shrinking by a factor of $10$ whenever $n$ increases by a factor of $10$ (e.g., $0.0305$ at $n=100$, $0.00312$ at $n=1000$, $0.000312$ at $n=10000$).
   - **Analytical Explanation**: Our algebraic transformation in Exercise 3 showed $a_n = \frac{5}{\sqrt{1+5/n}+1}$. Subtracting from $\frac{5}{2}$ gives:
     $$\frac{5}{2} - a_n = \frac{5\left(\sqrt{1 + 5/n} - 1\right)}{2\left(\sqrt{1 + 5/n} + 1\right)} = \frac{25}{2n\left(\sqrt{1+5/n}+1\right)^2} \approx \frac{25}{8n} = \frac{3.125}{n}.$$
     This analytical formula explains both why $a_n < 2.5$ for all $n$ and why the error at $n = 10,000$ is $\frac{3.125}{10000} = 0.0003125$, matching our table to $7$ decimal places!

2. **For the Function $f(x) = \frac{\sqrt{x}-2}{x-4}$**:
   - **Observation**: As $x \to 4^-$, $f(x)$ decreases smoothly toward $0.25$ ($0.2583, 0.2516, 0.25016, \dots$); as $x \to 4^+$, $f(x)$ increases smoothly toward $0.25$ ($0.2426, 0.2485, 0.24984, \dots$).
   - **Analytical Explanation**: Our rationalization in Exercise 8 showed $f(x) = \frac{1}{\sqrt{x}+2}$ for $x \neq 4$. The difference from $\frac{1}{4}$ is:
     $$f(x) - \frac{1}{4} = \frac{2 - \sqrt{x}}{4(\sqrt{x}+2)} = -\frac{x - 4}{4(\sqrt{x}+2)^2} \approx -\frac{x - 4}{64} = -0.015625(x - 4).$$
     This explains why for $x = 3.999$ ($x - 4 = -0.001$), $f(x) \approx 0.25 + 0.000015625$, and for $x = 4.001$ ($x - 4 = +0.001$), $f(x) \approx 0.25 - 0.000015625$, matching our table!

---

### Step 5: Why a Finite Number of Calculations or a Sketch Does Not Constitute a Proof

Even though our tables and sketches agree with the analytical limits, **a finite table of values or a sketch can never prove that a limit exists or equals $L$**, for four fundamental mathematical reasons:

1. **Finiteness vs. Infinitude of the Limit Definition**:
   - For a sequence $\lim_{n\to\infty} a_n = L$, the definition concerns the behavior of $a_n$ for **all** $n > N$ as $n \to \infty$. Checking $10$ or $1,000,000$ values leaves infinitely many larger values of $n$ completely untested. A sequence could follow $\sqrt{n^2+5n} - n$ for the first $10^{10}$ terms and then diverge (e.g., by adding $10^{-100}n^2$).
   - For a function $\lim_{x\to x_0} f(x) = L$, every open neighborhood $(x_0 - \delta, x_0 + \delta)$ contains **uncountably infinitely many** real numbers. Testing $x = 3.9, 3.99, 3.999, 3.9999$ only checks a single sequence of points and ignores what happens between them!
2. **Hidden Rapid Oscillations Near the Limit Point**:
   A function can appear to converge in a table of decimal points while actually failing to have a limit due to rapid oscillations between the sampled points. For example, consider $g(x) = \sin\left(\frac{\pi}{x - 4}\right)$ as $x \to 4$. If we only evaluate $g(x)$ at $x = 4 \pm 10^{-k}$ ($k = 1, 2, 3, \dots$), then $\frac{\pi}{x - 4} = \pm 10^k \pi$ is always an integer multiple of $\pi$, so $g(4 \pm 10^{-k}) = 0$ at **every single point in the table**, even though $\lim_{x\to 4} g(x)$ does not exist (it oscillates wildly between $-1$ and $+1$ infinitely many times near $x = 4$)!
3. **Finite Resolution of Sketches**:
   Any physical or computer-generated graph has finite pixel resolution and line thickness. It cannot distinguish between a true limit $0.25$ and $0.25000001$, nor can it resolve infinitely narrow spikes, microscopic jumps, or infinitely dense oscillations inside a sub-pixel neighborhood of $x = 4$.
4. **Floating-Point Artifacts, Input Rounding, and Catastrophic Cancellation**:
   Our two chosen examples ($a_n = \sqrt{n^2+5n} - n$ and $f(x) = \frac{\sqrt{x}-2}{x-4}$) illustrate how numerical floating-point evaluation can fail and mislead when pushed to extremes. In standard IEEE 754 double precision (`binary64`, offering $\approx 53$ bits or $15\text{--}17$ decimal digits of precision):

   - **For the Sequence $a_n = \sqrt{n^2+5n} - n$**:
     - At $n = 10^{10}$, $n^2 + 5n = 10^{20} + 5 \times 10^{10}$. The ratio $\frac{5n}{n^2} = 5 \times 10^{-10}$ is well above machine precision ($\varepsilon_{\text{mach}} \approx 1.11 \times 10^{-16}$), so direct floating-point calculation still correctly outputs $2.5$.
     - However, at $n = 10^{16}$, the ratio $\frac{5n}{n^2} = 5 \times 10^{-16}$ is on the edge of machine precision. Subtractive cancellation degrades the calculation, and direct evaluation computes $\sqrt{10^{32} + 5\times 10^{16}} - 10^{16} = \mathbf{2.0}$ instead of $2.5$.
     - At $n = 10^{17}$, the ratio $\frac{5n}{n^2} = 5 \times 10^{-17} < \varepsilon_{\text{mach}}$. In floating-point addition, $n^2 + 5n = 10^{34} + 5 \times 10^{17}$ rounds exactly to $10^{34} = n^2$. Consequently, the computer computes:
       $$\sqrt{n^2+5n} - n = \sqrt{n^2} - n = n - n = \mathbf{0.0}.$$
       Due to catastrophic cancellation, numerical evaluation reports $0.0$ instead of the true limit $2.5$.

   - **For the Function $f(x) = \frac{\sqrt{x}-2}{x-4}$ Near $x = 4$**:
     Here it is essential to distinguish between **rounding an input to the excluded point** and **catastrophic cancellation in a valid quotient**:
     - *Catastrophic cancellation in a valid quotient ($x \neq 4$)*: For $x = 4 + 10^{-15}$, the input is represented as the distinct floating-point number $x = 4 + 2^{-50} \approx 4.000000000000000888$. The denominator is $x - 4 = 2^{-50} \approx 8.88 \times 10^{-16} \neq 0$ (a valid, non-zero denominator in the punctured neighborhood). However, $\sqrt{4 + 2^{-50}}$ rounds in `binary64` to $2.0$ exactly, so the computed numerator is $\sqrt{x} - 2 = 0.0$. Thus, the computer calculates:
       $$\frac{\sqrt{x}-2}{x-4} = \frac{0.0}{8.88 \times 10^{-16}} = \mathbf{0.0}.$$
       The computed output is $0.0$ instead of the true limit $0.25$, solely because of cancellation in the numerator.
     - *Rounding the input to the excluded point ($x = 4$)*: In contrast, if we choose $\delta = 10^{-16}$, the quantity $4 + 10^{-16}$ falls below the spacing between representable floats near $4$ ($2^{-50} \approx 8.88 \times 10^{-16}$) and rounds directly to $4.0$ itself. At this rounded input, both numerator and denominator evaluate to $0.0$, so the machine encounters $\frac{0.0}{0.0}$, which is **undefined** (yielding `NaN` or a division-by-zero error), rather than $0.0$.

   These phenomena demonstrate that finite numerical computations can easily produce false zeros or undefined results. Only an **analytical proof** (e.g., using conjugation to remove the indeterminate form) provides an exact and trustworthy result.

## Verification and Consistency Checks

We have verified both the sequence $a_n = \sqrt{n^2+5n} - n$ and the function $f(x) = \frac{\sqrt{x}-2}{x-4}$ by cross-checking their direct numerical evaluations against their rationalized analytical forms:
- For $n = 1000$: direct formula $\sqrt{1005000} - 1000 \approx 2.49688279$; rationalized formula $\frac{5}{\sqrt{1.005}+1} \approx 2.49688279$.
- For $x = 3.9999$: direct formula $\frac{\sqrt{3.9999}-2}{3.9999-4} \approx 0.25000156$; rationalized formula $\frac{1}{\sqrt{3.9999}+2} \approx 0.25000156$.
Both forms agree identically, confirming the consistency of our numerical tables and analytical proofs.
