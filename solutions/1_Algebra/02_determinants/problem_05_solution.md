# Problem 05 Solution

## Problem Statement
For

$$
A=
\begin{pmatrix}
1 & 2 & 3 \\
2 & 1 & 0 \\
-1 & 4 & 2 \\
\end{pmatrix}
$$

find $\det A$ by simplifying the matrix with row operations. At each step, indicate whether and how the determinant changes.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Row Operations Preserving Determinant: Adding a scalar multiple of one row to another row ($R_i \leftarrow R_i + c R_j$ with $i \neq j$) does not change the determinant.
- Determinant of an Upper Triangular Matrix: The determinant of an upper triangular matrix equals the product of its diagonal entries.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Method Selection & Matrix Setup:**
The given matrix has size $3 \times 3$:

$$
A =
\begin{pmatrix}
1 & 2 & 3 \\
2 & 1 & 0 \\
-1 & 4 & 2 \\
\end{pmatrix}.
$$

We apply elementary row operations of Type III to transform $A$ into an upper triangular matrix. At each step, we record the operation and track its effect on the value of the determinant.

2. **Intermediate Calculations:**
**Step 1: Eliminate entry $(2,1)$ using $R_2 \leftarrow R_2 - 2R_1$**
Adding a scalar multiple of Row 1 to Row 2 leaves the determinant unchanged ($\det A_1 = \det A$).
We compute the entries of the new Row 2:

$$
\begin{aligned}
r_{21} &= 2 - 2(1) = 2 - 2 = 0 \\
r_{22} &= 1 - 2(2) = 1 - 4 = -3 \\
r_{23} &= 0 - 2(3) = 0 - 6 = -6
\end{aligned}
$$

The resulting matrix is:

$$
A_1 =
\begin{pmatrix}
1 & 2 & 3 \\
0 & -3 & -6 \\
-1 & 4 & 2 \\
\end{pmatrix}, \qquad \det(A_1) = \det(A).
$$

**Step 2: Eliminate entry $(3,1)$ using $R_3 \leftarrow R_3 + R_1$**
Adding Row 1 to Row 3 leaves the determinant unchanged ($\det A_2 = \det A_1 = \det A$).
We compute the entries of the new Row 3:

$$
\begin{aligned}
r_{31} &= -1 + 1 = 0 \\
r_{32} &= 4 + 2 = 6 \\
r_{33} &= 2 + 3 = 5
\end{aligned}
$$

The resulting matrix is:

$$
A_2 =
\begin{pmatrix}
1 & 2 & 3 \\
0 & -3 & -6 \\
0 & 6 & 5 \\
\end{pmatrix}, \qquad \det(A_2) = \det(A).
$$

**Step 3: Eliminate entry $(3,2)$ using $R_3 \leftarrow R_3 + 2R_2$**
Adding 2 times Row 2 to Row 3 leaves the determinant unchanged ($\det A_3 = \det A_2 = \det A$).
We compute the entries of the new Row 3:

$$
\begin{aligned}
r_{31} &= 0 + 2(0) = 0 \\
r_{32} &= 6 + 2(-3) = 6 - 6 = 0 \\
r_{33} &= 5 + 2(-6) = 5 - 12 = -7
\end{aligned}
$$

The resulting matrix is in upper triangular form:

$$
A_3 =
\begin{pmatrix}
1 & 2 & 3 \\
0 & -3 & -6 \\
0 & 0 & -7 \\
\end{pmatrix}, \qquad \det(A_3) = \det(A).
$$

3. **Arithmetic Evaluation:**
Because matrix $A_3$ is upper triangular, its determinant is the product of its main diagonal entries:

$$
\det A = \det A_3 = (a_{11})(a_{22})(a_{33}) = (1) \cdot (-3) \cdot (-7)
$$

Evaluating the product:

$$
\begin{aligned}
(1) \cdot (-3) &= -3 \\
(-3) \cdot (-7) &= 21
\end{aligned}
$$

Thus:

$$
\det A = 21
$$

## Final Answer

$$
\det(A) = 21
$$
