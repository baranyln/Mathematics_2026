# Problem 11 Solution

## Problem Statement
Compute

$$
\det
\begin{pmatrix}
1 & 2 & 3 \\
1 & 3 & 4 \\
1 & 4 & 6 \\
\end{pmatrix}
$$

by first performing row operations that create as many zeros as possible. State which operations do not change the determinant.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Row Operations Preserving Determinant: Adding a scalar multiple of one row to another row ($R_i \leftarrow R_i + c R_j$ with $i \neq j$) does not change the determinant.
- Determinant of an Upper Triangular Matrix: Once transformed into upper triangular form, the determinant equals the product of the diagonal elements.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Method Selection & Matrix Setup:**
The given matrix has size $3 \times 3$:

$$
A =
\begin{pmatrix}
1 & 2 & 3 \\
1 & 3 & 4 \\
1 & 4 & 6 \\
\end{pmatrix}.
$$

Notice that the first column entries are all equal to $1$. Using Row 1 as a pivot, we perform row operations to eliminate the non-zero entries in Column 1 below the pivot.

**Statement of Operations that Preserve the Determinant:**
Adding a scalar multiple of one row to another row ($R_i \leftarrow R_i + c R_j$ with $i \neq j$) does not change the determinant. Therefore, all three operations used below preserve the determinant exactly.

2. **Intermediate Calculations:**
**Step 1: Perform $R_2 \leftarrow R_2 - R_1$**
This operation adds $(-1)$ times Row 1 to Row 2, leaving the determinant unchanged.
We compute the new entries of Row 2:

$$
\begin{aligned}
r_{21} &= 1 - 1 = 0 \\
r_{22} &= 3 - 2 = 1 \\
r_{23} &= 4 - 3 = 1
\end{aligned}
$$

**Step 2: Perform $R_3 \leftarrow R_3 - R_1$**
This operation adds $(-1)$ times Row 1 to Row 3, leaving the determinant unchanged.
We compute the new entries of Row 3:

$$
\begin{aligned}
r_{31} &= 1 - 1 = 0 \\
r_{32} &= 4 - 2 = 2 \\
r_{33} &= 6 - 3 = 3
\end{aligned}
$$

The matrix becomes:

$$
A_1 =
\begin{pmatrix}
1 & 2 & 3 \\
0 & 1 & 1 \\
0 & 2 & 3 \\
\end{pmatrix}, \qquad \det(A_1) = \det(A).
$$

**Step 3: Perform $R_3 \leftarrow R_3 - 2R_2$**
To create an additional zero at entry $(3,2)$, we subtract $2$ times Row 2 from Row 3. This operation also preserves the determinant.
We compute the new entries of Row 3:

$$
\begin{aligned}
r_{31} &= 0 - 2(0) = 0 \\
r_{32} &= 2 - 2(1) = 2 - 2 = 0 \\
r_{33} &= 3 - 2(1) = 3 - 2 = 1
\end{aligned}
$$

The matrix is now transformed into upper triangular form:

$$
A_2 =
\begin{pmatrix}
1 & 2 & 3 \\
0 & 1 & 1 \\
0 & 0 & 1 \\
\end{pmatrix}, \qquad \det(A_2) = \det(A_1) = \det(A).
$$

3. **Arithmetic Evaluation:**
The matrix $A_2$ is in upper triangular form. Its determinant is the product of its diagonal entries:

$$
\det A = \det A_2 = a_{11} \cdot a_{22} \cdot a_{33} = (1) \cdot (1) \cdot (1)
$$

Multiplying the diagonal entries:

$$
(1) \cdot (1) \cdot (1) = 1
$$

Alternatively, expanding $\det A_1$ along the first column:

$$
\begin{aligned}
\det A_1 &= 1 \cdot (-1)^{1+1} \det\begin{pmatrix} 1 & 1 \\ 2 & 3 \\ \end{pmatrix} - 0 + 0 \\
         &= (1)(3) - (1)(2) \\
         &= 3 - 2 \\
         &= 1
\end{aligned}
$$

Both calculations confirm:

$$
\det A = 1
$$

## Final Answer

$$
\det(A) = 1
$$
