# Problem 13 Solution

## Problem Statement
Consider the system

$$
x_1+x_2=10,\qquad x_2+x_3=8,\qquad x_1-x_3=2.
$$

Solve it and check whether all three equations are independently necessary to describe the solution set. If one follows from the others, show this by calculation.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Linear Dependence and Redundancy of Equations: An equation in a linear system is redundant if it can be expressed as a linear combination of the other equations.
- Detection via Row Operations: If Gaussian elimination transforms an entire row of the augmented matrix into zeros ($0 = 0$), the original equation corresponding to that row carries no independent information.
- Parametric Description: When a system contains redundant equations, the remaining independent equations define the solution set in parametric form.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 5 (`cases` environment with rows on separate lines ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **System Setup & Matrix Formulation:**
We write the system of equations explicitly including zero coefficients:

$$
\begin{cases}
x_1 + x_2 + 0x_3 = 10, \\
0x_1 + x_2 + x_3 = 8, \\
x_1 + 0x_2 - x_3 = 2.
\end{cases}
$$

We formulate the augmented matrix $[A \mid b]$:

$$
\begin{pmatrix}
1 & 1 & 0 & \mid & 10 \\
0 & 1 & 1 & \mid & 8 \\
1 & 0 & -1 & \mid & 2 \\
\end{pmatrix}.
$$

2. **Intermediate Steps:**
**Step 1: Eliminate entry $(3,1)$ using operation $R_3 \leftarrow R_3 - R_1$**
We compute the new entries of Row 3:

$$
\begin{aligned}
r_{31} &= 1 - 1 = 0 \\
r_{32} &= 0 - 1 = -1 \\
r_{33} &= -1 - 0 = -1 \\
r_{34} &= 2 - 10 = -8
\end{aligned}
$$

The augmented matrix after Step 1 is:

$$
\begin{pmatrix}
1 & 1 & 0 & \mid & 10 \\
0 & 1 & 1 & \mid & 8 \\
0 & -1 & -1 & \mid & -8 \\
\end{pmatrix}.
$$

**Step 2: Eliminate entry $(3,2)$ using operation $R_3 \leftarrow R_3 + R_2$**
We compute the new entries of Row 3:

$$
\begin{aligned}
r_{31} &= 0 + 0 = 0 \\
r_{32} &= -1 + 1 = 0 \\
r_{33} &= -1 + 1 = 0 \\
r_{34} &= -8 + 8 = 0
\end{aligned}
$$

The augmented matrix becomes:

$$
\begin{pmatrix}
1 & 1 & 0 & \mid & 10 \\
0 & 1 & 1 & \mid & 8 \\
0 & 0 & 0 & \mid & 0 \\
\end{pmatrix}.
$$

**Step 3: Eliminate entry $(1,2)$ using operation $R_1 \leftarrow R_1 - R_2$**
We compute the new entries of Row 1:

$$
\begin{aligned}
r_{11} &= 1 - 0 = 1 \\
r_{12} &= 1 - 1 = 0 \\
r_{13} &= 0 - 1 = -1 \\
r_{14} &= 10 - 8 = 2
\end{aligned}
$$

The augmented matrix in reduced row echelon form (RREF) is:

$$
\begin{pmatrix}
1 & 0 & -1 & \mid & 2 \\
0 & 1 & 1 & \mid & 8 \\
0 & 0 & 0 & \mid & 0 \\
\end{pmatrix}.
$$

3. **Variable Evaluation & Redundancy Proof:**
**Demonstration of Redundancy:**
Not all three equations are independently necessary. The fact that Row 3 becomes entirely zero ($0 = 0$) demonstrates that the third equation carries no independent information.

We prove this by showing that Equation 3 is a direct linear combination of Equations 1 and 2.
Let the equations be denoted by:

$$
E_1: x_1 + x_2 = 10
$$

$$
E_2: x_2 + x_3 = 8
$$

$$
E_3: x_1 - x_3 = 2
$$

Subtracting Equation 2 from Equation 1:

$$
\begin{aligned}
E_1 - E_2 &= (x_1 + x_2) - (x_2 + x_3) \\
          &= x_1 - x_3
\end{aligned}
$$

Evaluating the right-hand sides:

$$
10 - 8 = 2.
$$

Thus:

$$
E_1 - E_2 = E_3 \iff x_1 - x_3 = 2.
$$

This calculation shows that Equation 3 is algebraically redundant; any point satisfying Equations 1 and 2 automatically satisfies Equation 3.

**Parametric Solution:**
- From Row 1:

$$
x_1 - x_3 = 2 \implies x_1 = 2 + x_3
$$

- From Row 2:

$$
x_2 + x_3 = 8 \implies x_2 = 8 - x_3
$$

- $x_3$ is the free variable. Setting $x_3 = t$, where $t \in \mathbb{R}$:

$$
x_1 = 2 + t, \qquad x_2 = 8 - t, \qquad x_3 = t, \qquad t \in \mathbb{R}
$$

In vector form:

$$
\begin{pmatrix}
x_1 \\
x_2 \\
x_3 \\
\end{pmatrix} =
\begin{pmatrix}
2 \\
8 \\
0 \\
\end{pmatrix}
+ t
\begin{pmatrix}
1 \\
-1 \\
1 \\
\end{pmatrix}, \qquad t \in \mathbb{R}.
$$

The system has **infinitely many solutions**.

## Final Answer

The equations are not independently necessary; Equation 3 follows directly from the others via:

$$
E_3 = E_1 - E_2 \implies (x_1 + x_2) - (x_2 + x_3) = 10 - 8 \implies x_1 - x_3 = 2
$$

The solution set is:

$$
\begin{pmatrix}
x_1 \\
x_2 \\
x_3 \\
\end{pmatrix} =
\begin{pmatrix}
2 + t \\
8 - t \\
t \\
\end{pmatrix}, \qquad t \in \mathbb{R}
$$
