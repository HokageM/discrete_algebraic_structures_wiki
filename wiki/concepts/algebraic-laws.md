---
type: concept
title: Algebraic Laws
aliases: [algebraic laws, Rechengesetze, Rechenregeln]
tags: [foundations, algebraic-laws]
sources: [raw/Rechengesetzte_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Algebraic Laws

## Core idea

Five completely different areas of the module — propositional logic (*Aussagenlogik*),
sets, $\mathbb{N}$, $\mathbb{Z}$, and the gcd (*ggT*) — obey **the same structural laws**.
Commutativity, associativity, idempotence, distributivity, De Morgan, and absorption keep
reappearing, just with different operations.

This very repetition is the reason structures are studied abstractly: you prove a law once
at the level of the structure instead of five times for five different areas.

The pair $(\vee, \wedge)$ in logic and $(\cup, \cap)$ for sets behave in exactly the same
way. $(+, \cdot)$ on $\mathbb{N}$ and $\mathbb{Z}$, on the other hand, behave differently:
here there is **no** idempotence, **no** absorption, and distributivity holds only in
*one* direction ($\cdot$ over $+$, not the other way around).

## Connections

Overview of all five areas from the source:

| Law | Propositions $\vee,\wedge$ | Sets $\cup,\cap$ | $\mathbb{N}$: $+,\cdot$ | $\mathbb{Z}$: $+,\cdot$ | gcd $(a,b)$ |
|---|:---:|:---:|:---:|:---:|:---:|
| Commutative    | ✓ | ✓ | ✓ | ✓ | ✓ |
| Associative    | ✓ | ✓ | ✓ | ✓ | ✓ |
| Idempotence    | ✓ | ✓ | – | – | ✓ (as $(a,a)=\lvert a\rvert$) |
| Distributive   | ✓ both ways | ✓ both ways | only $\cdot$ over $+$ | only $\cdot$ over $+$ | ✓ (as $a\cdot(b,c)=(ab,ac)$) |
| De Morgan     | ✓ | ✓ | – | – | – |
| Absorption    | ✓ | ✓ | – | – | – |
| Identity elements | $f$ for $\vee$, $w$ for $\wedge$ | $\emptyset$ for $\cup$ | $0$ for $+$, $1$ for $\cdot$ | $0$ for $+$, $1$ for $\cdot$ | $(0,a)=\lvert a\rvert$ |
| Cancellation law | – | – | ✓ | ✓ | – |

Detail pages:

- [[laws-of-propositional-logic]] — $\vee, \wedge, \neg$ on propositional forms
- [[laws-of-sets]] — $\cup, \cap, \setminus$ on sets
- [[laws-of-natural-numbers]] — $+, \cdot$ on $\mathbb{N}$
- [[laws-of-integers]] — $+, \cdot$ on $\mathbb{Z}$
- [[laws-of-gcd]] — the gcd as an operation $(a,b)$

### The logic–sets correspondence

The laws of [[laws-of-propositional-logic]] and [[laws-of-sets]] are identical
line by line.

| Logic | Sets |
|---|---|
| $\vee$ | $\cup$ |
| $\wedge$ | $\cap$ |
| $\neg$ | complement / $A \setminus \cdot$ |
| $f$ (false) | $\emptyset$ |
| $w$ (true) | universal set |
| $\Leftrightarrow$ | $=$ |

> [!inferred] not from the summaries
> The *reason* for the correspondence — $x \in A \cup B \iff (x \in A) \vee (x \in B)$ and
> $x \in A \cap B \iff (x \in A) \wedge (x \in B)$, so every set law is a propositional
> logic law applied to the membership statement — is not stated in the source. Likewise
> the name *Boolean lattice* for this shared structure.

Note the notational difference: in logic $\Leftrightarrow$ is used (equivalence of
propositional forms), for sets $=$ is used (equality of sets).

### Why numbers are the exception

$+$ and $\cdot$ are **not idempotent** ($2+2 \neq 2$) and satisfy **no absorption**.
Distributivity holds only in one direction: $l\cdot(m+n) = l\cdot m + l\cdot n$ is true,
but $l + (m \cdot n) = (l+m)\cdot(l+n)$ is false. In exchange, numbers have something logic
and sets don't: **cancellation laws**.

## Open questions

- The source lists the laws without proofs. Where the proofs are actually carried out
  (truth table? induction? Peano axioms?) does not become clear from this source — to be
  clarified when ingesting `Induktion_das.pdf` and `Algebraische_strukturen_das.pdf`.
- Whether the module explicitly introduces the terms *Boolean algebra* / *lattice*
  (*Verband*) is still open. If so, this page should later be linked there.
- The source never names a shared abstract structure (semigroup, monoid, ring). That
  connection is to be drawn when ingesting `Algebraische_strukturen_das.pdf`.
  **→ done:** see [[algebraic-structures]] with the mapping table.

## Sources

- `raw/Rechengesetzte_das.pdf`, p. 1–5
