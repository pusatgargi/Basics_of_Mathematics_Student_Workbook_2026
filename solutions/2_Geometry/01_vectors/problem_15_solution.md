# Problem 15: Comparing Directions Using the Cosine of the Angle

## Problem Statement

Given
$$a=(1,2,1),\qquad b=(2,4,2),\qquad c=(2,0,3).$$
For each pair, compute
$$\frac{u\cdot v}{\|u\|\,\|v\|}.$$
Order the pairs by increasing angle between the vectors. Explain why for $a$ and $b$ the value is $1$ even though the vectors have different lengths.

## Theoretical Background and Concepts

1. **Cosine of the Angle Between Two Vectors:** For any two non-zero vectors $u, v \in \mathbb{R}^3$, the cosine of the angle $\theta \in [0, \pi]$ ($[0^\circ, 180^\circ]$) between them is given by the normalized dot product:
   $$\cos\theta = \frac{u \cdot v}{\|u\|\,\|v\|}.$$

2. **Cosine Similarity as a Dot Product of Unit Vectors:** Notice that we can rewrite the quotient as the dot product of the two normalized unit vectors $\hat{u} = \frac{u}{\|u\|}$ and $\hat{v} = \frac{v}{\|v\|}$:
   $$\frac{u \cdot v}{\|u\|\,\|v\|} = \left(\frac{u}{\|u\|}\right) \cdot \left(\frac{v}{\|v\|}\right).$$
   Because normalizing removes each vector's length, this ratio depends **solely on the directions** of $u$ and $v$ and is completely invariant under positive scaling of either vector.

3. **Ordering Angles via Their Cosines:** On the interval $\theta \in [0, \pi]$, the function $\cos\theta$ is **strictly decreasing** from $\cos(0) = 1$ down to $\cos(\pi) = -1$. Consequently:
   - A **larger** value of $\cos\theta$ corresponds to a **smaller** angle $\theta$.
   - A **smaller** value of $\cos\theta$ corresponds to a **larger** angle $\theta$.
   - Equal values of $\cos\theta$ correspond to **equal** angles $\theta$.

## Detailed Step-by-Step Solution

We are given the three vectors in $\mathbb{R}^3$:
$$a = (1, 2, 1), \qquad b = (2, 4, 2), \qquad c = (2, 0, 3).$$

### Step 1: Compute the Length of Each Vector

Using the Euclidean norm formula $\|u\| = \sqrt{u_1^2 + u_2^2 + u_3^2}$:

1. **Length of $a = (1, 2, 1)$:**
   $$\|a\| = \sqrt{1^2 + 2^2 + 1^2} = \sqrt{1 + 4 + 1} = \sqrt{6}.$$

2. **Length of $b = (2, 4, 2)$:**
   $$\|b\| = \sqrt{2^2 + 4^2 + 2^2} = \sqrt{4 + 16 + 4} = \sqrt{24} = \sqrt{4 \cdot 6} = 2\sqrt{6}.$$

3. **Length of $c = (2, 0, 3)$:**
   $$\|c\| = \sqrt{2^2 + 0^2 + 3^2} = \sqrt{4 + 0 + 9} = \sqrt{13}.$$

### Step 2: Compute $\frac{u \cdot v}{\|u\|\,\|v\|}$ for Each Pair

#### Pair 1: Vectors $a = (1, 2, 1)$ and $b = (2, 4, 2)$

First, compute the dot product $a \cdot b = a_1 b_1 + a_2 b_2 + a_3 b_3$:
$$a \cdot b = (1)(2) + (2)(4) + (1)(2) = 2 + 8 + 2 = 12.$$
Next, compute the product of their norms:
$$\|a\|\,\|b\| = \sqrt{6} \cdot 2\sqrt{6} = 2 \cdot 6 = 12.$$
Taking the ratio gives:
$$\cos\theta_{ab} = \frac{a \cdot b}{\|a\|\,\|b\|} = \frac{12}{12} = 1.$$
This corresponds to the angle $\theta_{ab} = \arccos(1) = 0^\circ$ ($0\text{ rad}$).

#### Pair 2: Vectors $a = (1, 2, 1)$ and $c = (2, 0, 3)$

First, compute the dot product $a \cdot c = a_1 c_1 + a_2 c_2 + a_3 c_3$:
$$a \cdot c = (1)(2) + (2)(0) + (1)(3) = 2 + 0 + 3 = 5.$$
Next, compute the product of their norms:
$$\|a\|\,\|c\| = \sqrt{6} \cdot \sqrt{13} = \sqrt{6 \cdot 13} = \sqrt{78}.$$
Taking the ratio gives:
$$\cos\theta_{ac} = \frac{a \cdot c}{\|a\|\,\|c\|} = \frac{5}{\sqrt{78}} = \frac{5\sqrt{78}}{78} \approx 0.5661.$$
This corresponds to the angle $\theta_{ac} = \arccos\left(\frac{5}{\sqrt{78}}\right) \approx 55.52^\circ$ ($\approx 0.969\text{ rad}$).

#### Pair 3: Vectors $b = (2, 4, 2)$ and $c = (2, 0, 3)$

First, compute the dot product $b \cdot c = b_1 c_1 + b_2 c_2 + b_3 c_3$:
$$b \cdot c = (2)(2) + (4)(0) + (2)(3) = 4 + 0 + 6 = 10.$$
Next, compute the product of their norms:
$$\|b\|\,\|c\| = 2\sqrt{6} \cdot \sqrt{13} = 2\sqrt{78}.$$
Taking the ratio gives:
$$\cos\theta_{bc} = \frac{b \cdot c}{\|b\|\,\|c\|} = \frac{10}{2\sqrt{78}} = \frac{5}{\sqrt{78}} = \frac{5\sqrt{78}}{78} \approx 0.5661.$$
This corresponds to the angle $\theta_{bc} = \arccos\left(\frac{5}{\sqrt{78}}\right) \approx 55.52^\circ$ ($\approx 0.969\text{ rad}$).

### Step 3: Order the Pairs by Increasing Angle Between the Vectors

Comparing the three cosine values:
$$\cos\theta_{ab} = 1 \;>\; \cos\theta_{ac} = \cos\theta_{bc} = \frac{5}{\sqrt{78}} \approx 0.5661.$$
Because $\cos\theta$ is strictly decreasing on $[0, \pi]$, ordering from largest cosine to smallest cosine orders the pairs by **increasing angle**:
$$\theta_{ab} = 0^\circ \;<\; \theta_{ac} = \theta_{bc} = \arccos\left(\frac{5}{\sqrt{78}}\right) \approx 55.52^\circ.$$
Thus, ordered by increasing angle:
1. **Smallest angle:** Pair **$(a, b)$** with $\theta_{ab} = 0^\circ$ ($\cos\theta_{ab} = 1$).
2. **Larger angle (tied):** Pairs **$(a, c)$** and **$(b, c)$**, which have the **exact same angle** $\theta_{ac} = \theta_{bc} = \arccos\left(\frac{5}{\sqrt{78}}\right) \approx 55.52^\circ$ ($\cos\theta_{ac} = \cos\theta_{bc} = \frac{5}{\sqrt{78}}$), because $a$ and $b$ point along the exact same ray from the origin and therefore make the same angle with $c$.

### Step 4: Explain Why for $a$ and $b$ the Value Is $1$ Even Though the Vectors Have Different Lengths

Notice that $b = (2, 4, 2) = 2(1, 2, 1) = 2a$ is a positive scalar multiple of $a$, so $b$ has twice the length of $a$ ($\|b\| = 2\sqrt{6} = 2\|a\|$), yet points in the **exact same direction and orientation** ($\theta_{ab} = 0^\circ$).

In the formula $\frac{a \cdot b}{\|a\|\,\|b\|}$, dividing by the product of the lengths $\|a\|\,\|b\|$ **normalizes** both vectors before taking their dot product, completely canceling out the scalar factor $2$:
$$\frac{a \cdot b}{\|a\|\,\|b\|} = \frac{a \cdot (2a)}{\|a\|\,\|2a\|} = \frac{2(a \cdot a)}{\|a\| \cdot (2\|a\|)} = \frac{2\|a\|^2}{2\|a\|^2} = 1.$$
Equivalently, both $a$ and $b$ normalize to the **exact same unit vector** $\hat{e} = \frac{a}{\|a\|} = \frac{b}{\|b\|} = \frac{1}{\sqrt{6}}(1, 2, 1)$, and the dot product of any unit vector with itself is $\|\hat{e}\|^2 = 1$. Therefore, $\frac{u \cdot v}{\|u\|\,\|v\|}$ measures **pure directional alignment** ($\cos\theta$), completely independent of vector lengths.

## Verification and Consistency Checks

1. **Cauchy-Schwarz Inequality Check ($-1 \le \frac{u \cdot v}{\|u\|\,\|v\|} \le 1$):**
   - For $(a, b)$: $\frac{a \cdot b}{\|a\|\,\|b\|} = 1 \in [-1, 1]$, attaining the upper bound $= 1$ if and only if one vector is a positive scalar multiple of the other ($b = 2a$). $\checkmark$
   - For $(a, c)$ and $(b, c)$: since $5^2 = 25 < 78 = (\sqrt{78})^2$, we have $0 < \frac{5}{\sqrt{78}} < 1$. $\checkmark$

2. **Cross-Product Check for $\sin\theta_{ac}$ and $\sin^2\theta_{ac} + \cos^2\theta_{ac} = 1$:**
   Computing $a \times c$ for $a = (1, 2, 1)$ and $c = (2, 0, 3)$:
   $$a \times c = ((2)(3) - (1)(0),\; (1)(2) - (1)(3),\; (1)(0) - (2)(2)) = (6, -1, -4).$$
   Then $\|a \times c\|^2 = 6^2 + (-1)^2 + (-4)^2 = 36 + 1 + 16 = 53$, so
   $$\sin^2\theta_{ac} = \frac{\|a \times c\|^2}{\|a\|^2\|c\|^2} = \frac{53}{6 \cdot 13} = \frac{53}{78}.$$
   Adding $\cos^2\theta_{ac} = \left(\frac{5}{\sqrt{78}}\right)^2 = \frac{25}{78}$ gives:
   $$\sin^2\theta_{ac} + \cos^2\theta_{ac} = \frac{53}{78} + \frac{25}{78} = \frac{78}{78} = 1. \quad \checkmark$$
