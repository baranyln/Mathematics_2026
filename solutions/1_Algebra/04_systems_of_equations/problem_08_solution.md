# Problem 08 Solution

## Problem Statement
Solve by elimination the two systems

$$
\begin{cases}
2x+y=5, \\
x-y=1,
\end{cases}
$$

$$
\begin{cases}
2x+y=1, \\
x-y=4.
\end{cases}
$$

Compare the successive elimination steps. Which part of the calculation is the same in both cases, and why?

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Multiple Right-Hand Sides Simultaneous Elimination: When multiple systems share the identical coefficient matrix $A$, they can be solved simultaneously by appending all right-hand side vectors to the augmented matrix: $[A \mid b_1 \quad b_2]$.
- Invariance of Row Operations: Elementary row operations are determined entirely by the coefficient matrix $A$ to create leading pivots and clear columns, completely independent of the right-hand side constants.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 5 (`cases` environment with rows on separate lines ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **System Setup & Matrix Formulation:**
Both systems share the same $2 \times 2$ coefficient matrix:

$$
A =
\begin{pmatrix}
2 & 1 \\
1 & -1 \\
\end{pmatrix}.
$$

The respective right-hand side vectors are:

$$
b_1 =
\begin{pmatrix}
5 \\
1 \\
\end{pmatrix}, \qquad b_2 =
\begin{pmatrix}
1 \\
4 \\
\end{pmatrix}.
$$

We combine both systems into a single multi-augmented matrix $[A \mid b_1 \quad b_2]$:

$$
\begin{pmatrix}
2 & 1 & \mid & 5 & 1 \\
1 & -1 & \mid & 1 & 4 \\
\end{pmatrix}.
$$

2. **Intermediate Steps:**
**Step 1: Interchange Row 1 and Row 2 ($R_1 \leftrightarrow R_2$) to obtain pivot 1**

$$
\begin{pmatrix}
1 & -1 & \mid & 1 & 4 \\
2 & 1 & \mid & 5 & 1 \\
\end{pmatrix}.
$$

**Step 2: Eliminate entry $(2,1)$ using operation $R_2 \leftarrow R_2 - 2R_1$**
We compute the new entries of Row 2:
- Coefficient column 1: $2 - 2(1) = 0$
- Coefficient column 2: $1 - 2(-1) = 1 + 2 = 3$
- Right-hand side column 1 ($b_1$): $5 - 2(1) = 5 - 2 = 3$
- Right-hand side column 2 ($b_2$): $1 - 2(4) = 1 - 8 = -7$

The resulting matrix in row echelon form is:

$$
\begin{pmatrix}
1 & -1 & \mid & 1 & 4 \\
0 & 3 & \mid & 3 & -7 \\
\end{pmatrix}.
$$

3. **Variable Evaluation & Comparison:**
**Solving System 1 (with vector $b_1$):**
From Row 2:

$$
3y = 3 \implies y = 1.
$$

From Row 1:

$$
x - y = 1 \implies x - 1 = 1 \implies x = 2.
$$

Solution for System 1: $(x, y) = (2, 1)$.

Consistency check for System 1:
- Equation 1: $2(2) + 1 = 4 + 1 = 5$. Holds.
- Equation 2: $2 - 1 = 1$. Holds.

**Solving System 2 (with vector $b_2$):**
From Row 2:

$$
3y = -7 \implies y = -\frac{7}{3}.
$$

From Row 1:

$$
x - y = 4 \implies x - \left(-\frac{7}{3}\right) = 4 \implies x + \frac{7}{3} = \frac{12}{3} \implies x = \frac{5}{3}.
$$

Solution for System 2: $(x, y) = \left(\frac{5}{3}, -\frac{7}{3}\right)$.

Consistency check for System 2:
- Equation 1: $2\left(\frac{5}{3}\right) + \left(-\frac{7}{3}\right) = \frac{10 - 7}{3} = \frac{3}{3} = 1$. Holds.
- Equation 2: $\frac{5}{3} - \left(-\frac{7}{3}\right) = \frac{5 + 7}{3} = \frac{12}{3} = 4$. Holds.

**Comparison of Elimination Steps:**
- **What is the same:** The sequence of row operations (first swapping $R_1 \leftrightarrow R_2$, then subtracting $2R_1$ from $R_2$) and the resulting coefficient matrix $\begin{pmatrix} 1 & -1 \\ 0 & 3 \\ \end{pmatrix}$ are **100% identical** in both systems.
- **Why it is the same:** Gaussian elimination is designed to reduce the matrix of coefficients $A$ to row echelon form. The pivots, multipliers, and row operations are determined solely by the entries of $A$ ($a_{ij}$), regardless of what numbers appear in the right-hand side vector $b$. The right-hand side entries simply follow the transformations determined by $A$.

## Final Answer

- **System 1 Solution:**

$$
x = 2, \quad y = 1
$$

- **System 2 Solution:**

$$
x = \frac{5}{3}, \quad y = -\frac{7}{3}
$$

The coefficient elimination steps and operations are identical because they depend strictly on matrix $A$, not on the right-hand side constants.
