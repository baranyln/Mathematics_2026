# Problem 02 Solution

## Problem Statement
Solve using Gaussian elimination:

$$
\begin{cases}
x+y+z=6, \\
2x-y+z=3, \\
x+2y-z=2.
\end{cases}
$$

After solving, substitute the result into all equations and check consistency.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Gaussian Elimination: Represent the linear system as an augmented matrix $[A \mid b]$. Apply elementary row operations ($R_i \leftarrow R_i + c R_j$, $R_i \leftrightarrow R_j$, $R_i \leftarrow c R_i$) to transform the coefficient block into row echelon form (upper triangular form).
- Back-Substitution: Solve for the unknowns sequentially starting from the bottom row.
- Consistency Check: Substitute the evaluated solution vector into all original equations to verify that each equality is satisfied.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 5 (`cases` environment with rows on separate lines ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **System Setup & Matrix Formulation:**
We write the linear system:

$$
\begin{cases}
x + y + z = 6, \\
2x - y + z = 3, \\
x + 2y - z = 2.
\end{cases}
$$

We formulate the augmented matrix $[A \mid b]$:

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 6 \\
2 & -1 & 1 & \mid & 3 \\
1 & 2 & -1 & \mid & 2 \\
\end{pmatrix}.
$$

2. **Intermediate Steps:**
**Step 1: Eliminate entry $(2,1)$ using operation $R_2 \leftarrow R_2 - 2R_1$**
We compute the new entries of Row 2:

$$
\begin{aligned}
r_{21} &= 2 - 2(1) = 2 - 2 = 0 \\
r_{22} &= -1 - 2(1) = -1 - 2 = -3 \\
r_{23} &= 1 - 2(1) = 1 - 2 = -1 \\
r_{24} &= 3 - 2(6) = 3 - 12 = -9
\end{aligned}
$$

Row 2 becomes $\begin{pmatrix} 0 & -3 & -1 & \mid & -9 \end{pmatrix}$.

**Step 2: Eliminate entry $(3,1)$ using operation $R_3 \leftarrow R_3 - R_1$**
We compute the new entries of Row 3:

$$
\begin{aligned}
r_{31} &= 1 - 1 = 0 \\
r_{32} &= 2 - 1 = 1 \\
r_{33} &= -1 - 1 = -2 \\
r_{34} &= 2 - 6 = -4
\end{aligned}
$$

Row 3 becomes $\begin{pmatrix} 0 & 1 & -2 & \mid & -4 \end{pmatrix}$.
The augmented matrix is now:

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 6 \\
0 & -3 & -1 & \mid & -9 \\
0 & 1 & -2 & \mid & -4 \\
\end{pmatrix}.
$$

**Step 3: Interchange Row 2 and Row 3 ($R_2 \leftrightarrow R_3$) to obtain a pivot of 1**
Swapping Row 2 and Row 3:

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 6 \\
0 & 1 & -2 & \mid & -4 \\
0 & -3 & -1 & \mid & -9 \\
\end{pmatrix}.
$$

**Step 4: Eliminate entry $(3,2)$ using operation $R_3 \leftarrow R_3 + 3R_2$**
We compute the new entries of Row 3:

$$
\begin{aligned}
r_{31} &= 0 + 3(0) = 0 \\
r_{32} &= -3 + 3(1) = -3 + 3 = 0 \\
r_{33} &= -1 + 3(-2) = -1 - 6 = -7 \\
r_{34} &= -9 + 3(-4) = -9 - 12 = -21
\end{aligned}
$$

The augmented matrix in row echelon form is:

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 6 \\
0 & 1 & -2 & \mid & -4 \\
0 & 0 & -7 & \mid & -21 \\
\end{pmatrix}.
$$

3. **Variable Evaluation & Consistency Check:**
**Back-Substitution:**
- From Row 3:

$$
-7z = -21 \implies z = \frac{-21}{-7} = 3
$$

- From Row 2:

$$
y - 2z = -4
$$

Substituting $z = 3$:

$$
y - 2(3) = -4 \implies y - 6 = -4 \implies y = 2
$$

- From Row 1:

$$
x + y + z = 6
$$

Substituting $y = 2$ and $z = 3$:

$$
x + 2 + 3 = 6 \implies x + 5 = 6 \implies x = 1
$$

The system has a unique solution: $(x, y, z) = (1, 2, 3)$.

**Consistency Check (Verification in all original equations):**
- In Equation 1 ($x + y + z = 6$):

$$
1 + 2 + 3 = 6.
$$

Equality holds ($6 = 6$).
- In Equation 2 ($2x - y + z = 3$):

$$
2(1) - 2 + 3 = 2 - 2 + 3 = 3.
$$

Equality holds ($3 = 3$).
- In Equation 3 ($x + 2y - z = 2$):

$$
1 + 2(2) - 3 = 1 + 4 - 3 = 2.
$$

Equality holds ($2 = 2$).

All three equations are satisfied, confirming consistency.

## Final Answer

$$
x = 1, \quad y = 2, \quad z = 3
$$
