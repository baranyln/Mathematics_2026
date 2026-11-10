# Problem 04 Solution

## Problem Statement
Solve

$$
\begin{cases}
x+y+z=2, \\
2x+2y+2z=4, \\
x-y+z=0.
\end{cases}
$$

Give the solution in parametric form, identify a free variable, and for one chosen parameter value check that the resulting point really satisfies the system.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Underdetermined / Dependent Systems: When Gaussian elimination produces a row of zeros with $\mathrm{rank}(A) = \mathrm{rank}([A \mid b]) < n$, the system is consistent and has infinitely many solutions.
- Free Variables & Parametric Form: Columns without a leading pivot correspond to free variables that may be assigned arbitrary real parameters. The leading (pivot) variables are then expressed in terms of these parameters.
- Point Verification: Substituting a specific parameter value into the parametric representation generates a point that must satisfy all original equations.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 5 (`cases` environment with rows on separate lines ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **System Setup & Matrix Formulation:**
We are given the system:

$$
\begin{cases}
x + y + z = 2, \\
2x + 2y + 2z = 4, \\
x - y + z = 0.
\end{cases}
$$

We formulate the augmented matrix $[A \mid b]$:

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 2 \\
2 & 2 & 2 & \mid & 4 \\
1 & -1 & 1 & \mid & 0 \\
\end{pmatrix}.
$$

2. **Intermediate Steps:**
**Step 1: Eliminate entry $(2,1)$ using operation $R_2 \leftarrow R_2 - 2R_1$**
We compute the new entries of Row 2:

$$
\begin{aligned}
r_{21} &= 2 - 2(1) = 2 - 2 = 0 \\
r_{22} &= 2 - 2(1) = 2 - 2 = 0 \\
r_{23} &= 2 - 2(1) = 2 - 2 = 0 \\
r_{24} &= 4 - 2(2) = 4 - 4 = 0
\end{aligned}
$$

Row 2 becomes $\begin{pmatrix} 0 & 0 & 0 & \mid & 0 \end{pmatrix}$.

**Step 2: Eliminate entry $(3,1)$ using operation $R_3 \leftarrow R_3 - R_1$**
We compute the new entries of Row 3:

$$
\begin{aligned}
r_{31} &= 1 - 1 = 0 \\
r_{32} &= -1 - 1 = -2 \\
r_{33} &= 1 - 1 = 0 \\
r_{34} &= 0 - 2 = -2
\end{aligned}
$$

Row 3 becomes $\begin{pmatrix} 0 & -2 & 0 & \mid & -2 \end{pmatrix}$.
The augmented matrix is now:

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 2 \\
0 & 0 & 0 & \mid & 0 \\
0 & -2 & 0 & \mid & -2 \\
\end{pmatrix}.
$$

**Step 3: Interchange Row 2 and Row 3 ($R_2 \leftrightarrow R_3$) to place the non-zero row above the zero row**

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 2 \\
0 & -2 & 0 & \mid & -2 \\
0 & 0 & 0 & \mid & 0 \\
\end{pmatrix}.
$$

**Step 4: Scale Row 2 using operation $R_2 \leftarrow -\frac{1}{2} R_2$**

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 2 \\
0 & 1 & 0 & \mid & 1 \\
0 & 0 & 0 & \mid & 0 \\
\end{pmatrix}.
$$

**Step 5: Eliminate entry $(1,2)$ using operation $R_1 \leftarrow R_1 - R_2$**
We compute the new entries of Row 1:

$$
\begin{aligned}
r_{11} &= 1 - 0 = 1 \\
r_{12} &= 1 - 1 = 0 \\
r_{13} &= 1 - 0 = 1 \\
r_{14} &= 2 - 1 = 1
\end{aligned}
$$

The augmented matrix in reduced row echelon form (RREF) is:

$$
\begin{pmatrix}
1 & 0 & 1 & \mid & 1 \\
0 & 1 & 0 & \mid & 1 \\
0 & 0 & 0 & \mid & 0 \\
\end{pmatrix}.
$$

3. **Variable Evaluation & Consistency Check:**
**Identification of Free Variables:**
- Column 1 has a leading pivot in Row 1, corresponding to leading variable $x$.
- Column 2 has a leading pivot in Row 2, corresponding to leading variable $y$.
- Column 3 contains no leading pivot, which means variable $z$ is a **free variable**.

**Parametric Solution:**
Let $z = t$, where $t \in \mathbb{R}$ is an arbitrary parameter.
- From Row 2:

$$
y = 1
$$

- From Row 1:

$$
x + z = 1 \implies x = 1 - z = 1 - t
$$

Thus, the general solution in parametric form is:

$$
x = 1 - t, \qquad y = 1, \qquad z = t, \qquad t \in \mathbb{R}
$$

In vector notation:

$$
\begin{pmatrix}
x \\
y \\
z \\
\end{pmatrix} =
\begin{pmatrix}
1 \\
1 \\
0 \\
\end{pmatrix}
+ t
\begin{pmatrix}
-1 \\
0 \\
1 \\
\end{pmatrix}, \qquad t \in \mathbb{R}.
$$

Since $t$ can be any real number, the system has **infinitely many solutions**.

**Point Verification for a Chosen Parameter Value ($t = 1$):**
Choosing $t = 1$ yields the particular solution point:

$$
x = 1 - (1) = 0, \qquad y = 1, \qquad z = 1.
$$

We substitute $(x, y, z) = (0, 1, 1)$ into all three original equations:
- Equation 1 ($x + y + z = 2$):

$$
0 + 1 + 1 = 2.
$$

Equality holds ($2 = 2$).
- Equation 2 ($2x + 2y + 2z = 4$):

$$
2(0) + 2(1) + 2(1) = 0 + 2 + 2 = 4.
$$

Equality holds ($4 = 4$).
- Equation 3 ($x - y + z = 0$):

$$
0 - 1 + 1 = 0.
$$

Equality holds ($0 = 0$).

All three equations are satisfied, confirming the validity of the parametric solution.

## Final Answer

The system has infinitely many solutions with free variable $z = t$:

$$
\begin{pmatrix}
x \\
y \\
z \\
\end{pmatrix} =
\begin{pmatrix}
1 - t \\
1 \\
t \\
\end{pmatrix}, \qquad t \in \mathbb{R}
$$
