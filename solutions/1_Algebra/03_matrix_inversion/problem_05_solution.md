# Problem 05 Solution

## Problem Statement
Use Gauss–Jordan elimination to find the inverse of

$$
A=
\begin{pmatrix}
1 & 1 & 0 \\
0 & 1 & 1 \\
1 & 0 & 1 \\
\end{pmatrix}.
$$

Check the result by multiplication.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Gauss-Jordan Inversion Algorithm: Form the augmented matrix $[A \mid I_3]$ and apply elementary row operations to reduce the left-hand block to the reduced row echelon form (identity matrix $I_3$), which transforms the right-hand block into $A^{-1}$: $[A \mid I_3] \to [I_3 \mid A^{-1}]$.
- Determinant Invertibility Check: A $3 \times 3$ matrix is invertible if and only if $\det A \neq 0$.
- Matrix Verification: Multiplying $A$ by $A^{-1}$ must yield the identity matrix $I_3$.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Invertibility Check:**
We compute the determinant of the $3 \times 3$ matrix $A$ using Laplace expansion along Row 1:

$$
A =
\begin{pmatrix}
1 & 1 & 0 \\
0 & 1 & 1 \\
1 & 0 & 1 \\
\end{pmatrix}.
$$

Expanding along Row 1:

$$
\det A = 1 \cdot (-1)^{1+1} \det\begin{pmatrix} 1 & 1 \\ 0 & 1 \\ \end{pmatrix} + 1 \cdot (-1)^{1+2} \det\begin{pmatrix} 0 & 1 \\ 1 & 1 \\ \end{pmatrix} + 0
$$

Evaluating the $2 \times 2$ sub-determinants:

$$
\det\begin{pmatrix} 1 & 1 \\ 0 & 1 \\ \end{pmatrix} = (1)(1) - (1)(0) = 1 - 0 = 1
$$

$$
\det\begin{pmatrix} 0 & 1 \\ 1 & 1 \\ \end{pmatrix} = (0)(1) - (1)(1) = 0 - 1 = -1
$$

Substituting these values into the expansion:

$$
\begin{aligned}
\det A &= 1 \cdot (+1) \cdot (1) + 1 \cdot (-1) \cdot (-1) \\
       &= 1 + 1 \\
       &= 2
\end{aligned}
$$

Since $\det A = 2 \neq 0$, matrix $A$ is invertible.

2. **Intermediate Steps:**
We set up the augmented matrix $[A \mid I_3]$:

$$
\begin{pmatrix}
1 & 1 & 0 & \mid & 1 & 0 & 0 \\
0 & 1 & 1 & \mid & 0 & 1 & 0 \\
1 & 0 & 1 & \mid & 0 & 0 & 1 \\
\end{pmatrix}.
$$

**Step 1: Eliminate entry $(3,1)$ using operation $R_3 \leftarrow R_3 - R_1$**
We compute the new entries of Row 3:

$$
\begin{aligned}
r_{31} &= 1 - 1 = 0 \\
r_{32} &= 0 - 1 = -1 \\
r_{33} &= 1 - 0 = 1 \\
r_{34} &= 0 - 1 = -1 \\
r_{35} &= 0 - 0 = 0 \\
r_{36} &= 1 - 0 = 1
\end{aligned}
$$

The augmented matrix after Step 1 is:

$$
\begin{pmatrix}
1 & 1 & 0 & \mid & 1 & 0 & 0 \\
0 & 1 & 1 & \mid & 0 & 1 & 0 \\
0 & -1 & 1 & \mid & -1 & 0 & 1 \\
\end{pmatrix}.
$$

**Step 2: Eliminate entry $(3,2)$ using operation $R_3 \leftarrow R_3 + R_2$**
We compute the new entries of Row 3:

$$
\begin{aligned}
r_{31} &= 0 + 0 = 0 \\
r_{32} &= -1 + 1 = 0 \\
r_{33} &= 1 + 1 = 2 \\
r_{34} &= -1 + 0 = -1 \\
r_{35} &= 0 + 1 = 1 \\
r_{36} &= 1 + 0 = 1
\end{aligned}
$$

The augmented matrix after Step 2 is:

$$
\begin{pmatrix}
1 & 1 & 0 & \mid & 1 & 0 & 0 \\
0 & 1 & 1 & \mid & 0 & 1 & 0 \\
0 & 0 & 2 & \mid & -1 & 1 & 1 \\
\end{pmatrix}.
$$

**Step 3: Scale Row 3 to obtain a leading 1 using operation $R_3 \leftarrow \frac{1}{2} R_3$**
We compute the new entries of Row 3:

$$
\begin{aligned}
r_{31} &= \frac{1}{2}(0) = 0 \\
r_{32} &= \frac{1}{2}(0) = 0 \\
r_{33} &= \frac{1}{2}(2) = 1 \\
r_{34} &= \frac{1}{2}(-1) = -\frac{1}{2} \\
r_{35} &= \frac{1}{2}(1) = \frac{1}{2} \\
r_{36} &= \frac{1}{2}(1) = \frac{1}{2}
\end{aligned}
$$

The augmented matrix after Step 3 is:

$$
\begin{pmatrix}
1 & 1 & 0 & \mid & 1 & 0 & 0 \\
0 & 1 & 1 & \mid & 0 & 1 & 0 \\
0 & 0 & 1 & \mid & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \\
\end{pmatrix}.
$$

**Step 4: Eliminate entry $(2,3)$ using operation $R_2 \leftarrow R_2 - R_3$**
We compute the new entries of Row 2:

$$
\begin{aligned}
r_{21} &= 0 - 0 = 0 \\
r_{22} &= 1 - 0 = 1 \\
r_{23} &= 1 - 1 = 0 \\
r_{24} &= 0 - \left(-\frac{1}{2}\right) = \frac{1}{2} \\
r_{25} &= 1 - \frac{1}{2} = \frac{1}{2} \\
r_{26} &= 0 - \frac{1}{2} = -\frac{1}{2}
\end{aligned}
$$

The augmented matrix after Step 4 is:

$$
\begin{pmatrix}
1 & 1 & 0 & \mid & 1 & 0 & 0 \\
0 & 1 & 0 & \mid & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\
0 & 0 & 1 & \mid & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \\
\end{pmatrix}.
$$

**Step 5: Eliminate entry $(1,2)$ using operation $R_1 \leftarrow R_1 - R_2$**
We compute the new entries of Row 1:

$$
\begin{aligned}
r_{11} &= 1 - 0 = 1 \\
r_{12} &= 1 - 1 = 0 \\
r_{13} &= 0 - 0 = 0 \\
r_{14} &= 1 - \frac{1}{2} = \frac{1}{2} \\
r_{15} &= 0 - \frac{1}{2} = -\frac{1}{2} \\
r_{16} &= 0 - \left(-\frac{1}{2}\right) = \frac{1}{2}
\end{aligned}
$$

The augmented matrix after Step 5 is:

$$
\begin{pmatrix}
1 & 0 & 0 & \mid & \frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\
0 & 1 & 0 & \mid & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\
0 & 0 & 1 & \mid & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \\
\end{pmatrix}.
$$

The left-hand side is the identity matrix $I_3$. The right-hand side is the inverse matrix:

$$
A^{-1} =
\begin{pmatrix}
\frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\
\frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\
-\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \\
\end{pmatrix}
= \frac{1}{2}
\begin{pmatrix}
1 & -1 & 1 \\
1 & 1 & -1 \\
-1 & 1 & 1 \\
\end{pmatrix}.
$$

3. **Verification:**
We check the result by computing the product $A \cdot A^{-1}$:

$$
A \cdot A^{-1} =
\begin{pmatrix}
1 & 1 & 0 \\
0 & 1 & 1 \\
1 & 0 & 1 \\
\end{pmatrix}
\left[\frac{1}{2}
\begin{pmatrix}
1 & -1 & 1 \\
1 & 1 & -1 \\
-1 & 1 & 1 \\
\end{pmatrix}\right].
$$

We evaluate the matrix product entry by entry:
- Row 1:
  - $(1,1)$: $(1)(1) + (1)(1) + (0)(-1) = 1 + 1 + 0 = 2$
  - $(1,2)$: $(1)(-1) + (1)(1) + (0)(1) = -1 + 1 + 0 = 0$
  - $(1,3)$: $(1)(1) + (1)(-1) + (0)(1) = 1 - 1 + 0 = 0$
- Row 2:
  - $(2,1)$: $(0)(1) + (1)(1) + (1)(-1) = 0 + 1 - 1 = 0$
  - $(2,2)$: $(0)(-1) + (1)(1) + (1)(1) = 0 + 1 + 1 = 2$
  - $(2,3)$: $(0)(1) + (1)(-1) + (1)(1) = 0 - 1 + 1 = 0$
- Row 3:
  - $(3,1)$: $(1)(1) + (0)(1) + (1)(-1) = 1 + 0 - 1 = 0$
  - $(3,2)$: $(1)(-1) + (0)(1) + (1)(1) = -1 + 0 + 1 = 0$
  - $(3,3)$: $(1)(1) + (0)(-1) + (1)(1) = 1 + 0 + 1 = 2$

Multiplying by the scalar $\frac{1}{2}$:

$$
A \cdot A^{-1} = \frac{1}{2}
\begin{pmatrix}
2 & 0 & 0 \\
0 & 2 & 0 \\
0 & 0 & 2 \\
\end{pmatrix} =
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1 \\
\end{pmatrix}
= I_3.
$$

The result is fully verified.

## Final Answer

$$
A^{-1} =
\begin{pmatrix}
\frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\
\frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\
-\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \\
\end{pmatrix}
$$
