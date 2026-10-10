# Problem 14: Rotation Matrices

## Problem Statement
The matrix for a rotation through an angle $\theta$ is

$$R(\theta)=\begin{pmatrix}\cos\theta&-\sin\theta\\\sin\theta&\cos\theta\end{pmatrix}.$$
Compute $R(\alpha)R(\beta)$ and, using the angle-sum formulas for sine and cosine, show that

$$R(\alpha)R(\beta)=R(\alpha+\beta).$$
Explain the result geometrically.

## Theoretical Background and Concepts
Rotations in the plane can be represented by matrices. The product of two rotation matrices corresponds to rotating by the sum of the angles.

## Detailed Step-by-Step Solution
First multiply:

$$R(\alpha)R(\beta)=
\begin{pmatrix}\cos\alpha&-\sin\alpha\\\sin\alpha&\cos\alpha\end{pmatrix}
\begin{pmatrix}\cos\beta&-\sin\beta\\\sin\beta&\cos\beta\end{pmatrix}.$$

Using row-by-column multiplication,

$$R(\alpha)R(\beta)=
\begin{pmatrix}
\cos\alpha\cos\beta-\sin\alpha\sin\beta & -\cos\alpha\sin\beta-\sin\alpha\cos\beta \\
\sin\alpha\cos\beta+\cos\alpha\sin\beta & -\sin\alpha\sin\beta+\cos\alpha\cos\beta
\end{pmatrix}.$$

Now use the angle-sum identities:

$$\cos(\alpha+\beta)=\cos\alpha\cos\beta-\sin\alpha\sin\beta,$$

$$\sin(\alpha+\beta)=\sin\alpha\cos\beta+\cos\alpha\sin\beta.$$

Thus the matrix becomes

$$R(\alpha)R(\beta)=
\begin{pmatrix}
\cos(\alpha+\beta)&-\sin(\alpha+\beta)\\
\sin(\alpha+\beta)&\cos(\alpha+\beta)
\end{pmatrix}
=R(\alpha+\beta).$$

## Geometric Interpretation
Composing two rotations by angles $\alpha$ and $\beta$ is equivalent to a single rotation by the total angle $\alpha+\beta$. This is why the product of rotation matrices corresponds to adding angles.

## Verification and Consistency Checks
The identity matches the standard angle-sum formulas exactly, so the matrix algebra agrees with the geometry of rotations.
