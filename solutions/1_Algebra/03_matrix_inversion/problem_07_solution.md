# Problem 07 Solution

## Problem Statement
For

$$
A=
\begin{pmatrix}
1 & 1 \\
0 & 1 \\
\end{pmatrix},\qquad B=
\begin{pmatrix}
2 & 0 \\
0 & 3 \\
\end{pmatrix}
$$

compute $(AB)^{-1}$ and $B^{-1}A^{-1}$. Check that the results are the same and explain the meaning of the reversed order.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Inverse of a Matrix Product: For any invertible matrices $A$ and $B$ of the same size, the inverse of their product satisfies $(AB)^{-1} = B^{-1}A^{-1}$.
- Inversion Formula for $2 \times 2$ Matrices: $M^{-1} = \frac{1}{\det M} \mathrm{adj}(M)$.
- Reversed Order Interpretation: In composition of linear mappings, reversing the operation requires undoing the outermost (last applied) transformation first.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Invertibility Check:**
We compute the determinants of matrices $A$ and $B$:

$$
\det A = (1)(1) - (1)(0) = 1 - 0 = 1 \neq 0
$$

$$
\det B = (2)(3) - (0)(0) = 6 - 0 = 6 \neq 0
$$

Since $\det A = 1 \neq 0$ and $\det B = 6 \neq 0$, both matrices are invertible.
By the multiplicative property of determinants:

$$
\det(AB) = \det(A) \cdot \det(B) = (1)(6) = 6 \neq 0
$$

Thus, the product $AB$ is also invertible.

2. **Intermediate Steps:**
**Step 1: Compute the product matrix $AB$**

$$
AB =
\begin{pmatrix}
1 & 1 \\
0 & 1 \\
\end{pmatrix}
\begin{pmatrix}
2 & 0 \\
0 & 3 \\
\end{pmatrix}
$$

Evaluating each entry:
- Entry $(1,1)$: $(1)(2) + (1)(0) = 2 + 0 = 2$
- Entry $(1,2)$: $(1)(0) + (1)(3) = 0 + 3 = 3$
- Entry $(2,1)$: $(0)(2) + (1)(0) = 0 + 0 = 0$
- Entry $(2,2)$: $(0)(0) + (1)(3) = 0 + 3 = 3$

Thus:

$$
AB =
\begin{pmatrix}
2 & 3 \\
0 & 3 \\
\end{pmatrix}.
$$

**Step 2: Compute $(AB)^{-1}$ directly**
Using $\det(AB) = (2)(3) - (3)(0) = 6$:

$$
(AB)^{-1} = \frac{1}{6}
\begin{pmatrix}
3 & -3 \\
0 & 2 \\
\end{pmatrix} =
\begin{pmatrix}
\frac{3}{6} & -\frac{3}{6} \\
0 & \frac{2}{6} \\
\end{pmatrix} =
\begin{pmatrix}
\frac{1}{2} & -\frac{1}{2} \\
0 & \frac{1}{3} \\
\end{pmatrix}.
$$

**Step 3: Compute $A^{-1}$ and $B^{-1}$ individually**
For matrix $A$:

$$
A^{-1} = \frac{1}{1}
\begin{pmatrix}
1 & -1 \\
0 & 1 \\
\end{pmatrix} =
\begin{pmatrix}
1 & -1 \\
0 & 1 \\
\end{pmatrix}.
$$

For matrix $B$:

$$
B^{-1} = \frac{1}{6}
\begin{pmatrix}
3 & 0 \\
0 & 2 \\
\end{pmatrix} =
\begin{pmatrix}
\frac{1}{2} & 0 \\
0 & \frac{1}{3} \\
\end{pmatrix}.
$$

**Step 4: Compute the product $B^{-1}A^{-1}$**

$$
B^{-1}A^{-1} =
\begin{pmatrix}
\frac{1}{2} & 0 \\
0 & \frac{1}{3} \\
\end{pmatrix}
\begin{pmatrix}
1 & -1 \\
0 & 1 \\
\end{pmatrix}.
$$

Evaluating each entry:
- Entry $(1,1)$: $\left(\frac{1}{2}\right)(1) + (0)(0) = \frac{1}{2} + 0 = \frac{1}{2}$
- Entry $(1,2)$: $\left(\frac{1}{2}\right)(-1) + (0)(1) = -\frac{1}{2} + 0 = -\frac{1}{2}$
- Entry $(2,1)$: $(0)(1) + \left(\frac{1}{3}\right)(0) = 0 + 0 = 0$
- Entry $(2,2)$: $(0)(-1) + \left(\frac{1}{3}\right)(1) = 0 + \frac{1}{3} = \frac{1}{3}$

Thus:

$$
B^{-1}A^{-1} =
\begin{pmatrix}
\frac{1}{2} & -\frac{1}{2} \\
0 & \frac{1}{3} \\
\end{pmatrix}.
$$

3. **Verification & Meaning of Reversed Order:**
Comparing the two matrices:

$$
(AB)^{-1} =
\begin{pmatrix}
\frac{1}{2} & -\frac{1}{2} \\
0 & \frac{1}{3} \\
\end{pmatrix}
= B^{-1}A^{-1}.
$$

Both calculations produce the identical matrix.
We verify by direct multiplication with $AB$:

$$
(AB)(B^{-1}A^{-1}) = A(BB^{-1})A^{-1} = A(I_2)A^{-1} = AA^{-1} = I_2.
$$

**Explanation of the Reversed Order:**
When a composite linear mapping acts on a vector $x$, the order of application is $y = (AB)x = A(Bx)$. The transformation $B$ is applied first, followed by transformation $A$.
To undo this sequence, one must reverse the operations in opposite chronological order:
First, undo $A$ by applying $A^{-1}$ to $y$: $Bx = A^{-1}y$.
Second, undo $B$ by applying $B^{-1}$ to the result: $x = B^{-1}(A^{-1}y) = (B^{-1}A^{-1})y$.
This fundamental principle explains why the inverse of a product reverses the order of its factors.

## Final Answer

$$
(AB)^{-1} = B^{-1}A^{-1} =
\begin{pmatrix}
\frac{1}{2} & -\frac{1}{2} \\
0 & \frac{1}{3} \\
\end{pmatrix}
$$
