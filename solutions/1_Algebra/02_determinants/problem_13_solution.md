# Problem 13 Solution

## Problem Statement
Compute the determinant

$$
A=
\begin{pmatrix}
1 & 2 & 3 \\
2 & 5 & 7 \\
1 & 0 & 2 \\
\end{pmatrix}
$$

using elimination. Record the effect of every row operation used on the value of the determinant.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Elimination and Determinants:
  - Row Addition / Subtraction ($R_i \leftarrow R_i + c R_j$ with $i \neq j$): Preserves the determinant.
  - Row Scaling ($R_i \leftarrow c R_i$ with $c \neq 0$): Multiplies the determinant by $c$.
  - Row Swapping ($R_i \leftrightarrow R_j$ with $i \neq j$): Multiplies the determinant by $-1$.
  - Determinant of an Upper Triangular Matrix: Equals the product of its diagonal entries.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Method Selection & Matrix Setup:**
The given matrix has size $3 \times 3$:

$$
A =
\begin{pmatrix}
1 & 2 & 3 \\
2 & 5 & 7 \\
1 & 0 & 2 \\
\end{pmatrix}.
$$

We use Gaussian elimination to transform matrix $A$ into an upper triangular matrix $A_3$ while recording the effect of each elementary row operation on the determinant.

2. **Intermediate Calculations:**
**Step 1: Eliminate entry $(2,1)$ using operation $R_2 \leftarrow R_2 - 2R_1$**
Adding a scalar multiple of Row 1 to Row 2 preserves the determinant:

$$
\det(A_1) = \det(A)
$$

We compute the entries of the new Row 2:

$$
\begin{aligned}
r_{21} &= 2 - 2(1) = 2 - 2 = 0 \\
r_{22} &= 5 - 2(2) = 5 - 4 = 1 \\
r_{23} &= 7 - 2(3) = 7 - 6 = 1
\end{aligned}
$$

The matrix becomes:

$$
A_1 =
\begin{pmatrix}
1 & 2 & 3 \\
0 & 1 & 1 \\
1 & 0 & 2 \\
\end{pmatrix}.
$$

**Step 2: Eliminate entry $(3,1)$ using operation $R_3 \leftarrow R_3 - R_1$**
Adding a scalar multiple of Row 1 to Row 3 preserves the determinant:

$$
\det(A_2) = \det(A_1) = \det(A)
$$

We compute the entries of the new Row 3:

$$
\begin{aligned}
r_{31} &= 1 - 1 = 0 \\
r_{32} &= 0 - 2 = -2 \\
r_{33} &= 2 - 3 = -1
\end{aligned}
$$

The matrix becomes:

$$
A_2 =
\begin{pmatrix}
1 & 2 & 3 \\
0 & 1 & 1 \\
0 & -2 & -1 \\
\end{pmatrix}.
$$

**Step 3: Eliminate entry $(3,2)$ using operation $R_3 \leftarrow R_3 + 2R_2$**
Adding $2$ times Row 2 to Row 3 preserves the determinant:

$$
\det(A_3) = \det(A_2) = \det(A)
$$

We compute the entries of the new Row 3:

$$
\begin{aligned}
r_{31} &= 0 + 2(0) = 0 \\
r_{32} &= -2 + 2(1) = -2 + 2 = 0 \\
r_{33} &= -1 + 2(1) = -1 + 2 = 1
\end{aligned}
$$

The matrix is now in upper triangular form:

$$
A_3 =
\begin{pmatrix}
1 & 2 & 3 \\
0 & 1 & 1 \\
0 & 0 & 1 \\
\end{pmatrix}.
$$

3. **Arithmetic Evaluation:**
All elementary row operations performed were of Type III ($R_i \leftarrow R_i + c R_j$), meaning none of them changed the value of the determinant:

$$
\det(A) = \det(A_3)
$$

Matrix $A_3$ is an upper triangular matrix, so its determinant is the product of its diagonal elements:

$$
\det(A_3) = a_{11} \cdot a_{22} \cdot a_{33} = (1) \cdot (1) \cdot (1)
$$

Multiplying the diagonal elements:

$$
(1) \cdot (1) \cdot (1) = 1
$$

Thus:

$$
\det(A) = 1
$$

## Final Answer

$$
\det(A) = 1
$$
