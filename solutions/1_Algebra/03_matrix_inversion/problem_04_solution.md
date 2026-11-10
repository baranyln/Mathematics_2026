# Problem 04 Solution

## Problem Statement
Find $A^{-1}$ using the Gauss–Jordan method for

$$
A=
\begin{pmatrix}
1 & 2 \\
3 & 5 \\
\end{pmatrix}.
$$

Show the augmented matrix $[A\mid I]$ after successive operations and explain why obtaining $I$ on the left gives the inverse on the right.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Gauss-Jordan Elimination: Augment matrix $A$ with the identity matrix $I$ of the same size to form $[A \mid I]$. Apply elementary row operations until the left block becomes the identity matrix: $[A \mid I] \to [I \mid A^{-1}]$.
- Elementary Matrix Interpretation: Each elementary row operation corresponds to multiplying on the left by an elementary matrix $E_k$. If a sequence of operations transforms $A$ to $I$, then $(E_k \cdots E_1) A = I$, which proves that the accumulated transformation matrix is $E_k \cdots E_1 = A^{-1}$. Applying the same operations to $I$ yields $(E_k \cdots E_1) I = A^{-1}$.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Invertibility Check:**
We compute the determinant of matrix $A$:

$$
A =
\begin{pmatrix}
1 & 2 \\
3 & 5 \\
\end{pmatrix}.
$$

Applying the $2 \times 2$ determinant formula:

$$
\begin{aligned}
\det A &= (a_{11})(a_{22}) - (a_{12})(a_{21}) \\
       &= (1)(5) - (2)(3) \\
       &= 5 - 6 \\
       &= -1
\end{aligned}
$$

Since $\det A = -1 \neq 0$, matrix $A$ is invertible.

2. **Intermediate Steps:**
We set up the augmented matrix $[A \mid I_2]$:

$$
\begin{pmatrix}
1 & 2 & \mid & 1 & 0 \\
3 & 5 & \mid & 0 & 1 \\
\end{pmatrix}.
$$

**Step 1: Eliminate entry $(2,1)$ using operation $R_2 \leftarrow R_2 - 3R_1$**
We compute the new entries of Row 2:

$$
\begin{aligned}
r_{21} &= 3 - 3(1) = 3 - 3 = 0 \\
r_{22} &= 5 - 3(2) = 5 - 6 = -1 \\
r_{23} &= 0 - 3(1) = 0 - 3 = -3 \\
r_{24} &= 1 - 3(0) = 1 - 0 = 1
\end{aligned}
$$

The augmented matrix after Step 1 is:

$$
\begin{pmatrix}
1 & 2 & \mid & 1 & 0 \\
0 & -1 & \mid & -3 & 1 \\
\end{pmatrix}.
$$

**Step 2: Scale Row 2 to obtain a leading 1 using operation $R_2 \leftarrow (-1) R_2$**
We multiply Row 2 by $-1$:

$$
\begin{aligned}
r_{21} &= (-1)(0) = 0 \\
r_{22} &= (-1)(-1) = 1 \\
r_{23} &= (-1)(-3) = 3 \\
r_{24} &= (-1)(1) = -1
\end{aligned}
$$

The augmented matrix after Step 2 is:

$$
\begin{pmatrix}
1 & 2 & \mid & 1 & 0 \\
0 & 1 & \mid & 3 & -1 \\
\end{pmatrix}.
$$

**Step 3: Eliminate entry $(1,2)$ using operation $R_1 \leftarrow R_1 - 2R_2$**
We compute the new entries of Row 1:

$$
\begin{aligned}
r_{11} &= 1 - 2(0) = 1 - 0 = 1 \\
r_{12} &= 2 - 2(1) = 2 - 2 = 0 \\
r_{13} &= 1 - 2(3) = 1 - 6 = -5 \\
r_{14} &= 0 - 2(-1) = 0 + 2 = 2
\end{aligned}
$$

The augmented matrix after Step 3 is:

$$
\begin{pmatrix}
1 & 0 & \mid & -5 & 2 \\
0 & 1 & \mid & 3 & -1 \\
\end{pmatrix}.
$$

The left-hand block is now the identity matrix $I_2$. The right-hand block is the inverse matrix:

$$
A^{-1} =
\begin{pmatrix}
-5 & 2 \\
3 & -1 \\
\end{pmatrix}.
$$

**Explanation of the Gauss-Jordan Method:**
Each elementary row operation can be represented algebraically by multiplying the augmented matrix on the left by an elementary matrix $E_k$.
If a sequence of row operations $E_1, E_2, \dots, E_p$ transforms $A$ into the identity matrix $I$, we have:

$$
(E_p \cdots E_2 E_1) A = I.
$$

Multiplying both sides of this equation on the right by $A^{-1}$:

$$
(E_p \cdots E_2 E_1) A A^{-1} = I A^{-1} \implies E_p \cdots E_2 E_1 = A^{-1}.
$$

Since the exact same operations are simultaneously performed on the identity matrix block on the right, the right block becomes:

$$
(E_p \cdots E_2 E_1) I = A^{-1}.
$$

Thus, obtaining $I$ on the left guarantees that the block on the right is $A^{-1}$.

3. **Verification:**
We check the result by computing the product $A \cdot A^{-1}$:

$$
A \cdot A^{-1} =
\begin{pmatrix}
1 & 2 \\
3 & 5 \\
\end{pmatrix}
\begin{pmatrix}
-5 & 2 \\
3 & -1 \\
\end{pmatrix}.
$$

Evaluating each entry:
- Entry $(1,1)$: $(1)(-5) + (2)(3) = -5 + 6 = 1$
- Entry $(1,2)$: $(1)(2) + (2)(-1) = 2 - 2 = 0$
- Entry $(2,1)$: $(3)(-5) + (5)(3) = -15 + 15 = 0$
- Entry $(2,2)$: $(3)(2) + (5)(-1) = 6 - 5 = 1$

Assembling the result:

$$
A \cdot A^{-1} =
\begin{pmatrix}
1 & 0 \\
0 & 1 \\
\end{pmatrix}
= I_2.
$$

The result is fully verified.

## Final Answer

$$
A^{-1} =
\begin{pmatrix}
-5 & 2 \\
3 & -1 \\
\end{pmatrix}
$$
