# Problem 10: A Cable Through Water and Land

## Problem Statement

Point $A$ lies on one bank of a river of width $100$ m, and point $B$ lies on the other bank, $500$ m along the bank from the point directly opposite $A$.

The cost per meter of cable underwater is twice the cost per meter of cable on land.

Build a cost function depending on the point where the cable comes out of the water, determine the domain, and find the solution that minimizes the cost.

## Theoretical Background and Concepts

This problem is a classic example of **spatial path optimization across two media with different unit costs** (mathematically analogous to Snell's Law of Refraction Derived from Fermat's Principle of Least Time):

1. **Geometric Decomposition of the Path**:
   Model the river as a parallel strip of width $W = 100\text{ m}$. Let $O$ be the point on the opposite bank directly across from $A$, so segment $AO$ is perpendicular to the riverbank ($AO \perp OB$) with $|AO| = 100\text{ m}$ and $|OB| = 500\text{ m}$.
   If the cable runs in a straight line underwater from $A$ to an emergence point $P$ on the bank segment $OB$, and then along the bank on land from $P$ to $B$:
   - The underwater segment $AP$ is the hypotenuse of the right triangle $\triangle AOP$.
   - The overland segment $PB$ is a straight segment along the bank.

2. **Weighted Objective Function**:
   When different sections of a path have different unit costs $c_1$ and $c_2$, the total cost is the weighted sum of the Euclidean lengths:
   $$
   C = c_{\text{water}} \cdot |AP| + c_{\text{land}} \cdot |PB|.
   $$

3. **Optimization on a Closed Bounded Interval**:
   For a continuous differentiable cost function $C(x)$ on a closed interval $[a, b]$, the global minimum occurs either at an interior stationary point where $C'(x) = 0$ or at one of the boundary endpoints $x = a$ or $x = b$.

## Detailed Step-by-Step Solution

### Step 1: Defining Variables and Building the Cost Function

Let $O$ be the point on the second bank directly opposite $A$, so that $\angle AOB = 90^\circ$, $|AO| = 100\text{ m}$, and $|OB| = 500\text{ m}$.
Let $P$ be the point on the bank where the cable emerges from the water, and define:
$$
x = |OP| \quad [\text{m}]
$$
as the distance along the bank from the point $O$ (directly opposite $A$) to the emergence point $P$.

- **Length of cable underwater ($|AP|$)**:
  By the Pythagorean theorem in the right triangle $\triangle AOP$:
  $$
  L_{\text{water}}(x) = |AP| = \sqrt{|AO|^2 + |OP|^2} = \sqrt{100^2 + x^2} = \sqrt{x^2 + 10\,000}\quad [\text{m}].
  $$
- **Length of cable on land ($|PB|$)**:
  $$
  L_{\text{land}}(x) = |PB| = 500 - x\quad [\text{m}].
  $$
- **Unit Costs**:
  Let $c > 0$ denote the cost per meter of laying the cable on land (in monetary units per meter). Then the cost per meter underwater is $2c$.
- **Total Cost Function $C(x)$**:
  $$
  \begin{aligned}
  C(x) &= (2c)\cdot L_{\text{water}}(x) + c\cdot L_{\text{land}}(x) \\
  &= 2c\sqrt{x^2 + 10\,000} + c(500 - x) \\
  &= c\left(2\sqrt{x^2 + 10\,000} + 500 - x\right).
  \end{aligned}
  $$
  *(Note: If one instead defines $u = 500 - x$ as the distance from $B$ to $P$, the cost function is $\widetilde{C}(u) = c\left(2\sqrt{(500-u)^2 + 10\,000} + u\right)$.)*

---

### Step 2: Determining the Domain

Geometrically, the emergence point $P$ should lie on the segment $OB$ between the point $O$ (directly opposite $A$) and the destination $B$:
- If $x = 0$, the cable crosses the river perpendicularly to $O$ and goes $500\text{ m}$ on land.
- If $x = 500$, the cable goes diagonally underwater all the way from $A$ to $B$ with $0\text{ m}$ on land.
- Choosing $x < 0$ or $x > 500$ would strictly increase both the underwater distance and the land distance compared to $x = 0$ or $x = 500$.

Therefore, the physically meaningful domain is the closed interval:
$$
D = [0, 500] \quad (\text{in meters}).
$$

---

### Step 3: Finding the Point that Minimizes the Cost

**Step 3a: Differentiate $C(x)$ with respect to $x$.**
Using the chain rule $\frac{d}{dx}\sqrt{x^2 + 10\,000} = \frac{2x}{2\sqrt{x^2 + 10\,000}} = \frac{x}{\sqrt{x^2 + 10\,000}}$:
$$
\begin{aligned}
C'(x) &= c\left(2 \cdot \frac{x}{\sqrt{x^2 + 10\,000}} - 1\right) \\
&= c\,\frac{2x - \sqrt{x^2 + 10\,000}}{\sqrt{x^2 + 10\,000}}.
\end{aligned}
$$

**Step 3b: Solve $C'(x) = 0$ for stationary points.**
Since $c > 0$ and $\sqrt{x^2 + 10\,000} > 0$, we have $C'(x) = 0$ if and only if:
$$
2x - \sqrt{x^2 + 10\,000} = 0 \iff 2x = \sqrt{x^2 + 10\,000}.
$$
Since $x \in [0, 500]$, both sides are non-negative. Squaring both sides gives:
$$
\begin{aligned}
4x^2 = x^2 + 10\,000 &\iff 3x^2 = 10\,000 \\
&\iff x^2 = \frac{10\,000}{3} \\
&\implies x^* = \frac{100}{\sqrt{3}} = \frac{100\sqrt{3}}{3}\text{ m} \approx 57.74\text{ m}.
\end{aligned}
$$
Clearly, $x^* = \frac{100\sqrt{3}}{3} \approx 57.74\text{ m}$ lies strictly inside the domain $[0, 500]$.

**Step 3c: Justify that $x^*$ is the global minimum on $[0, 500]$.**
- **First Derivative Test**:
  - For $x \in \left[0, \frac{100\sqrt{3}}{3}\right)$, we have $4x^2 < x^2 + 10\,000 \implies 2x < \sqrt{x^2 + 10\,000} \implies C'(x) < 0$, so $C(x)$ is **strictly decreasing**.
  - For $x \in \left(\frac{100\sqrt{3}}{3}, 500\right]$, we have $4x^2 > x^2 + 10\,000 \implies 2x > \sqrt{x^2 + 10\,000} \implies C'(x) > 0$, so $C(x)$ is **strictly increasing**.
  Hence, $x^* = \frac{100\sqrt{3}}{3}\text{ m}$ is the unique global minimum on $[0, 500]$.
- **Second Derivative Test**:
  $$
  C''(x) = 2c\,\frac{\sqrt{x^2+10\,000} - x\cdot\frac{x}{\sqrt{x^2+10\,000}}}{x^2+10\,000} = \frac{20\,000\,c}{\left(x^2 + 10\,000\right)^{3/2}} > 0 \quad \text{for all } x \in [0, 500],
  $$
  confirming strict convexity of $C(x)$ on the entire interval.

---

### Step 4: Summary and Interpretation of the Optimal Solution

- **Optimal Emergence Point**: The cable should come out of the water at a distance of
  $$
  x^* = \frac{100\sqrt{3}}{3}\text{ m} \approx 57.74\text{ m}
  $$
  downstream from the point $O$ directly opposite $A$ (which is $500 - \frac{100\sqrt{3}}{3} \approx 442.26\text{ m}$ before reaching point $B$).
- **Optimal Path Lengths**:
  - Underwater cable length: $|AP| = \sqrt{\frac{10\,000}{3} + 10\,000} = \frac{200}{\sqrt{3}} = \frac{200\sqrt{3}}{3}\text{ m} \approx 115.47\text{ m}$.
  - Land cable length: $|PB| = 500 - \frac{100\sqrt{3}}{3}\text{ m} \approx 442.26\text{ m}$.
- **Minimum Total Cost**:
  $$
  C_{\min} = C\left(\frac{100\sqrt{3}}{3}\right) = c\left(\frac{400}{\sqrt{3}} + 500 - \frac{100}{\sqrt{3}}\right) = c\left(500 + 100\sqrt{3}\right) \approx 673.21\,c.
  $$

## Verification and Consistency Checks

1. **Comparison with Boundary Endpoints ($x = 0$ and $x = 500$)**:
   - **Perpendicular river crossing ($x = 0$)**:
     $$
     C(0) = c\left(2\sqrt{10\,000} + 500\right) = c(200 + 500) = 700\,c > 673.21\,c.
     $$
   - **Straight underwater diagonal ($x = 500$)**:
     $$
     C(500) = c\left(2\sqrt{250\,000 + 10\,000} + 0\right) = 200\sqrt{26}\,c \approx 1019.80\,c > 673.21\,c.
     $$
   The optimal path saves $26.79\,c$ (about $3.8\%$) compared to crossing straight across and saves $346.60\,c$ compared to going straight diagonally underwater.

2. **Trigonometric / Snell's Law Check**:
   In $\triangle AOP$, the angle $\theta$ between the underwater cable $AP$ and the normal $AO$ satisfies $\sin\theta = \frac{x^*}{|AP|} = \frac{100/\sqrt{3}}{200/\sqrt{3}} = \frac{1}{2} = \frac{c_{\text{land}}}{c_{\text{water}}}$, so $\theta = 30^\circ$ (and the angle with the bank is $60^\circ$). Notice that as long as the horizontal distance to $B$ is at least $\frac{100}{\sqrt{3}} \approx 57.74\text{ m}$, the optimal emergence angle is always $30^\circ$ from the perpendicular!
