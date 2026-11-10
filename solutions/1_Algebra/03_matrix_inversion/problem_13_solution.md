# Problem 13 Solution

## Problem Statement
The matrices

$$
S=
\begin{pmatrix}
2 & 0 \\
0 & 1 \\
\end{pmatrix},\qquad H=
\begin{pmatrix}
1 & 1 \\
0 & 1 \\
\end{pmatrix}
$$

describe nonuniform scaling and shear. For $T=HS$, find $T^{-1}$ in two ways:

1. first compute $T$, then its inverse,
2. use $(HS)^{-1}=S^{-1}H^{-1}$.

Compare the results. Additionally compute $H^{-1}S^{-1}$ and verify that the incorrect order gives a different matrix. Explain the rule: “when undoing a composition of operations, we undo them from the end.”

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Inverse of a Composite Matrix: For invertible square matrices $A$ and $B$, the inverse of their product reverses the multiplication order: $(AB)^{-1} = B^{-1}A^{-1}$.
- Direct Matrix Inversion: $M^{-1} = \frac{1}{\det M} \mathrm{adj}(M)$.
- Transformation Composition Principle: Undoing a sequence of geometric operations requires reversing the individual steps in exact reverse chronological order.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Invertibility Check:**
We compute the determinants of matrices $S$ and $H$:

$$
S =
\begin{pmatrix}
2 & 0 \\
0 & 1 \\
\end{pmatrix} \implies \det S = (2)(1) - (0)(0) = 2 \neq 0
$$

$$
H =
\begin{pmatrix}
1 & 1 \\
0 & 1 \\
\end{pmatrix} \implies \det H = (1)(1) - (1)(0) = 1 \neq 0
$$

For $T = HS$, applying the multiplicative determinant property:

$$
\det T = \det(HS) = \det H \cdot \det S = (1)(2) = 2 \neq 0
$$

Since $\det T = 2 \neq 0$, the composite transformation matrix $T$ is invertible.

2. **Intermediate Steps:**
**Method 1: First compute $T$, then invert $T$**
We multiply $H$ and $S$:

$$
T = HS =
\begin{pmatrix}
1 & 1 \\
0 & 1 \\
\end{pmatrix}
\begin{pmatrix}
2 & 0 \\
0 & 1 \\
\end{pmatrix}.
$$

Evaluating each entry:
- Entry $(1,1)$: $(1)(2) + (1)(0) = 2 + 0 = 2$
- Entry $(1,2)$: $(1)(0) + (1)(1) = 0 + 1 = 1$
- Entry $(2,1)$: $(0)(2) + (1)(0) = 0 + 0 = 0$
- Entry $(2,2)$: $(0)(0) + (1)(1) = 0 + 1 = 1$

Thus:

$$
T =
\begin{pmatrix}
2 & 1 \\
0 & 1 \\
\end{pmatrix}.
$$

Using $\det T = (2)(1) - (1)(0) = 2$, we compute $T^{-1}$:

$$
T^{-1} = \frac{1}{2}
\begin{pmatrix}
1 & -1 \\
0 & 2 \\
\end{pmatrix} =
\begin{pmatrix}
\frac{1}{2} & -\frac{1}{2} \\
0 & 1 \\
\end{pmatrix}.
$$

**Method 2: Use the formula $(HS)^{-1} = S^{-1}H^{-1}$**
We find the individual inverses $S^{-1}$ and $H^{-1}$:

$$
S^{-1} = \frac{1}{2}
\begin{pmatrix}
1 & 0 \\
0 & 2 \\
\end{pmatrix} =
\begin{pmatrix}
\frac{1}{2} & 0 \\
0 & 1 \\
\end{pmatrix}
$$

$$
H^{-1} = \frac{1}{1}
\begin{pmatrix}
1 & -1 \\
0 & 1 \\
\end{pmatrix} =
\begin{pmatrix}
1 & -1 \\
0 & 1 \\
\end{pmatrix}.
$$

Now we compute the product $S^{-1}H^{-1}$:

$$
S^{-1}H^{-1} =
\begin{pmatrix}
\frac{1}{2} & 0 \\
0 & 1 \\
\end{pmatrix}
\begin{pmatrix}
1 & -1 \\
0 & 1 \\
\end{pmatrix}.
$$

Evaluating each entry:
- Entry $(1,1)$: $\left(\frac{1}{2}\right)(1) + (0)(0) = \frac{1}{2} + 0 = \frac{1}{2}$
- Entry $(1,2)$: $\left(\frac{1}{2}\right)(-1) + (0)(1) = -\frac{1}{2} + 0 = -\frac{1}{2}$
- Entry $(2,1)$: $(0)(1) + (1)(0) = 0 + 0 = 0$
- Entry $(2,2)$: $(0)(-1) + (1)(1) = 0 + 1 = 1$

Thus:

$$
S^{-1}H^{-1} =
\begin{pmatrix}
\frac{1}{2} & -\frac{1}{2} \\
0 & 1 \\
\end{pmatrix}.
$$

Comparing Method 1 and Method 2 shows that both approaches produce the identical matrix.

**Computing the Incorrect Order $H^{-1}S^{-1}$:**
We multiply in the unreversed order:

$$
H^{-1}S^{-1} =
\begin{pmatrix}
1 & -1 \\
0 & 1 \\
\end{pmatrix}
\begin{pmatrix}
\frac{1}{2} & 0 \\
0 & 1 \\
\end{pmatrix}.
$$

Evaluating each entry:
- Entry $(1,1)$: $(1)\left(\frac{1}{2}\right) + (-1)(0) = \frac{1}{2} + 0 = \frac{1}{2}$
- Entry $(1,2)$: $(1)(0) + (-1)(1) = 0 - 1 = -1$
- Entry $(2,1)$: $(0)\left(\frac{1}{2}\right) + (1)(0) = 0 + 0 = 0$
- Entry $(2,2)$: $(0)(0) + (1)(1) = 0 + 1 = 1$

Thus:

$$
H^{-1}S^{-1} =
\begin{pmatrix}
\frac{1}{2} & -1 \\
0 & 1 \\
\end{pmatrix}.
$$

Comparing this with $T^{-1}$:

$$
\begin{pmatrix}
\frac{1}{2} & -\frac{1}{2} \\
0 & 1 \\
\end{pmatrix}
\neq
\begin{pmatrix}
\frac{1}{2} & -1 \\
0 & 1 \\
\end{pmatrix}.
$$

The entry in Row 1, Column 2 differs ($-\frac{1}{2} \neq -1$).

3. **Verification & Explanation of the Rule:**
We test the candidate inverses by multiplying on the right of $T$:

$$
T (S^{-1}H^{-1}) = (HS)(S^{-1}H^{-1}) = H(S S^{-1})H^{-1} = H(I_2)H^{-1} = H H^{-1} = I_2.
$$

In contrast, multiplying $T$ by the incorrect order $H^{-1}S^{-1}$ gives:

$$
T (H^{-1}S^{-1}) =
\begin{pmatrix}
2 & 1 \\
0 & 1 \\
\end{pmatrix}
\begin{pmatrix}
\frac{1}{2} & -1 \\
0 & 1 \\
\end{pmatrix} =
\begin{pmatrix}
(2)\left(\frac{1}{2}\right) + (1)(0) & (2)(-1) + (1)(1) \\
(0)\left(\frac{1}{2}\right) + (1)(0) & (0)(-1) + (1)(1) \\
\end{pmatrix} =
\begin{pmatrix}
1 & -1 \\
0 & 1 \\
\end{pmatrix}
\neq I_2.
$$

**Explanation of the Rule:**
When performing a composite sequence of actions $y = T x = H(S x)$, the scaling $S$ is executed first, and the shear $H$ is executed second.
To restore the system to its initial state, one must undo the actions in reverse chronological order:
First, undo the most recent operation ($H$) by applying $H^{-1}$.
Second, undo the preceding operation ($S$) by applying $S^{-1}$.
This is analogous to the everyday rule that when putting on shoes over socks, one must remove the shoes before removing the socks. Thus, undoing operations from the end yields $(HS)^{-1} = S^{-1}H^{-1}$.

## Final Answer

$$
T^{-1} = (HS)^{-1} = S^{-1}H^{-1} =
\begin{pmatrix}
\frac{1}{2} & -\frac{1}{2} \\
0 & 1 \\
\end{pmatrix}
$$

The incorrect order produces:

$$
H^{-1}S^{-1} =
\begin{pmatrix}
\frac{1}{2} & -1 \\
0 & 1 \\
\end{pmatrix}
\neq T^{-1}
$$
