---
type: example
title: Computing with permutations
aliases: [permutation arithmetic, Produkt und Inverses von Permutationen, Mit Permutationen rechnen]
tags: [permutations, example]
sources: [raw/relation_und_permutation_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Computing with permutations

Worked exam problems on [[permutation]] and [[signum]]. The problem statement is the
same every time: "Compute $\pi\tau$, $\tau\pi$ as well as $\pi^{-1}$ and give
$\operatorname{sgn}(\tau)$."

## Convention

The source computes $\pi\tau$ as composition **from right to left**:
$$(\pi\tau)(x) = \pi\bigl(\tau(x)\bigr).$$
This can be checked against the results below and agrees with the usual composition of
maps (Abbildungskomposition). Consequence: $\pi\tau \neq \tau\pi$ in general — the group
$S_n$ is **not commutative** for $n \ge 3$.

## Problem A (degree 9)

$$\pi = (1\,2\,4\,5)(7\,6)(8\,9), \qquad \tau = (1\,9\,8\,7)(2\,3\,4)$$

**Signum of $\tau$.** A 4-cycle and a 3-cycle:
$$\operatorname{sgn}(\tau) = (-1)^{4-1}\cdot(-1)^{3-1} = (-1)\cdot(+1) = -1$$

**$\pi\tau$.** Element by element, right first:

| $x$ | $\tau(x)$ | $\pi(\tau(x))$ |
|---|---|---|
| 1 | 9 | **8** |
| 8 | 7 | **6** |
| 6 | 6 | **7** |
| 7 | 1 | **2** |
| 2 | 3 | **3** |
| 3 | 4 | **5** |
| 5 | 5 | **1** |
| 4 | 2 | **4** (fixed point) |
| 9 | 8 | **9** (fixed point) |

$$\pi\tau = (1\,8\,6\,7\,2\,3\,5)(4)(9)$$

**$\tau\pi$.**
$$\tau\pi = (1\,3\,4\,5\,9\,7\,6)(2)(8)$$

Clearly visible: $\pi\tau \neq \tau\pi$, even though both consist of a 7-cycle and two
fixed points.

**$\pi^{-1}$.** Read each cycle backwards:
$$\pi^{-1} = (5\,4\,2\,1)(6\,7)(9\,8) = (1\,5\,4\,2)(6\,7)(8\,9)$$

Check: $\pi: 1\to2$, so $\pi^{-1}: 2\to1$ must hold — in the cycle $(1\,5\,4\,2)$, the $1$
follows the $2$. $\checkmark$

## Problem B (degree 8)

$$\pi = (1\,2\,3\,4\,5\,7\,6)(3\,8), \qquad \tau = (2\,1\,3)(4\,7)(5\,6)$$

**Signum of $\tau$.** A 3-cycle and two 2-cycles:
$$\operatorname{sgn}(\tau) = (-1)^{3-1}\cdot(-1)^{2-1}\cdot(-1)^{2-1} = (+1)(-1)(-1) = +1$$

The source solves this problem in **two-line notation (Zweizeilennotation)** instead of
cycles — this is often clearer for products, since one simply chains two tables one
after another:

$$\tau = \begin{pmatrix}1&2&3&4&5&6&7&8\\3&1&2&7&6&5&4&8\end{pmatrix}$$

To form $\pi\tau$, one reads off the image in the $\tau$ row and looks it up in $\pi$.

**$\pi^{-1}$ in two-line notation.** Rule: *swap the rows and reorder.*
One writes the bottom row on top, sorts the columns ascending by the new top row —
done.

> [!warning] Transcription uncertain
> The two-line notations on p. 7 and p. 15 contain entries in the scan that cannot be
> read unambiguously; some bottom rows do not appear bijective (duplicate values).
> This is most likely a **misreading of the handwriting**, not an error in the source.
> The result values of these two sub-problems are therefore not reproduced here. The
> cycle notations and all signum computations are legible and correct.

## Problem C: signum of inverses and products (p. 15)

$$\pi = (1\,2\,3\,4\,5)(6\,7\,8), \qquad \tau = (1\,2)(3\,4)(5\,6)(7\,8)$$

$$\operatorname{sgn}(\pi) = (-1)^{5-1}\cdot(-1)^{3-1} = (-1)^4 \cdot (-1)^2 = +1$$
$$\operatorname{sgn}(\tau) = \bigl[(-1)^{2-1}\bigr]^4 = (-1)^4 = +1$$
$$\operatorname{sgn}(\pi^{-1}) = +1 = \operatorname{sgn}(\pi)$$
$$\operatorname{sgn}(\pi\tau) = \operatorname{sgn}(\pi)\cdot\operatorname{sgn}(\tau) = 1\cdot1 = 1$$

$\pi^{-1}$ consists of the same cycle lengths as $\pi$ — that's why
$\operatorname{sgn}(\pi^{-1}) = \operatorname{sgn}(\pi)$ is always true, not just here.

## Key points

- **Signum first**: it only needs the cycle lengths, no need to compute the product.
- **Inverse in cycle notation** is pure backward reading — much faster than via two-line
  notation.
- **Product**: most safely done element-wise with a value table, then read off the cycle.
- The sum of all cycle lengths (including fixed points) must always equal the degree
  $n$ — the best check after each computation.

## Related

- [[permutation]] — definitions, notations, count $(n)_k$
- [[signum]] — rules for computing the sign
- [[subgroup-proofs]] — $A_n \le S_n$ follows from the product rule
- [[group-like-structures]] — $S_n$ as a non-abelian group

## Sources

- `raw/relation_und_permutation_das.pdf`, p. 4 (problem 1.5), p. 7 (problem 2.5), p. 15 (exercise 9.3)
