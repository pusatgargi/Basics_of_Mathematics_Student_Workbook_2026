# Problem 3: Recognizing Basic Antiderivatives

## Problem Statement

Compute
$$\int\left(2e^x+3\cos x-4\sin x\right)\,dx.$$
Match each term with a known derivative and verify the entire result with one differentiation.

## Theoretical Background and Concepts

- **Antiderivatives as Reversed Derivative Formulas**: Every standard differentiation formula immediately yields a corresponding basic integration formula:
  $$F'(x) = f(x) \iff \int f(x)\,dx = F(x) + C.$$
  In particular, for exponential and trigonometric functions:
  - Since $\frac{d}{dx}(e^x) = e^x$, we have $\int e^x\,dx = e^x + C$.
  - Since $\frac{d}{dx}(\sin x) = \cos x$, we have $\int \cos x\,dx = \sin x + C$.
  - Since $\frac{d}{dx}(\cos x) = -\sin x$, multiplying by $-1$ gives $\frac{d}{dx}(-\cos x) = \sin x$, so $\int \sin x\,dx = -\cos x + C$.
- **Constant of Integration $C$ and Linearity**: Because $\frac{d}{dx}[C] = 0$, the indefinite integral represents a family of vertically shifted functions differing by $C \in \mathbb{R}$. By linearity, constants factor out of integrals and sums integrate term-by-term:
  $$\int \bigl(c_1 f_1(x) + c_2 f_2(x) + c_3 f_3(x)\bigr)\,dx = c_1\int f_1(x)\,dx + c_2\int f_2(x)\,dx + c_3\int f_3(x)\,dx.$$
- **Overview of Integration Methods and Interpretation**: When basic antiderivative tables and the power rule ($\int x^n\,dx = \frac{x^{n+1}}{n+1}+C$) are not directly applicable, we use $u$-substitution (reversing the chain rule for composite functions) or integration by parts (reversing the product rule for products of functions). When limits of integration are given, the Newton-Leibniz theorem $\int_a^b f(x)\,dx = F(b)-F(a)$ computes the net signed area rather than the unsigned geometric area $\int_a^b |f(x)|\,dx$.

## Detailed Step-by-Step Solution

### 1. Recognizing the Integration Method
The integrand $f(x) = 2e^x + 3\cos x - 4\sin x$ is a linear combination of three elementary transcendental functions ($e^x$, $\cos x$, and $\sin x$) whose arguments are simply $x$ (no composite inner functions and no products of functions of $x$). Therefore, **direct integration** using the table of elementary derivatives and the **linearity of the integral** is the appropriate method.

### 2. Matching Each Term with a Known Derivative
We match each elementary function in the integrand with the function of which it is the derivative:

| Term in Integrand | Known Differentiation Rule | Corresponding Antiderivative |
| :--- | :--- | :--- |
| $e^x$ | $\frac{d}{dx}\left(e^x\right) = e^x$ | $\int e^x\,dx = e^x$ |
| $\cos x$ | $\frac{d}{dx}\left(\sin x\right) = \cos x$ | $\int \cos x\,dx = \sin x$ |
| $\sin x$ | $\frac{d}{dx}\left(-\cos x\right) = -(-\sin x) = \sin x$ | $\int \sin x\,dx = -\cos x$ |

*(Note the sign on the third term: differentiating $\cos x$ produces $-\sin x$, so differentiating $-\cos x$ produces $+\sin x$, and differentiating $+4\cos x$ produces $-4\sin x$.)*

### 3. Computing the Indefinite Integral
Applying the linearity property of the indefinite integral:
$$\begin{aligned}
\int\left(2e^x + 3\cos x - 4\sin x\right)\,dx &= 2\int e^x\,dx + 3\int \cos x\,dx - 4\int \sin x\,dx \\
&= 2\left(e^x\right) + 3\left(\sin x\right) - 4\left(-\cos x\right) + C \\
&= 2e^x + 3\sin x + 4\cos x + C, \quad C \in \mathbb{R}.
\end{aligned}$$

## Verification and Consistency Checks

We verify the entire result $F(x) = 2e^x + 3\sin x + 4\cos x + C$ with a single differentiation with respect to $x$:

$$\begin{aligned}
F'(x) &= \frac{d}{dx}\left(2e^x + 3\sin x + 4\cos x + C\right) \\
&= 2\frac{d}{dx}\left(e^x\right) + 3\frac{d}{dx}\left(\sin x\right) + 4\frac{d}{dx}\left(\cos x\right) + \frac{d}{dx}(C) \\
&= 2e^x + 3(\cos x) + 4(-\sin x) + 0 \\
&= 2e^x + 3\cos x - 4\sin x.
\end{aligned}$$

The derivative $F'(x)$ reproduces the original integrand $2e^x + 3\cos x - 4\sin x$ with all coefficients and signs matching exactly.
