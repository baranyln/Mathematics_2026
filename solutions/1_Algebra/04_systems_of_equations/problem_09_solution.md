# Problem 09 Solution

## Problem Statement
Find numbers $x,y$ satisfying

$$
x+y=10,\qquad 2x+5y=32.
$$

Solve the system and explain geometrically why the solution is unique.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Linear Systems as Intersecting Geometric Objects: In two dimensions, every linear equation $a_i x + b_i y = c_i$ defines a straight line.
- Uniqueness Condition: A system of two linear equations in two unknowns has a unique solution if and only if the lines are not parallel, which occurs when their slopes differ ($m_1 \neq m_2$), or equivalently, when the determinant of the coefficient matrix is non-zero ($\det A \neq 0$).
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 5 (`cases` environment with rows on separate lines ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **System Setup & Matrix Formulation:**
We write the system of equations in standard form:

$$
\begin{cases}
x + y = 10, \\
2x + 5y = 32.
\end{cases}
$$

We formulate the augmented matrix $[A \mid b]$:

$$
\begin{pmatrix}
1 & 1 & \mid & 10 \\
2 & 5 & \mid & 32 \\
\end{pmatrix}.
$$

2. **Intermediate Steps:**
We eliminate the unknown $x$ from the second row using the elementary row operation $R_2 \leftarrow R_2 - 2R_1$.

We compute the entries of the new Row 2:

$$
\begin{aligned}
r_{21} &= 2 - 2(1) = 2 - 2 = 0 \\
r_{22} &= 5 - 2(1) = 5 - 2 = 3 \\
r_{23} &= 32 - 2(10) = 32 - 20 = 12
\end{aligned}
$$

The augmented matrix in row echelon form is:

$$
\begin{pmatrix}
1 & 1 & \mid & 10 \\
0 & 3 & \mid & 12 \\
\end{pmatrix}.
$$

3. **Variable Evaluation & Geometric Explanation:**
**Back-Substitution:**
- From Row 2:

$$
3y = 12 \implies y = \frac{12}{3} = 4
$$

- From Row 1:

$$
x + y = 10
$$

Substituting $y = 4$:

$$
x + 4 = 10 \implies x = 10 - 4 = 6
$$

Thus, the unique algebraic solution is $(x, y) = (6, 4)$.

**Consistency Check:**
- In Equation 1: $6 + 4 = 10$. Holds.
- In Equation 2: $2(6) + 5(4) = 12 + 20 = 32$. Holds.

**Geometric Explanation of Uniqueness:**
In the Cartesian plane $\mathbb{R}^2$, each linear equation represents a straight line.
We express each equation in slope-intercept form ($y = mx + k$):
- For Line $L_1$:

$$
x + y = 10 \implies y = -x + 10
$$

The slope of $L_1$ is $m_1 = -1$.
- For Line $L_2$:

$$
2x + 5y = 32 \implies 5y = -2x + 32 \implies y = -\frac{2}{5}x + \frac{32}{5}
$$

The slope of $L_2$ is $m_2 = -\frac{2}{5}$.

Comparing the slopes:

$$
m_1 = -1 \neq -\frac{2}{5} = m_2.
$$

Because the two lines have distinct slopes, they are not parallel. In Euclidean geometry, any two non-parallel lines in a two-dimensional plane intersect at exactly one unique point. That single intersection point is $(x, y) = (6, 4)$.

Algebraically, this corresponds to the non-vanishing of the determinant of the coefficient matrix:

$$
\det A = (1)(5) - (1)(2) = 5 - 2 = 3 \neq 0.
$$

Since $\det A \neq 0$, the matrix has full rank ($\mathrm{rank}(A) = 2$), which confirms that the solution is unique.

## Final Answer

$$
x = 6, \quad y = 4
$$
