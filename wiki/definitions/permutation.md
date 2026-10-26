---
type: definition
title: Permutation
aliases: [permutation, Permutation, k-permutation, k-Permutation, cycle notation, Zykelschreibweise, two-line notation, Zweizeilennotation, symmetric group, symmetrische Gruppe]
tags: [permutations, combinatorics]
sources: [raw/relation_und_permutation_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Permutation

## Definition

Let $x = x_1 \dots x_k$ be a **word** of length $k$ over $\underline{n} = \{1,\dots,n\}$.

$x$ is called a **$k$-permutation of $n$** $:\Longleftrightarrow$ no symbol occurs more
than once in $x$.

**Connection to maps.** Every $k$-permutation $x = x_1 \dots x_k$ induces a map
$$f_x = \begin{pmatrix} 1 & 2 & \dots & k \\ x_1 & x_2 & \dots & x_k \end{pmatrix}
: \underline{k} \to \underline{n}.$$
The assignment $x \mapsto f_x$ is a **bijection** between the $k$-permutations of $n$ and
the **injective** maps $\underline{k} \to \underline{n}$.

**Count.** For $1 \leq k \leq n$:
$$(n)_k = n \cdot (n-1) \cdot \dots \cdot (n-k+1)$$

**Case $k = n$.** Every $n$-permutation of $n$ is a **bijective** map
$\underline{n} \to \underline{n}$, and
$$(n)_n = n!$$
These form the symmetric group (*symmetrische Gruppe*) $S_n$.

## Two notations

**Two-line notation** (*Zweizeilennotation*) — preimages on top, images below:
$$\pi = \begin{pmatrix} 1&2&3&4&5&6&7&8 \\ 2&3&4&5&1&7&8&6 \end{pmatrix}$$

**Cycle notation** (*Zykelschreibweise*) — trace where an element wanders until you're
back at the start:
$$\pi = (1\,2\,3\,4\,5)(6\,7\,8)$$
Read: $1 \mapsto 2 \mapsto 3 \mapsto 4 \mapsto 5 \mapsto 1$ and $6 \mapsto 7 \mapsto 8 \mapsto 6$.

Fixed points are written as 1-cycles or omitted.

## Computing with permutations

**Inverse.** The source's rule: "swap rows and reorder!"
$$\pi^{-1}: \text{ swap the two rows, then sort the columns by the top row}$$
In cycle notation: **read each cycle backwards**, e.g.
$$\pi = (1\,2\,4\,5)(7\,6)(8\,9) \;\Longrightarrow\;
\pi^{-1} = (5\,4\,2\,1)(6\,7)(9\,8) = (1\,5\,4\,2)(6\,7)(8\,9)$$

**Product.** $\pi\tau$ is evaluated by sending an element through both permutations and
decomposing the result back into cycles.

Worked-out examples: [[computing-with-permutations]].

## Example: $S_3$ as symmetries of the triangle

The $3$-permutations of $3$, i.e. $3! = 6$ of them:

| | Two-line notation | Word | geometrically |
|---|---|---|---|
| $\mathrm{id}$ | $\binom{1\,2\,3}{1\,2\,3}$ | $123$ | rotation by $0°$ |
| $s_1$ | $\binom{1\,2\,3}{2\,3\,1}$ | $231$ | rotation |
| $s_2$ | $\binom{1\,2\,3}{3\,1\,2}$ | $312$ | rotation |
| $r_1$ | $\binom{1\,2\,3}{1\,3\,2}$ | $132$ | reflection |
| $r_2$ | $\binom{1\,2\,3}{3\,2\,1}$ | $321$ | reflection |
| $r_3$ | $\binom{1\,2\,3}{2\,1\,3}$ | $213$ | reflection |

$\mathrm{id}, s_1, s_2$ are the **rotations**, $r_1, r_2, r_3$ the **reflections** of an
equilateral triangle. The rotations form a subgroup — proved in [[subgroup-proofs]]:

| $\circ$ | $\mathrm{id}$ | $s_1$ | $s_2$ |
|---|---|---|---|
| $\mathrm{id}$ | $\mathrm{id}$ | $s_1$ | $s_2$ |
| $s_1$ | $s_1$ | $s_2$ | $\mathrm{id}$ |
| $s_2$ | $s_2$ | $\mathrm{id}$ | $s_1$ |

## Related

- [[signum]] — the sign of a permutation
- [[computing-with-permutations]] — products, inverses, signum worked out
- [[group-like-structures]] — $S_n$ is a group
- [[subgroup-proofs]] — $A_n$ and the rotation group as subgroups
- [[klein-four-group]] — every group can be written as a permutation group
- [[urn-model]] — $(n)_k$ as a counting coefficient in the urn model
- [[combinatorics]] — combinatorics chapter overview
- [[counting-exercises]] — the six symmetries of the equilateral triangle

## Note on the source

The formula $(n)_k$ is first mistakenly written on p. 13 as "$n \cdot \ldots \cdot n$"
and only spelled out correctly on p. 14 as $n(n-1)\cdots(n-k+1)$. In the example
"$2$-permutations of $4$" the list in the scan is partly illegible; it should read
$12,21,13,31,14,41,23,32,24,42,34,43$ — that is $(4)_2 = 4 \cdot 3 = 12$ of them.

## Sources

- `raw/relation_und_permutation_das.pdf`, p. 13, p. 14, p. 15
