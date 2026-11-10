# Problem 06 Solution

## Problem Statement
Analyze, depending on the parameter $a$, the system

$$
\begin{cases}
x+y=2, \\
ax+ay=4.
\end{cases}
$$

Among the three possibilities — exactly one solution, infinitely many solutions, no solution — determine which actually occur and for which values of $a$. If one type cannot occur, explain why.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Parameterized Gaussian Elimination: Perform row operations on the augmented matrix $[A(a) \mid b]$ and analyze the resulting bottom row as a function of the parameter $a$.
- Rouché-Capelli Theorem:
  - If $\mathrm{rank}(A) = \mathrm{rank}([A \mid b]) = n$, there is a unique solution.
  - If $\mathrm{rank}(A) = \mathrm{rank}([A \mid b]) < n$, there are infinitely many solutions.
  - If $\mathrm{rank}(A) < \mathrm{rank}([A \mid b])$, there is no solution.
- Singularity Check via Determinant: $\det A(a) = 0$ for all $a$ implies that the coefficient matrix is never invertible.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 5 (`cases` environment with rows on separate lines ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **System Setup & Matrix Formulation:**
We are given the system depending on parameter $a \in \mathbb{R}$:

$$
\begin{cases}
x + y = 2, \\
ax + ay = 4.
\end{cases}
$$

We formulate the augmented matrix $[A(a) \mid b]$:

$$
\begin{pmatrix}
1 & 1 & \mid & 2 \\
a & a & \mid & 4 \\
\end{pmatrix}.
$$

2. **Intermediate Steps:**
We evaluate the determinant of the coefficient matrix $A(a)$:

$$
A(a) =
\begin{pmatrix}
1 & 1 \\
a & a \\
\end{pmatrix}.
$$

Applying the $2 \times 2$ determinant formula:

$$
\begin{aligned}
\det A(a) &= (1)(a) - (1)(a) \\
          &= a - a \\
          &= 0
\end{aligned}
$$

Notice that $\det A(a) = 0$ holds identically for **all** real numbers $a$.
The two rows of the coefficient matrix are always linearly dependent ($R_2 = a R_1$), so $\mathrm{rank}(A(a)) \le 1$ for all $a$.

Now we perform Gaussian elimination on the augmented matrix using the elementary row operation $R_2 \leftarrow R_2 - a R_1$:

$$
\begin{aligned}
r_{21} &= a - a(1) = 0 \\
r_{22} &= a - a(1) = 0 \\
r_{23} &= 4 - a(2) = 4 - 2a
\end{aligned}
$$

The augmented matrix in row echelon form is:

$$
\begin{pmatrix}
1 & 1 & \mid & 2 \\
0 & 0 & \mid & 4 - 2a \\
\end{pmatrix}.
$$

3. **Variable Evaluation & Case Analysis:**
We examine the second row $0x + 0y = 4 - 2a$, which is equivalent to $0 = 4 - 2a$:

- **Possibility 1: Exactly One Solution**
  A linear system with a square coefficient matrix has a unique solution if and only if $\det A \neq 0$ (full rank $\mathrm{rank}(A) = 2$).
  Because $\det A(a) = 0$ for all $a \in \mathbb{R}$, the coefficient matrix is singular for every choice of $a$.
  Therefore, **the case of exactly one solution can never occur**.

- **Possibility 2: Infinitely Many Solutions**
  For the system to be consistent, the second equation $0 = 4 - 2a$ must hold:

$$
4 - 2a = 0 \iff 2a = 4 \iff a = 2.
$$

  When $a = 2$, the augmented matrix becomes:

$$
\begin{pmatrix}
1 & 1 & \mid & 2 \\
0 & 0 & \mid & 0 \\
\end{pmatrix}.
$$

  Here, $\mathrm{rank}(A) = \mathrm{rank}([A \mid b]) = 1 < 2$. The second equation is an exact scalar multiple of the first ($2x + 2y = 4 \iff x + y = 2$).
  Setting the free variable $y = t$ ($t \in \mathbb{R}$), we obtain:

$$
x = 2 - t, \qquad y = t, \qquad t \in \mathbb{R}.
$$

  Therefore, the system has **infinitely many solutions** if and only if $a = 2$.

- **Possibility 3: No Solution**
  If $4 - 2a \neq 0$ (which means $a \neq 2$), the second row represents:

$$
0x + 0y = 4 - 2a \implies 0 = 4 - 2a \neq 0.
$$

  This is a contradiction ($0 \neq 0$).
  In terms of ranks:

$$
\mathrm{rank}(A) = 1, \qquad \mathrm{rank}([A \mid b]) = 2.
$$

  Since $\mathrm{rank}(A) < \mathrm{rank}([A \mid b])$, the system is inconsistent.
  Therefore, the system has **no solution** for all $a \in \mathbb{R} \setminus \{2\}$.

## Final Answer

- **Exactly one solution:** Never occurs for any value of $a$ (because $\det A(a) = 0$ identically).
- **Infinitely many solutions:** Occurs if and only if $a = 2$, with solution set:

$$
\begin{pmatrix}
x \\
y \\
\end{pmatrix} =
\begin{pmatrix}
2 - t \\
t \\
\end{pmatrix}, \qquad t \in \mathbb{R}
$$

- **No solution:** Occurs for all $a \in \mathbb{R} \setminus \{2\}$.
