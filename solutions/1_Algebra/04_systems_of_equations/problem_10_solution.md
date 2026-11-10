# Problem 10 Solution

## Problem Statement
Find a polynomial $p(x)=ax^2+bx+c$ whose graph passes through $(0,1)$, $(1,3)$, and $(2,9)$. Reduce the problem to a system of equations and check the result by substituting all three points.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Polynomial Interpolation via Linear Systems: Fitting a polynomial of degree $n$ through $n+1$ points $(x_i, y_i)$ translates to a system of linear equations in the unknown polynomial coefficients $(a, b, c)$, structured as a Vandermonde system.
- Gaussian Elimination: Reduce the augmented matrix to row echelon form to determine the unique coefficient values.
- Consistency Check: Substitute the coordinates of all original interpolation points into the resulting polynomial function $p(x)$ to verify exact matching.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 5 (`cases` environment with rows on separate lines ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **System Setup & Matrix Formulation:**
The quadratic polynomial is given by:

$$
p(x) = ax^2 + bx + c.
$$

The graph of $p(x)$ passes through three given points $(x_i, y_i)$:
- Point $(0, 1)$:

$$
p(0) = a(0)^2 + b(0) + c = 1 \implies 0a + 0b + c = 1
$$

- Point $(1, 3)$:

$$
p(1) = a(1)^2 + b(1) + c = 3 \implies a + b + c = 3
$$

- Point $(2, 9)$:

$$
p(2) = a(2)^2 + b(2) + c = 9 \implies 4a + 2b + c = 9
$$

Arranging these equations into standard order for the unknowns $a, b, c$:

$$
\begin{cases}
a + b + c = 3, \\
4a + 2b + c = 9, \\
c = 1.
\end{cases}
$$

We formulate the augmented matrix:

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 3 \\
4 & 2 & 1 & \mid & 9 \\
0 & 0 & 1 & \mid & 1 \\
\end{pmatrix}.
$$

2. **Intermediate Steps:**
We eliminate the entry in Row 2, Column 1 using the elementary row operation $R_2 \leftarrow R_2 - 4R_1$.

We compute the entries of the new Row 2:

$$
\begin{aligned}
r_{21} &= 4 - 4(1) = 4 - 4 = 0 \\
r_{22} &= 2 - 4(1) = 2 - 4 = -2 \\
r_{23} &= 1 - 4(1) = 1 - 4 = -3 \\
r_{24} &= 9 - 4(3) = 9 - 12 = -3
\end{aligned}
$$

The augmented matrix in row echelon form is:

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 3 \\
0 & -2 & -3 & \mid & -3 \\
0 & 0 & 1 & \mid & 1 \\
\end{pmatrix}.
$$

3. **Variable Evaluation & Consistency Check:**
**Back-Substitution:**
- From Row 3:

$$
c = 1
$$

- From Row 2:

$$
-2b - 3c = -3
$$

Substituting $c = 1$:

$$
-2b - 3(1) = -3 \implies -2b - 3 = -3 \implies -2b = 0 \implies b = 0
$$

- From Row 1:

$$
a + b + c = 3
$$

Substituting $b = 0$ and $c = 1$:

$$
a + 0 + 1 = 3 \implies a + 1 = 3 \implies a = 2
$$

The unique coefficients are $a = 2$, $b = 0$, and $c = 1$.
The polynomial is:

$$
p(x) = 2x^2 + 1.
$$

**Consistency Check (Evaluating $p(x)$ at the three points):**
- At $x = 0$:

$$
p(0) = 2(0)^2 + 1 = 0 + 1 = 1.
$$

Matches $(0, 1)$.
- At $x = 1$:

$$
p(1) = 2(1)^2 + 1 = 2(1) + 1 = 3.
$$

Matches $(1, 3)$.
- At $x = 2$:

$$
p(2) = 2(2)^2 + 1 = 2(4) + 1 = 8 + 1 = 9.
$$

Matches $(2, 9)$.

All three points lie on the graph of the polynomial, confirming consistency.

## Final Answer

$$
p(x) = 2x^2 + 1
$$

The coefficients are:

$$
a = 2, \quad b = 0, \quad c = 1
$$
