# Problem 11 Solution

## Problem Statement
Analyze the number of solutions depending on $t$:

$$
\begin{cases}
x+y+z=1, \\
x+ty+z=2, \\
x+y+tz=3.
\end{cases}
$$

Use elimination and separately analyze the parameter values for which a standard calculation step ceases to be valid.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Parametric Gaussian Elimination: Apply row operations on the augmented matrix $[A(t) \mid b]$ and identify critical parameter values where division by a pivot term ceases to be defined (division by zero).
- Critical Parameter Analysis: At critical parameter values, substitute the value directly into the eliminated matrix to test consistency (Rouché-Capelli Theorem).
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 5 (`cases` environment with rows on separate lines ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **System Setup & Matrix Formulation:**
We are given the parameterized linear system with parameter $t \in \mathbb{R}$:

$$
\begin{cases}
x + y + z = 1, \\
x + ty + z = 2, \\
x + y + tz = 3.
\end{cases}
$$

We formulate the augmented matrix $[A(t) \mid b]$:

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 1 \\
1 & t & 1 & \mid & 2 \\
1 & 1 & t & \mid & 3 \\
\end{pmatrix}.
$$

2. **Intermediate Steps:**
**Step 1: Eliminate entry $(2,1)$ using operation $R_2 \leftarrow R_2 - R_1$**
We compute the new entries of Row 2:

$$
\begin{aligned}
r_{21} &= 1 - 1 = 0 \\
r_{22} &= t - 1 \\
r_{23} &= 1 - 1 = 0 \\
r_{24} &= 2 - 1 = 1
\end{aligned}
$$

Row 2 becomes $\begin{pmatrix} 0 & t - 1 & 0 & \mid & 1 \end{pmatrix}$.

**Step 2: Eliminate entry $(3,1)$ using operation $R_3 \leftarrow R_3 - R_1$**
We compute the new entries of Row 3:

$$
\begin{aligned}
r_{31} &= 1 - 1 = 0 \\
r_{32} &= 1 - 1 = 0 \\
r_{33} &= t - 1 \\
r_{34} &= 3 - 1 = 2
\end{aligned}
$$

Row 3 becomes $\begin{pmatrix} 0 & 0 & t - 1 & \mid & 2 \end{pmatrix}$.

The augmented matrix in triangular row echelon form is:

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 1 \\
0 & t - 1 & 0 & \mid & 1 \\
0 & 0 & t - 1 & \mid & 2 \\
\end{pmatrix}.
$$

3. **Variable Evaluation & Case Analysis:**
The standard back-substitution procedure requires dividing by the pivot coefficient $t - 1$.
This algebraic step ceases to be valid when:

$$
t - 1 = 0 \iff t = 1.
$$

We separately analyze the critical case $t = 1$ and the non-critical case $t \neq 1$:

- **Case 1: Critical Value $t = 1$**
  Substituting $t = 1$ directly into the row-reduced augmented matrix gives:

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 1 \\
0 & 0 & 0 & \mid & 1 \\
0 & 0 & 0 & \mid & 2 \\
\end{pmatrix}.
$$

  Row 2 represents the equation:

$$
0x + 0y + 0z = 1 \implies 0 = 1.
$$

  Row 3 represents the equation:

$$
0x + 0y + 0z = 2 \implies 0 = 2.
$$

  Both rows produce contradictions.
  In terms of matrix ranks:

$$
\mathrm{rank}(A(1)) = 1, \qquad \mathrm{rank}([A(1) \mid b]) = 3.
$$

  Because $\mathrm{rank}(A) < \mathrm{rank}([A \mid b])$, the system is inconsistent.
  Therefore, for $t = 1$, the system has **no solution**.

- **Case 2: General Case $t \neq 1$**
  When $t \neq 1$, the term $t - 1$ is non-zero, so division by $t - 1$ is valid.
  The matrix has 3 non-zero rows, meaning:

$$
\mathrm{rank}(A(t)) = \mathrm{rank}([A(t) \mid b]) = 3.
$$

  Because the rank equals the number of unknowns ($n = 3$), the system has **exactly one unique solution**.
  We carry out back-substitution:
  - From Row 3:

$$
(t - 1)z = 2 \implies z = \frac{2}{t - 1}
$$

  - From Row 2:

$$
(t - 1)y = 1 \implies y = \frac{1}{t - 1}
$$

  - From Row 1:

$$
x + y + z = 1 \implies x = 1 - y - z
$$

  Substituting $y$ and $z$:

$$
\begin{aligned}
x &= 1 - \frac{1}{t - 1} - \frac{2}{t - 1} \\
  &= 1 - \frac{3}{t - 1} \\
  &= \frac{(t - 1) - 3}{t - 1} \\
  &= \frac{t - 4}{t - 1}
\end{aligned}
$$

**Consistency Check for $t \neq 1$ (substituting into original equations):**
- Equation 1:

$$
\frac{t - 4}{t - 1} + \frac{1}{t - 1} + \frac{2}{t - 1} = \frac{t - 4 + 1 + 2}{t - 1} = \frac{t - 1}{t - 1} = 1.
$$

- Equation 2:

$$
\frac{t - 4}{t - 1} + t\left(\frac{1}{t - 1}\right) + \frac{2}{t - 1} = \frac{t - 4 + t + 2}{t - 1} = \frac{2t - 2}{t - 1} = \frac{2(t - 1)}{t - 1} = 2.
$$

- Equation 3:

$$
\frac{t - 4}{t - 1} + \frac{1}{t - 1} + t\left(\frac{2}{t - 1}\right) = \frac{t - 4 + 1 + 2t}{t - 1} = \frac{3t - 3}{t - 1} = \frac{3(t - 1)}{t - 1} = 3.
$$

All three equations hold.

## Final Answer

- **For $t = 1$:** The system has **no solution** (inconsistent).
- **For $t \neq 1$:** The system has **exactly one unique solution**:

$$
x = \frac{t - 4}{t - 1}, \quad y = \frac{1}{t - 1}, \quad z = \frac{2}{t - 1}
$$
