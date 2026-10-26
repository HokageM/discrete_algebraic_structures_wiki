---
type: definition
title: Partitions, Stirling and Bell numbers
aliases: [partition, Zahlpartition, Mengenpartition, Stirling number, Stirling-Zahl, Bell number, Bell-Zahl, integer partition, set partition]
tags: [combinatorics]
sources: [raw/kombinatorik_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Partitions, Stirling and Bell numbers

Four related counting quantities that appear in the table of the
[[box-model|box model]] (*Fächermodell*). They are easily confused — the difference lies
in **what is being decomposed** (a number or a set) and **whether order matters**.

## Integer partitions

A **$k$-integer partition of $n$** (*Zahlpartition*) is a decomposition of the number $n$
into $k$ positive summands.

**Unordered** — $P(n,k)$: order of the summands does not matter.
**Ordered** — $p(n,k) = \dbinom{n-1}{k-1}$: order matters (also called a *composition*).

**Example from the source: 2-integer partitions of 5**

| | Representations | Count |
|---|---|---|
| unordered | $14$, $23$ | $P(5,2) = 2$ |
| ordered | $14$, $41$, $23$, $32$ | $p(5,2) = \binom41 = 4$ |

The source explicitly notes $14 = 41$ in the unordered case.

**The formula $p(n,k) = \binom{n-1}{k-1}$** ("stars and bars"): write $n$ ones in a row
and place a divider in $k-1$ of the $n-1$ gaps.

## Set partitions: Stirling number of the second kind

$S(n,k)$ = number of decompositions of an **$n$-element set** into $k$ nonempty,
indistinguishable blocks.

**Example from the source: all 3-partitions of $\{1,2,3,4\}$**

The block-size profile is necessarily $4 = 1+1+2$, since three nonempty blocks from four
elements admit only this split. What remains is the question of **which two** elements
end up together:

$$\{\{1\},\{2\},\{3,4\}\},\quad \{\{1\},\{2,3\},\{4\}\},\quad \{\{1,3\},\{2\},\{4\}\},$$
$$\{\{1\},\{2,4\},\{3\}\},\quad \{\{1,4\},\{2\},\{3\}\},\quad \{\{1,2\},\{3\},\{4\}\}$$

$$S(4,3) = \binom42 = 6$$

The count is exactly the choice of the pair block.

> [!inferred] not from the summaries
> The identity $S(n, n-1) = \binom n2$ is not in the source, but explains why exactly
> $6$ comes out here.

## Bell number

$$B(n) = \sum_{i=1}^{n} S(n,i)$$

The number of **all** set partitions of an $n$-element set, without fixing the number
of blocks. In the table of the [[box-model|box model]] it appears in the row
"balls yes, boxes no", column "arbitrary", for the case $k = n$.

## Overview

| Symbol | what is decomposed | order | formula / example |
|---|---|---|---|
| $P(n,k)$ | number $n$ | irrelevant | $P(5,2)=2$ |
| $p(n,k)$ | number $n$ | matters | $\binom{n-1}{k-1}$ |
| $S(n,k)$ | set $\underline n$ | irrelevant (blocks) | $S(4,3)=6$ |
| $B(n)$ | set $\underline n$ | irrelevant, $k$ free | $\sum_i S(n,i)$ |

**Connection to surjective maps:**
$$\#\{\text{surjective } \underline n \to \underline k\} = k!\cdot S(n,k)$$
The preimage set is partitioned into $k$ blocks ($S(n,k)$ possibilities), and the blocks
are then distributed onto the $k$ distinguishable boxes ($k!$ possibilities).

## Notation pitfall in the source

On p. 1, **both** kinds of partition are denoted with the same uppercase $P(n,k)$:

> "$P(n,k) = \#$ unordered $k$-integer partitions of $n$" … "$P(n,k) = \#$ ordered
> $k$-integer partition of $n$"

In the table on p. 2 and p. 6, however, a clean distinction is made between $P(n,k)$
(unordered) and $p(n,k)$ (ordered, $=\binom{n-1}{k-1}$). **The table is authoritative**;
the notation on p. 1 is a slip.

Second pitfall: "3-partition of 4" can mean either an *integer partition* or a *set
partition*. In the problem on p. 4/5, **set partitions** are meant (answer: 6); as an
integer partition the answer would be $P(4,3) = 1$, namely $4 = 1+1+2$. The source
writes both one below the other — first the integer partition $4 = 1+1+2$ as an
intermediate step, then the six set partitions as the answer.

## Related

- [[box-model]] — where these quantities sit in the table
- [[urn-model]] — the simpler case
- [[counting-exercises]] — worked-out problems
- [[combinatorics]] — chapter overview

## Sources

- `raw/kombinatorik_das.pdf`, p. 1, p. 2, p. 4, p. 5, p. 6
