---
type: example
title: Checking tautologies
aliases: [checking tautologies, Tautologien prüfen, Wahrheitstafel, truth table]
tags: [propositional-logic, example]
sources: [raw/relation_und_permutation_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Checking tautologies

Problems on the [[laws-of-propositional-logic|laws of propositional logic (Rechengesetze
der Aussagenlogik)]]. A **tautology** is a propositional form whose column in the truth
table (Wahrheitstafel) is $1$ throughout.

The source consistently shows **two approaches** and uses Boolean notation
($\cdot$ for $\wedge$, $+$ for $\vee$, $\overline{X}$ for $\neg X$, $w$/$f$ for true/false):

1. **Truth table** — $2^n$ rows for $n$ variables, filled in mechanically. Safe, but long.
2. **Rewriting** with the laws — faster, but requires confidence with distributivity and
   De Morgan.

## 1. $P \wedge R \wedge (P\Rightarrow Q) \wedge (R \Rightarrow \neg Q)$ is unsatisfiable

**Truth table.**

| $P$ | $Q$ | $R$ | $P\Rightarrow Q$ | $R\Rightarrow\neg Q$ | $P \wedge R \wedge (P\Rightarrow Q)\wedge(R\Rightarrow\neg Q)$ |
|---|---|---|---|---|---|
| 0 | 0 | 0 | 1 | 1 | **0** |
| 0 | 0 | 1 | 1 | 1 | **0** |
| 0 | 1 | 0 | 1 | 1 | **0** |
| 0 | 1 | 1 | 1 | 0 | **0** |
| 1 | 0 | 0 | 0 | 1 | **0** |
| 1 | 0 | 1 | 0 | 1 | **0** |
| 1 | 1 | 0 | 1 | 1 | **0** |
| 1 | 1 | 1 | 1 | 0 | **0** |

The column is constantly $0$ — the formula is a **contradiction**, so its negation
$\neg(\dots)$ is a tautology.

**By rewriting.** With $P\Rightarrow Q \equiv \overline{P}+Q$:
$$(\overline P + Q)(\overline R + \overline Q)\cdot P R$$
$$= RPP(\overline R + \overline Q) + RPQ\overline R + RPQ\overline Q$$
$$= f + f + f = f$$
Every summand contains a pair $X \cdot \overline X = f$, and $f \cdot B = f$. So
$\neg(\dots) = w$: **tautology**.

In terms of content: from $P$ follows $Q$, from $R$ follows $\neg Q$ — then $P$ and $R$
cannot hold simultaneously.

## 2. $\bigl((P\wedge Q)\vee(P\wedge R)\bigr) \Rightarrow P\wedge(Q\vee R)$

| $P$ | $Q$ | $R$ | $P\wedge Q$ | $P\wedge R$ | $(P\wedge Q)\vee(P\wedge R)$ | $Q\vee R$ | $P\wedge(Q\vee R)$ |
|---|---|---|---|---|---|---|---|
| 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| 1 | 0 | 1 | 0 | 1 | 1 | 1 | 1 |
| 1 | 1 | 0 | 1 | 0 | 1 | 1 | 1 |
| 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 | 0 | 0 | 1 | 0 |
| 0 | 0 | 1 | 0 | 0 | 0 | 1 | 0 |
| 0 | 1 | 0 | 0 | 0 | 0 | 1 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

The last two columns are **identical**, so the implication is $1$ everywhere:
**tautology**.

This was to be expected — it is exactly the **distributive law** from
[[laws-of-propositional-logic]], written here as an implication instead of an
equivalence.

## 3. Two implication formulas compared

$$P \Rightarrow (Q \Rightarrow P)$$

| $P$ | $Q$ | $Q\Rightarrow P$ | $P\Rightarrow(Q\Rightarrow P)$ |
|---|---|---|---|
| 1 | 1 | 1 | 1 |
| 1 | 0 | 1 | 1 |
| 0 | 1 | 0 | **1** |
| 0 | 0 | 1 | 1 |

**Tautology.** A true $P$ follows from anything.

$$(P \Rightarrow Q) \Rightarrow P$$

| $P$ | $Q$ | $P\Rightarrow Q$ | $(P\Rightarrow Q)\Rightarrow P$ |
|---|---|---|---|
| 1 | 1 | 1 | 1 |
| 1 | 0 | 0 | 1 |
| 0 | 1 | 1 | **0** |
| 0 | 0 | 1 | **0** |

**Not a tautology.** So the order of implications is not arbitrary —
$\Rightarrow$ is neither commutative nor associative.

## 4. Simplifying: $\neg(P\vee Q) \vee (\neg P \wedge Q) \equiv \neg P$

| $P$ | $\neg P$ | $Q$ | $\neg(P\vee Q)$ | $\neg P \wedge Q$ | $\neg(P\vee Q)\vee(\neg P\wedge Q)$ |
|---|---|---|---|---|---|
| 1 | 0 | 1 | 0 | 0 | 0 |
| 1 | 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 | 1 | 1 |
| 0 | 1 | 0 | 1 | 0 | 1 |

The last column matches $\neg P$.

**By rewriting** — first De Morgan, then distributivity, then complement:
$$\neg(P\vee Q)\vee(\neg P\wedge Q)
\;\overset{\text{De Morgan}}{=}\; (\neg P \wedge \neg Q)\vee(\neg P \wedge Q)$$
$$\overset{\text{Distrib.}}{=}\; \neg P \wedge (\neg Q \vee Q)
\;\overset{\text{Complement}}{=}\; \neg P \wedge w = \neg P$$

The law used, $(a\wedge b)\vee(a\wedge c) = a\wedge(b\vee c)$, is written explicitly next
to it in the source.

## Key points

- Truth table = **proof by exhaustion**, rewriting = **proof by calculation**. For 2–3
  variables the table is usually faster; from 4 variables on ($16$ rows), rewriting pays
  off.
- When rewriting, first eliminate all $\Rightarrow$ via $P\Rightarrow Q \equiv \neg P \vee Q$
  — only then do the Boolean laws apply.
- $X \wedge \neg X = f$ and $X \vee \neg X = w$ are the closing rules that almost every
  rewriting ends up using.

## Related

- [[laws-of-propositional-logic]] — the table of laws
- [[algebraic-laws]] — overview of all collections of laws
- [[laws-of-sets]] — the same laws for $\cap, \cup, \overline{\phantom{A}}$

## Sources

- `raw/relation_und_permutation_das.pdf`, p. 2 (problem 1.1), p. 5/7 (problem 2.1),
  p. 8 (exercise 1, formal theorems)
