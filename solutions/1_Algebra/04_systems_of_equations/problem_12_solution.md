# Problem 12 Solution

## Problem Statement
Solve

$$
\begin{cases}
x+2y-z=0, \\
2x+4y-2z=0, \\
x-y+2z=0.
\end{cases}
$$

Give all solutions in parametric form and explain why $(0,0,0)$ always satisfies a homogeneous system.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Homogeneous Linear Systems ($Ax = 0$): A linear system with a right-hand side of all zeros is always consistent because the trivial solution $x = 0$ satisfies $A \cdot 0 = 0$.
- Non-Trivial Solutions: If $\mathrm{rank}(A) < n$, the nullspace (kernel) contains infinitely many non-zero solutions, which are represented in parametric vector form using free variables.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 5 (`cases` environment with rows on separate lines ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **System Setup & Matrix Formulation:**
We are given the homogeneous system:

$$
\begin{cases}
x + 2y - z = 0, \\
2x + 4y - 2z = 0, \\
x - y + 2z = 0.
\end{cases}
$$

We formulate the augmented matrix $[A \mid 0]$:

$$
\begin{pmatrix}
1 & 2 & -1 & \mid & 0 \\
2 & 4 & -2 & \mid & 0 \\
1 & -1 & 2 & \mid & 0 \\
\end{pmatrix}.
$$

2. **Intermediate Steps:**
**Step 1: Eliminate entry $(2,1)$ using operation $R_2 \leftarrow R_2 - 2R_1$**
We compute the entries of the new Row 2:

$$
\begin{aligned}
r_{21} &= 2 - 2(1) = 2 - 2 = 0 \\
r_{22} &= 4 - 2(2) = 4 - 4 = 0 \\
r_{23} &= -2 - 2(-1) = -2 + 2 = 0 \\
r_{24} &= 0 - 2(0) = 0
\end{aligned}
$$

Row 2 becomes $\begin{pmatrix} 0 & 0 & 0 & \mid & 0 \end{pmatrix}$.

**Step 2: Eliminate entry $(3,1)$ using operation $R_3 \leftarrow R_3 - R_1$**
We compute the entries of the new Row 3:

$$
\begin{aligned}
r_{31} &= 1 - 1 = 0 \\
r_{32} &= -1 - 2 = -3 \\
r_{33} &= 2 - (-1) = 2 + 1 = 3 \\
r_{34} &= 0 - 0 = 0
\end{aligned}
$$

Row 3 becomes $\begin{pmatrix} 0 & -3 & 3 & \mid & 0 \end{pmatrix}$.
The augmented matrix is now:

$$
\begin{pmatrix}
1 & 2 & -1 & \mid & 0 \\
0 & 0 & 0 & \mid & 0 \\
0 & -3 & 3 & \mid & 0 \\
\end{pmatrix}.
$$

**Step 3: Interchange Row 2 and Row 3 ($R_2 \leftrightarrow R_3$)**

$$
\begin{pmatrix}
1 & 2 & -1 & \mid & 0 \\
0 & -3 & 3 & \mid & 0 \\
0 & 0 & 0 & \mid & 0 \\
\end{pmatrix}.
$$

**Step 4: Scale Row 2 using operation $R_2 \leftarrow -\frac{1}{3} R_2$**

$$
\begin{pmatrix}
1 & 2 & -1 & \mid & 0 \\
0 & 1 & -1 & \mid & 0 \\
0 & 0 & 0 & \mid & 0 \\
\end{pmatrix}.
$$

**Step 5: Eliminate entry $(1,2)$ using operation $R_1 \leftarrow R_1 - 2R_2$**
We compute the entries of the new Row 1:

$$
\begin{aligned}
r_{11} &= 1 - 2(0) = 1 \\
r_{12} &= 2 - 2(1) = 0 \\
r_{13} &= -1 - 2(-1) = -1 + 2 = 1 \\
r_{14} &= 0 - 2(0) = 0
\end{aligned}
$$

The augmented matrix in reduced row echelon form (RREF) is:

$$
\begin{pmatrix}
1 & 0 & 1 & \mid & 0 \\
0 & 1 & -1 & \mid & 0 \\
0 & 0 & 0 & \mid & 0 \\
\end{pmatrix}.
$$

3. **Variable Evaluation & Explanation:**
**Parametric Solution:**
- From Row 1:

$$
x + z = 0 \implies x = -z
$$

- From Row 2:

$$
y - z = 0 \implies y = z
$$

- Column 3 contains no pivot, so $z$ is the free variable.
Let $z = t$, where $t \in \mathbb{R}$ is an arbitrary parameter.
The general solution in parametric form is:

$$
x = -t, \qquad y = t, \qquad z = t, \qquad t \in \mathbb{R}
$$

In vector form:

$$
\begin{pmatrix}
x \\
y \\
z \\
\end{pmatrix}
= t
\begin{pmatrix}
-1 \\
1 \\
1 \\
\end{pmatrix}, \qquad t \in \mathbb{R}.
$$

The system has **infinitely many solutions**.

**Explanation of Why $(0,0,0)$ Always Satisfies a Homogeneous System:**
A linear system is called homogeneous when the constant term on the right-hand side of every equation is zero:

$$
Ax = 0.
$$

When evaluating the matrix-vector product $Ax$ for the zero vector $x = (0, 0, 0)^T$:

$$
\sum_{j=1}^n a_{ij} x_j = \sum_{j=1}^n a_{ij} \cdot 0 = 0 + 0 + \dots + 0 = 0
$$

for every row $i \in \{1, 2, \dots, m\}$.
Because multiplying any real number by zero produces zero, substituting $x = 0, y = 0, z = 0$ will always make every linear combination vanish, identically matching the right-hand side $0$.
Hence, the zero vector is always a valid solution (called the **trivial solution**) for any homogeneous system. In our parametric solution, setting $t = 0$ directly yields this trivial solution $(0,0,0)$.

## Final Answer

The system has infinitely many solutions (with free variable $z = t$):

$$
\begin{pmatrix}
x \\
y \\
z \\
\end{pmatrix}
= t
\begin{pmatrix}
-1 \\
1 \\
1 \\
\end{pmatrix}, \qquad t \in \mathbb{R}
$$

The trivial solution $(0,0,0)$ always satisfies a homogeneous system because $A \cdot 0 = 0$ holds identically for any matrix $A$.
