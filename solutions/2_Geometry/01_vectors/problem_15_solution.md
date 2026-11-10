# Problem 15 Solution

## Problem Statement
Given

$$
a=(1,2,1),\qquad b=(2,4,2),\qquad c=(2,0,3).
$$

For each pair, compute

$$
\frac{u\cdot v}{\|u\|\,\|v\|}.
$$

Order the pairs by increasing angle between the vectors. Explain why for $a$ and $b$ the value is $1$ even though the vectors have different lengths.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Cosine of the Angle Between Two Vectors: For non-zero vectors $u$ and $v$, the angle $\theta \in [0, \pi]$ between them satisfies:

$$
\cos \theta = \frac{u \cdot v}{\|u\| \, \|v\|}
$$

- Dot Product (Component-wise):

$$
u \cdot v = u_1 v_1 + u_2 v_2 + u_3 v_3
$$

- Euclidean Norm in $\mathbb{R}^3$:

$$
\|u\| = \sqrt{u_1^2 + u_2^2 + u_3^2}
$$

- Cosine Bounds: $\cos \theta = 1 \iff \theta = 0^\circ$ (vectors parallel, same orientation); $\cos \theta = -1 \iff \theta = 180^\circ$ (antiparallel).
- Direction vs. Length: The cosine formula measures angular separation between direction vectors; magnitude scaling by a positive scalar does not change the direction and therefore does not change the angle.
- Formatting Standards: Display math with `$$` on separate lines, no `\text` macros, and all arithmetic products and square roots stated in full.

## Detailed Step-by-Step Solution
1. **Vector Setup & Formula Selection:**
We are given three vectors in $\mathbb{R}^3$:

$$
a = (1, 2, 1), \qquad b = (2, 4, 2), \qquad c = (2, 0, 3)
$$

There are three vector pairs: $(a, b)$, $(a, c)$, and $(b, c)$. For each pair we compute the dot product, the individual norms, and the cosine ratio. We then determine the exact angles $\theta$, order the pairs from smallest to largest angle, and explain the geometric reason behind $\cos \theta_{ab} = 1$.

2. **Intermediate Calculations:**
- **Step 1: Compute the norms $\|a\|$, $\|b\|$, $\|c\|$:**
For $a = (1, 2, 1)$:

$$
\begin{aligned}
\|a\| &= \sqrt{1^2 + 2^2 + 1^2} \\
      &= \sqrt{1 + 4 + 1} \\
      &= \sqrt{6}
\end{aligned}
$$

For $b = (2, 4, 2)$:

$$
\begin{aligned}
\|b\| &= \sqrt{2^2 + 4^2 + 2^2} \\
      &= \sqrt{4 + 16 + 4} \\
      &= \sqrt{24} \\
      &= \sqrt{4 \cdot 6} \\
      &= 2\sqrt{6}
\end{aligned}
$$

For $c = (2, 0, 3)$:

$$
\begin{aligned}
\|c\| &= \sqrt{2^2 + 0^2 + 3^2} \\
      &= \sqrt{4 + 0 + 9} \\
      &= \sqrt{13}
\end{aligned}
$$

- **Step 2: Pair $(a, b)$ — compute $a \cdot b$ and $\cos \theta_{ab}$:**
Dot product:

$$
\begin{aligned}
a \cdot b &= (1)(2) + (2)(4) + (1)(2) \\
          &= 2 + 8 + 2 \\
          &= 12
\end{aligned}
$$

Product of norms:

$$
\|a\| \, \|b\| = \sqrt{6} \cdot 2\sqrt{6} = 2 \cdot (\sqrt{6})^2 = 2 \cdot 6 = 12
$$

Cosine of angle:

$$
\cos \theta_{ab} = \frac{a \cdot b}{\|a\| \, \|b\|} = \frac{12}{12} = 1
$$

Since $\cos \theta_{ab} = 1$, the angle is:

$$
\theta_{ab} = \arccos(1) = 0^\circ
$$

- **Step 3: Pair $(a, c)$ — compute $a \cdot c$ and $\cos \theta_{ac}$:**
Dot product:

$$
\begin{aligned}
a \cdot c &= (1)(2) + (2)(0) + (1)(3) \\
          &= 2 + 0 + 3 \\
          &= 5
\end{aligned}
$$

Product of norms:

$$
\|a\| \, \|c\| = \sqrt{6} \cdot \sqrt{13} = \sqrt{6 \cdot 13} = \sqrt{78}
$$

Cosine of angle:

$$
\cos \theta_{ac} = \frac{a \cdot c}{\|a\| \, \|c\|} = \frac{5}{\sqrt{78}}
$$

Numerical evaluation: $\sqrt{78} \approx 8.832$, so:

$$
\cos \theta_{ac} \approx \frac{5}{8.832} \approx 0.5661
$$

$$
\theta_{ac} = \arccos\left(\frac{5}{\sqrt{78}}\right) \approx 55.52^\circ
$$

- **Step 4: Pair $(b, c)$ — compute $b \cdot c$ and $\cos \theta_{bc}$:**
Dot product:

$$
\begin{aligned}
b \cdot c &= (2)(2) + (4)(0) + (2)(3) \\
          &= 4 + 0 + 6 \\
          &= 10
\end{aligned}
$$

Product of norms:

$$
\|b\| \, \|c\| = 2\sqrt{6} \cdot \sqrt{13} = 2\sqrt{78}
$$

Cosine of angle:

$$
\cos \theta_{bc} = \frac{b \cdot c}{\|b\| \, \|c\|} = \frac{10}{2\sqrt{78}} = \frac{5}{\sqrt{78}}
$$

Numerical evaluation: same denominator as pair $(a, c)$:

$$
\cos \theta_{bc} \approx 0.5661
$$

$$
\theta_{bc} = \arccos\left(\frac{5}{\sqrt{78}}\right) \approx 55.52^\circ
$$

3. **Evaluation, Ordering, and Explanation:**
- **Ordering by increasing angle:**

| Pair | $\cos \theta$ | Angle $\theta$ |
|------|--------------|----------------|
| $(a, b)$ | $1$ | $0^\circ$ |
| $(a, c)$ | $5/\sqrt{78} \approx 0.5661$ | $\approx 55.52^\circ$ |
| $(b, c)$ | $5/\sqrt{78} \approx 0.5661$ | $\approx 55.52^\circ$ |

Ordering from smallest to largest angle: **pair $(a, b)$** with $\theta = 0^\circ$, then **pairs $(a, c)$ and $(b, c)$** both tied at $\approx 55.52^\circ$.

- **Explanation of why $\cos \theta_{ab} = 1$ despite $\|a\| \neq \|b\|$:**
Observe that $b = 2a$:

$$
\begin{aligned}
2a &= 2(1, 2, 1) \\
   &= (2 \cdot 1, 2 \cdot 2, 2 \cdot 1) \\
   &= (2, 4, 2) \\
   &= b
\end{aligned}
$$

Vectors $a$ and $b$ are therefore parallel with the same orientation ($b$ is a positive scalar multiple of $a$ with scalar factor $2 > 0$). Two vectors that are positive scalar multiples of each other point in precisely the same direction and have $\theta = 0^\circ$.

The cosine formula measures the angular separation between the **direction** vectors, completely independently of their magnitudes. Scaling a vector by any positive constant rescales its length but preserves its direction and orientation, leaving the angle with any other vector unchanged. Because the $\|a\|\,\|b\|$ denominator also scales by the same factor of $2$, the two scaling factors cancel:

$$
\cos \theta_{ab} = \frac{a \cdot (2a)}{\|a\| \, \|2a\|} = \frac{2(a \cdot a)}{2\|a\|^2} = \frac{2\|a\|^2}{2\|a\|^2} = 1
$$

- **Why $(a, c)$ and $(b, c)$ give the same angle:**
Since $b = 2a$, any angle that $a$ makes with another vector $c$ must equal the angle $b$ makes with the same vector $c$. The scale factor of $2$ cancels in both the numerator and the denominator of the cosine formula:

$$
\cos \theta_{bc} = \frac{b \cdot c}{\|b\| \, \|c\|} = \frac{2a \cdot c}{2\|a\| \, \|c\|} = \frac{a \cdot c}{\|a\| \, \|c\|} = \cos \theta_{ac}
$$

## Final Answer

$$
\cos \theta_{ab} = 1 \implies \theta_{ab} = 0^\circ
$$

$$
\cos \theta_{ac} = \frac{5}{\sqrt{78}} \implies \theta_{ac} \approx 55.52^\circ
$$

$$
\cos \theta_{bc} = \frac{5}{\sqrt{78}} \implies \theta_{bc} \approx 55.52^\circ
$$

Order by increasing angle: pair $(a, b)$ at $0^\circ$, then pairs $(a, c)$ and $(b, c)$ both at $\approx 55.52^\circ$.
