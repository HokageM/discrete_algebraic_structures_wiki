---
type: theorem
title: Laws of Propositional Logic
aliases: [laws of propositional logic, Rechengesetze der Aussagenlogik, Aussagenlogik Rechengesetze]
tags: [foundations, algebraic-laws, propositional-logic]
sources: [raw/Rechengesetzte_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Laws of propositional logic (Aussagenlogik)

## Statement

For all propositions (Aussageformen) $P$, $Q$ and $R$ the following algebraic laws hold:

**Commutative law**
$$P \vee Q \;\Leftrightarrow\; Q \vee P \qquad P \wedge Q \;\Leftrightarrow\; Q \wedge P$$

**Associative law**
$$P \vee (Q \vee R) \;\Leftrightarrow\; (P \vee Q) \vee R \qquad
P \wedge (Q \wedge R) \;\Leftrightarrow\; (P \wedge Q) \wedge R$$

**Idempotent law**
$$P \vee P \;\Leftrightarrow\; P \qquad P \wedge P \;\Leftrightarrow\; P$$

**Distributive law**
$$P \vee (Q \wedge R) \;\Leftrightarrow\; (P \vee Q) \wedge (P \vee R)$$
$$P \wedge (Q \vee R) \;\Leftrightarrow\; (P \wedge Q) \vee (P \wedge R)$$

**De Morgan's laws** (1806–1878)
$$\neg(P \wedge Q) \;\Leftrightarrow\; \neg P \vee \neg Q \qquad
\neg(P \vee Q) \;\Leftrightarrow\; \neg P \wedge \neg Q$$

**Absorption law**
$$P \vee (P \wedge Q) \;\Leftrightarrow\; P \qquad P \wedge (P \vee Q) \;\Leftrightarrow\; P$$

**Law of double negation**
$$\neg(\neg P) \;\Leftrightarrow\; P$$

**Laws involving true and false propositions** ($w$ = true, $f$ = false)
$$\neg P \wedge P \;\Leftrightarrow\; f \qquad \neg P \vee P \;\Leftrightarrow\; w$$
$$P \vee f \;\Leftrightarrow\; P \qquad P \vee w \;\Leftrightarrow\; w$$

## Hypotheses

$P, Q, R$ are arbitrary propositions. There are no further restrictions — all laws
hold unconditionally.

## Proof idea

The source gives no proofs.

> [!inferred] not from the summaries
> Each of these laws can be verified with a **truth table** (Wahrheitstafel): 4 rows
> for two variables, 8 rows for three variables. One checks that the left and right
> sides have the same truth value in every row.

## Application / typical exam problem

- Simplifying propositions (e.g. bringing them into a normal form using absorption
  and De Morgan).
- Pulling negations inward: $\neg(P \wedge Q)$ becomes $\neg P \vee \neg Q$. Rule of
  thumb: negating flips $\wedge \leftrightarrow \vee$.
- Showing equivalence of two expressions — either via a truth table or by stepwise
  rewriting with these laws.

## Remarks

- **Duality**: if in every law one simultaneously swaps $\vee \leftrightarrow \wedge$
  and $w \leftrightarrow f$, one again obtains a valid law. The laws therefore come in
  pairs.
- The last two lines of the source only give $P \vee f \Leftrightarrow P$ and
  $P \vee w \Leftrightarrow w$; the dual variants $P \wedge w \Leftrightarrow P$ and
  $P \wedge f \Leftrightarrow f$ are **not** listed in the source but follow from
  duality.

## Related theorems

- [[algebraic-laws]] — overview and comparison of all five domains
- [[laws-of-sets]] — the same laws with $\cup, \cap$ instead of $\vee, \wedge$
- [[checking-tautologies]] — the laws applied: truth tables and rewriting

## Sources

- `raw/Rechengesetzte_das.pdf`, p. 1
