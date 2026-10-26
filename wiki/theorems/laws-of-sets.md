---
type: theorem
title: Laws of Sets
aliases: [set algebra laws, Rechengesetze für Mengen, Mengenalgebra]
tags: [foundations, algebraic-laws, set-theory]
sources: [raw/Rechengesetzte_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Laws of sets (Mengen)

## Statement

For all sets $A$, $B$ and $C$ the following algebraic laws hold:

**Commutative law**
$$A \cup B = B \cup A \qquad A \cap B = B \cap A$$

**Associative law**
$$A \cup (B \cup C) = (A \cup B) \cup C \qquad A \cap (B \cap C) = (A \cap B) \cap C$$

**Idempotent law**
$$A \cup A = A \qquad A \cap A = A$$

**Distributive law**
$$A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$$
$$A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$$

**De Morgan's laws**
$$A \setminus (B \cap C) = (A \setminus B) \cup (A \setminus C)$$
$$A \setminus (B \cup C) = (A \setminus B) \cap (A \setminus C)$$

**Absorption law**
$$A \cup (A \cap B) = A \qquad A \cap (A \cup B) = A$$

**Properties of the empty set**
$$A \cup \emptyset = A \qquad A \cap \emptyset = \emptyset$$

## Hypotheses

$A, B, C$ are arbitrary sets. No further restrictions.

## Proof idea

The source gives no proofs.

> [!inferred] not from the summaries
> Standard approach: show elementwise equality, i.e. $x \in \text{left}
> \iff x \in \text{right}$. The condition on the right side then reduces to a
> propositional logic law from [[laws-of-propositional-logic]]. Alternatively:
> $A = B$ via $A \subseteq B$ and $B \subseteq A$.

## Application / typical exam problem

- Simplifying set expressions.
- Proving set equalities (elementwise or via mutual inclusion).
- Venn diagrams for illustration — as a proof they usually don't suffice.

## Remarks

- **De Morgan with difference instead of complement**: the source states De Morgan
  without a universal set, only using the difference (Differenz) $A \setminus \cdot$.
  This is the more general variant and works without having to fix a universe. Rule of
  thumb, as in logic: "pulling out" the difference flips $\cap \leftrightarrow \cup$.
- The source only gives $A \cup \emptyset = A$ and $A \cap \emptyset = \emptyset$ for
  the empty set. The counterparts with a universal set $\Omega$ are not listed.
- Unlike propositional logic, everywhere here we have $=$ (set equality), not
  $\Leftrightarrow$.

## Related theorems

- [[algebraic-laws]] — overview and comparison of all five domains
- [[laws-of-propositional-logic]] — the structurally identical table of laws

## Sources

- `raw/Rechengesetzte_das.pdf`, p. 2
