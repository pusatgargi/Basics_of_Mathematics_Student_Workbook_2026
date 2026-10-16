# Problem 6: Shifted Ellipse

## Problem Statement

Reduce
$$4x^2+9y^2-16x+18y-11=0$$
to canonical form. Give the center and semiaxis lengths. Check that substituting the coordinates of the center into the left-hand side gives a value consistent with the form you obtained.

## Theoretical Background and Concepts

When an **ellipse** with horizontal semiaxis $a > 0$ and vertical semiaxis $b > 0$ is translated (shifted) so that its center moves from the origin $(0,0)$ to a point $S = (x_0, y_0)$, its **canonical equation** becomes:
$$\frac{(x - x_0)^2}{a^2} + \frac{(y - y_0)^2}{b^2} = 1.$$
Geometrically, introducing translated coordinates $X = x - x_0$ and $Y = y - y_0$ places the new origin at $(x_0, y_0)$, in which the equation is simply $\frac{X^2}{a^2} + \frac{Y^2}{b^2} = 1$.

When expanded and multiplied by $a^2 b^2$, the shifted ellipse equation takes the **general form**:
$$Ax^2 + By^2 + Cx + Dy + E = 0,$$
where $A$ and $B$ have the **same sign** ($A > 0, B > 0$) and $A \neq B$.

To reduce such an equation to canonical form, we:
1. Group the $x$-terms and factor out the leading coefficient $A$ from the $x$-group; group the $y$-terms and factor out $B$ from the $y$-group.
2. **Complete the square** inside each parenthesis using $u^2 + bu = (u + b/2)^2 - (b/2)^2$.
3. Distribute $A$ and $B$ carefully across the completed squares (paying close attention to the subtracted constant terms $A(b_x/2)^2$ and $B(b_y/2)^2$).
4. Move the combined constant term to the right-hand side and divide both sides by that positive constant so that the right-hand side equals $1$.

Notice also that before dividing by the constant $K$, the completed-square form of the left-hand side is:
$$L(x, y) = A(x - x_0)^2 + B(y - y_0)^2 - K.$$
Evaluating the left-hand side $L(x, y)$ at the center $(x_0, y_0)$ makes both squared terms vanish, leaving $L(x_0, y_0) = -K$, which reaches the minimum value of the quadratic polynomial $L(x,y)$ and directly matches the constant moved to the right-hand side.

## Detailed Step-by-Step Solution

### Step 1: Group Terms and Factor Out Leading Coefficients
Start with the given equation:
$$4x^2 + 9y^2 - 16x + 18y - 11 = 0.$$
Group the $x$-terms together and the $y$-terms together:
$$(4x^2 - 16x) + (9y^2 + 18y) - 11 = 0.$$
Factor $4$ out of the $x$-terms and $9$ out of the $y$-terms:
$$4(x^2 - 4x) + 9(y^2 + 2y) - 11 = 0.$$

### Step 2: Complete the Square Inside Each Group
1. **For the $x$-expression $x^2 - 4x$:**
   Half of the linear coefficient $-4$ is $\frac{-4}{2} = -2$, and its square is $(-2)^2 = 4$:
   $$x^2 - 4x = (x^2 - 4x + 4) - 4 = (x - 2)^2 - 4.$$
   Multiplying by the outer factor $4$:
   $$4(x^2 - 4x) = 4\big((x - 2)^2 - 4\big) = 4(x - 2)^2 - 16.$$

2. **For the $y$-expression $y^2 + 2y$:**
   Half of the linear coefficient $2$ is $\frac{2}{2} = 1$, and its square is $1^2 = 1$:
   $$y^2 + 2y = (y^2 + 2y + 1) - 1 = (y + 1)^2 - 1.$$
   Multiplying by the outer factor $9$:
   $$9(y^2 + 2y) = 9\big((y + 1)^2 - 1\big) = 9(y + 1)^2 - 9.$$

### Step 3: Substitute Back and Normalize to Canonical Form
Substitute both completed-square expressions into the equation:
$$\big(4(x - 2)^2 - 16\big) + \big(9(y + 1)^2 - 9\big) - 11 = 0.$$
Combine all constant terms on the left-hand side ($-16 - 9 - 11 = -36$):
$$4(x - 2)^2 + 9(y + 1)^2 - 36 = 0.$$
Move $-36$ to the right-hand side:
$$4(x - 2)^2 + 9(y + 1)^2 = 36.$$
Divide every term on both sides by $36$ so that the right-hand side becomes $1$:
$$\frac{4(x - 2)^2}{36} + \frac{9(y + 1)^2}{36} = \frac{36}{36}$$
$$\frac{(x - 2)^2}{9} + \frac{(y + 1)^2}{4} = 1.$$
This is the **canonical form** of the shifted ellipse.

### Step 4: Identify the Center and Semiaxis Lengths
Comparing $\frac{(x - 2)^2}{9} + \frac{(y + 1)^2}{4} = 1$ with the standard shifted ellipse formula $\frac{(x - x_0)^2}{a^2} + \frac{(y - y_0)^2}{b^2} = 1$:
- $x_0 = 2$ and $y_0 = -1$ (since $y + 1 = y - (-1)$).
- $a^2 = 9 \implies a = \sqrt{9} = 3$ (horizontal semiaxis / semi-major axis).
- $b^2 = 4 \implies b = \sqrt{4} = 2$ (vertical semiaxis / semi-minor axis).

Thus:
- **Center:** $S = (2, -1)$.
- **Horizontal semiaxis length:** $a = 3$.
- **Vertical semiaxis length:** $b = 2$.
- **Vertices:** Moving $\pm 3$ horizontally from $(2,-1)$ gives $(-1, -1)$ and $(5, -1)$; moving $\pm 2$ vertically from $(2,-1)$ gives $(2, -3)$ and $(2, 1)$.

### Step 5: Check by Substituting the Center Coordinates into the Left-Hand Side
Let $L(x, y)$ denote the original left-hand side expression:
$$L(x, y) = 4x^2 + 9y^2 - 16x + 18y - 11.$$
From Step 3, before dividing by $36$, we showed that $L(x, y)$ is algebraically identical to the completed-square form:
$$L(x, y) = 4(x - 2)^2 + 9(y + 1)^2 - 36.$$

Now let us substitute the coordinates of the center $(x_0, y_0) = (2, -1)$ into both forms of $L(x, y)$:
1. **In the completed-square form:**
   $$L(2, -1) = 4(2 - 2)^2 + 9(-1 + 1)^2 - 36 = 4(0)^2 + 9(0)^2 - 36 = -36.$$
2. **In the original expanded left-hand side:**
   $$L(2, -1) = 4(2)^2 + 9(-1)^2 - 16(2) + 18(-1) - 11$$
   $$= 4(4) + 9(1) - 32 - 18 - 11$$
   $$= 16 + 9 - 32 - 18 - 11$$
   $$= 25 - 61 = -36.$$

Both evaluations yield the exact same value, **$-36$**, which is the negative of the right-hand side constant $36$ prior to dividing by $36$ (and corresponds to $\frac{0}{9} + \frac{0}{4} - 1 = -1$ after dividing by $36$). This confirms that the center coordinates $(2, -1)$ and the constant $36$ obtained during completing the square are completely consistent.

## Verification and Consistency Checks

1. **Test the Four Vertices of the Shifted Ellipse in the Original Equation:**
   - **Right vertex $(x_0 + a, y_0) = (5, -1)$:**
     $$L(5, -1) = 4(5)^2 + 9(-1)^2 - 16(5) + 18(-1) - 11 = 100 + 9 - 80 - 18 - 11 = 109 - 109 = 0. \quad \checkmark$$
   - **Left vertex $(x_0 - a, y_0) = (-1, -1)$:**
     $$L(-1, -1) = 4(-1)^2 + 9(-1)^2 - 16(-1) + 18(-1) - 11 = 4 + 9 + 16 - 18 - 11 = 29 - 29 = 0. \quad \checkmark$$
   - **Top vertex $(x_0, y_0 + b) = (2, 1)$:**
     $$L(2, 1) = 4(2)^2 + 9(1)^2 - 16(2) + 18(1) - 11 = 16 + 9 - 32 + 18 - 11 = 43 - 43 = 0. \quad \checkmark$$
   - **Bottom vertex $(x_0, y_0 - b) = (2, -3)$:**
     $$L(2, -3) = 4(2)^2 + 9(-3)^2 - 16(2) + 18(-3) - 11 = 16 + 81 - 32 - 54 - 11 = 97 - 97 = 0. \quad \checkmark$$
