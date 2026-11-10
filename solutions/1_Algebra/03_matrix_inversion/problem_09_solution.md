# Problem 09 Solution

## Problem Statement
Given

$$
A=
\begin{pmatrix}
1 & 2 \\
0 & 1 \\
\end{pmatrix},\qquad B=
\begin{pmatrix}
3 & 1 \\
2 & 4 \\
\end{pmatrix}.
$$

Solve the equation $AX=B$ for $X$. Before calculating, decide on which side of the equation $A^{-1}$ must be used. Then check the result by computing $AX$.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Solving Matrix Equations: Because matrix multiplication is non-commutative in general ($CD \neq DC$), one must isolate the unknown matrix $X$ by multiplying on the appropriate side. For $AX = B$, multiply on the left by $A^{-1}$ to obtain $X = A^{-1}B$.
- Inverse of a $2 \times 2$ Matrix: $A^{-1} = \frac{1}{\det A} \begin{pmatrix} d & -b \\ -c & a \\ \end{pmatrix}$.
- Verification: Multiplying $A$ by the computed solution $X$ confirms that $AX = B$.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Invertibility Check:**
We compute the determinant of matrix $A$:

$$
A =
\begin{pmatrix}
1 & 2 \\
0 & 1 \\
\end{pmatrix}.
$$

Applying the $2 \times 2$ determinant formula:

$$
\begin{aligned}
\det A &= (a_{11})(a_{22}) - (a_{12})(a_{21}) \\
       &= (1)(1) - (2)(0) \\
       &= 1 - 0 \\
       &= 1
\end{aligned}
$$

Since $\det A = 1 \neq 0$, matrix $A$ is non-singular and its inverse $A^{-1}$ exists.

2. **Intermediate Steps:**
**Decision on Which Side to Multiply by $A^{-1}$:**
We are given the matrix equation:

$$
AX = B.
$$

To isolate $X$, we multiply both sides on the **left** by $A^{-1}$:

$$
A^{-1}(AX) = A^{-1}B
$$

Using the associative property of matrix multiplication:

$$
(A^{-1}A)X = A^{-1}B \implies I_2 X = A^{-1}B \implies X = A^{-1}B.
$$

If we had instead multiplied on the right, we would obtain $(AX)A^{-1} = BA^{-1}$, which does not simplify the left-hand side because matrix multiplication does not commute ($XA^{-1} \neq A^{-1}X$). Therefore, $A^{-1}$ must be applied on the left.

**Computing the Inverse $A^{-1}$:**
Using the explicit $2 \times 2$ formula:

$$
A^{-1} = \frac{1}{1}
\begin{pmatrix}
1 & -2 \\
0 & 1 \\
\end{pmatrix} =
\begin{pmatrix}
1 & -2 \\
0 & 1 \\
\end{pmatrix}.
$$

**Computing $X = A^{-1}B$:**

$$
X =
\begin{pmatrix}
1 & -2 \\
0 & 1 \\
\end{pmatrix}
\begin{pmatrix}
3 & 1 \\
2 & 4 \\
\end{pmatrix}.
$$

Evaluating each entry of the product:
- Entry $(1,1)$: $(1)(3) + (-2)(2) = 3 - 4 = -1$
- Entry $(1,2)$: $(1)(1) + (-2)(4) = 1 - 8 = -7$
- Entry $(2,1)$: $(0)(3) + (1)(2) = 0 + 2 = 2$
- Entry $(2,2)$: $(0)(1) + (1)(4) = 0 + 4 = 4$

Assembling matrix $X$:

$$
X =
\begin{pmatrix}
-1 & -7 \\
2 & 4 \\
\end{pmatrix}.
$$

3. **Verification:**
We check the solution by multiplying $A$ by $X$:

$$
AX =
\begin{pmatrix}
1 & 2 \\
0 & 1 \\
\end{pmatrix}
\begin{pmatrix}
-1 & -7 \\
2 & 4 \\
\end{pmatrix}.
$$

Evaluating each entry:
- Entry $(1,1)$: $(1)(-1) + (2)(2) = -1 + 4 = 3$
- Entry $(1,2)$: $(1)(-7) + (2)(4) = -7 + 8 = 1$
- Entry $(2,1)$: $(0)(-1) + (1)(2) = 0 + 2 = 2$
- Entry $(2,2)$: $(0)(-7) + (1)(4) = 0 + 4 = 4$

Assembling the result:

$$
AX =
\begin{pmatrix}
3 & 1 \\
2 & 4 \\
\end{pmatrix}
= B.
$$

The product confirms that $AX = B$ holds exactly.

## Final Answer

$$
X =
\begin{pmatrix}
-1 & -7 \\
2 & 4 \\
\end{pmatrix}, \qquad A^{-1} =
\begin{pmatrix}
1 & -2 \\
0 & 1 \\
\end{pmatrix}
$$
