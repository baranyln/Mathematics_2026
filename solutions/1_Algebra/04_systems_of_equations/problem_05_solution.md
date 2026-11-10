# Problem 05 Solution

## Problem Statement
For the augmented matrix

$$
\begin{pmatrix}
1 & 2 & -1 & \mid & 3 \\
0 & 1 & 2 & \mid & 1 \\
0 & 0 & 0 & \mid & 0 \\
\end{pmatrix}
$$

determine the number of solutions and write them in parametric form. Explain how you know how many variables may be chosen freely.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Reading Solutions from Row Echelon Form: In an augmented matrix $[A \mid b]$, the rank $r = \mathrm{rank}(A)$ is the number of non-zero rows (pivots).
- Free Variable Count Formula: For a consistent system with $n$ unknowns and rank $r$, the number of free variables is exactly $n - r$.
- Parametric Solution Representation: Express the leading (basic) variables corresponding to pivot columns in terms of the free variables corresponding to non-pivot columns.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **System Setup & Matrix Formulation:**
We are given the augmented matrix:

$$
\begin{pmatrix}
1 & 2 & -1 & \mid & 3 \\
0 & 1 & 2 & \mid & 1 \\
0 & 0 & 0 & \mid & 0 \\
\end{pmatrix}.
$$

Let the unknowns be denoted by $x_1, x_2, x_3$.
The matrix represents the linear system:

$$
\begin{aligned}
x_1 + 2x_2 - x_3 &= 3 \\
x_2 + 2x_3 &= 1 \\
0 &= 0
\end{aligned}
$$

2. **Intermediate Steps:**
**Pivot Identification:**
- In Row 1, the leading non-zero entry (pivot) is $1$, located in Column 1 (corresponding to variable $x_1$).
- In Row 2, the leading non-zero entry (pivot) is $1$, located in Column 2 (corresponding to variable $x_2$).
- In Row 3, all entries are zero ($0 = 0$), so Row 3 contains no pivot.
- Column 3 contains no leading pivot in any row.

**Determination of Ranks and Consistency:**
- The rank of the coefficient matrix is the number of pivots:

$$
\mathrm{rank}(A) = 2.
$$

- The rank of the augmented matrix is also equal to the number of non-zero rows:

$$
\mathrm{rank}([A \mid b]) = 2.
$$

- Since $\mathrm{rank}(A) = \mathrm{rank}([A \mid b]) = 2$, the system is consistent.
- The total number of variables is $n = 3$.

**Explanation of the Number of Free Variables:**
By the rank theorem, the number of independent variables (free variables) is given by:

$$
n - \mathrm{rank}(A) = 3 - 2 = 1.
$$

Because Column 3 has no pivot, variable $x_3$ can be assigned any arbitrary real value and is chosen as the **free variable**.

**Reduction to Reduced Row Echelon Form (RREF):**
To express $x_1$ directly in terms of the free variable, we eliminate the entry above the pivot in Column 2 using the row operation $R_1 \leftarrow R_1 - 2R_2$:

$$
\begin{aligned}
r_{11} &= 1 - 2(0) = 1 \\
r_{12} &= 2 - 2(1) = 0 \\
r_{13} &= -1 - 2(2) = -1 - 4 = -5 \\
r_{14} &= 3 - 2(1) = 3 - 2 = 1
\end{aligned}
$$

The augmented matrix in reduced row echelon form is:

$$
\begin{pmatrix}
1 & 0 & -5 & \mid & 1 \\
0 & 1 & 2 & \mid & 1 \\
0 & 0 & 0 & \mid & 0 \\
\end{pmatrix}.
$$

3. **Variable Evaluation & Consistency Check:**
Translating the RREF rows back to equations:
- From Row 1:

$$
x_1 - 5x_3 = 1 \implies x_1 = 1 + 5x_3
$$

- From Row 2:

$$
x_2 + 2x_3 = 1 \implies x_2 = 1 - 2x_3
$$

Setting the free variable $x_3 = t$, where $t \in \mathbb{R}$ is an arbitrary parameter:

$$
x_1 = 1 + 5t, \qquad x_2 = 1 - 2t, \qquad x_3 = t
$$

In vector form:

$$
\begin{pmatrix}
x_1 \\
x_2 \\
x_3 \\
\end{pmatrix} =
\begin{pmatrix}
1 \\
1 \\
0 \\
\end{pmatrix}
+ t
\begin{pmatrix}
5 \\
-2 \\
1 \\
\end{pmatrix}, \qquad t \in \mathbb{R}.
$$

Because $t$ can take infinitely many distinct values in $\mathbb{R}$, the system has **infinitely many solutions**.

**Consistency Check:**
We test the solution vector for parameter $t = 0$, giving the point $(x_1, x_2, x_3) = (1, 1, 0)$:
- Equation 1: $1 + 2(1) - (0) = 1 + 2 = 3$. Holds.
- Equation 2: $0 + 1 + 2(0) = 1$. Holds.
- Equation 3: $0(1) + 0(1) + 0(0) = 0$. Holds.

Testing for parameter $t = 1$, giving $(x_1, x_2, x_3) = (6, -1, 1)$:
- Equation 1: $6 + 2(-1) - (1) = 6 - 2 - 1 = 3$. Holds.
- Equation 2: $-1 + 2(1) = 1$. Holds.

The solution set is fully verified.

## Final Answer

The system has infinitely many solutions (with $1$ free variable, $x_3 = t$):

$$
\begin{pmatrix}
x_1 \\
x_2 \\
x_3 \\
\end{pmatrix} =
\begin{pmatrix}
1 + 5t \\
1 - 2t \\
t \\
\end{pmatrix}, \qquad t \in \mathbb{R}
$$
