---
type: concept
title: Relations and Permutations
aliases: [relations and permutations, Relationen und Permutationen, Ordnungen, Kapitelübersicht Relationen]
tags: [hub, relations, permutations]
sources: [raw/relation_und_permutation_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Relations and Permutations

Hub page for the chapter. The source covers two topics that at first glance seem to have
little to do with each other — in fact both are **special cases of subsets of
$A \times B$**: a relation is any such subset, a permutation a bijective map, i.e. a
particularly regular relation.

## The map

```
Relation R ⊆ A × B
    │
    ├── homogeneous (A = B) ──┬── reflexive
    │                         ├── symmetric        → equivalence relation
    │                         ├── antisymmetric    → order → Hasse diagram
    │                         └── transitive
    │
    └── mapping (each x has exactly one image)
            │
            └── bijective, A = B = {1..n} ── permutation → S_n, sgn, A_n
```

## Pages of this chapter

### Relations

| Page | Content |
|---|---|
| [[relation]] | definition, relation product $R\circ S$, inverse relation $R^{-1}$, digraph |
| [[properties-of-homogeneous-relations]] | reflexive, symmetric, antisymmetric, transitive — and how to read them off the digraph |
| [[equivalence-relation]] | reflexive + symmetric + transitive; classes, quotient set |
| [[hasse-diagram]] | drawing order relations without loops and transitive edges |

### Permutations

| Page | Content |
|---|---|
| [[permutation]] | $k$-permutation, two-line and cycle notation, $(n)_k$, $n!$ |
| [[signum]] | $\operatorname{sgn}$, cycle-length rule, product rule |

### Worked problems

| Page | Content |
|---|---|
| [[checking-relation-properties]] | six relations checked against all four properties |
| [[equivalence-relation-proofs]] | $f(x)=f(y)$ and $3 \mid a^2-b^2$ fully proven |
| [[hasse-diagrams-of-divisors]] | divisors of $28$, $36$, $72$ |
| [[computing-with-permutations]] | $\pi\tau$, $\tau\pi$, $\pi^{-1}$, $\operatorname{sgn}$ |
| [[checking-tautologies]] | truth tables — as a "mixed topic" in the same source |

## The three basic techniques

**1. Draw the digraph, then read off.** The four properties of homogeneous relations each
have a visual pattern:

| Property | in the digraph |
|---|---|
| reflexive | a loop $\circlearrowright$ at **every** node |
| symmetric | **every** arrow is a double arrow $\leftrightarrow$ |
| antisymmetric | **no** double arrow between distinct nodes |
| transitive | every path of length 2 has a shortcut |

**2. Tick off three properties.** For an equivalence proof, always check reflexive →
symmetric → transitive individually, then determine the classes.

**3. Cycles instead of tables.** Permutations are almost always faster to handle in cycle
notation: inverse = read backwards, signum = read off cycle lengths.

## Cross-connections to other chapters

- $S_n$ is a [[group-like-structures|group]], $A_n$ a
  [[substructures|subgroup]] — cf. [[subgroup-proofs]].
- $\operatorname{sgn} : S_n \to \{\pm1\}$ is a [[homomorphism|group homomorphism]].
- Every group can be realized as a permutation group — [[klein-four-group]].
- The divisibility relation orders the [[hasse-diagrams-of-divisors|divisor sets]]; the
  corresponding laws are in [[laws-of-gcd]].
- The congruence $a \equiv b \pmod n$ is the most important equivalence relation of the
  module — it leads to $\mathbb{Z}_n$.
- [[checking-tautologies]] uses [[laws-of-propositional-logic]].
- The number $(n)_k$ of $k$-permutations of $n$ is a counting coefficient from
  [[combinatorics]] — see [[urn-model]] and [[box-model]].

## Sources

- `raw/relation_und_permutation_das.pdf` (15 pages)
