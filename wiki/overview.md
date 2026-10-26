---
type: overview
title: Overview — Discrete Algebraic Structures (DAS, TUHH)
aliases: [Overview, Überblick, Startseite, Diskrete Algebraische Strukturen]
tags: [overview]
sources: [all]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Overview: Discrete Algebraic Structures

Start page of the wiki. Full catalog: [[index]]. Chronology: [[log]].

Status: **7 of 7 sources** in `raw/` ingested, **57 content pages**.

The module is taught in German (*Diskrete Algebraische Strukturen*); this wiki is written
in English, with the German term given in parentheses on first mention of each concept.

## The storyline of the module

The whole module can be read as a single line of thought:

> **Algebraic laws** describe how operations behave.
> **Algebraic structures** give names to sets carrying such operations.
> **Relations** provide the tool for turning one set into a new one (a quotient).
> **$\mathbb{Z}_n$** is that construction applied to $\mathbb{Z}$.
> **$K[x]_g$** is the same construction applied to polynomials.
> **Induction** is the proof technique, **combinatorics** the counting technique.

| Chapter | Hub page | Source |
|---|---|---|
| 1. Algebraic laws | [[algebraic-laws]] | `Rechengesetzte_das.pdf` |
| 2. Mathematical induction | [[mathematical-induction]] | `Induktion_das.pdf` |
| 3. Algebraic structures | [[algebraic-structures]] | `Algebraische_strukturen_das.pdf` |
| 4. Relations and permutations | [[relations-and-permutations]] | `relation_und_permutation_das.pdf` |
| 5. Residue class rings $\mathbb{Z}_n$ | [[residue-class-rings]] | `Zn_das.pdf` |
| 6. Polynomial rings $K[x]$ | [[polynomial-rings]] | `polynomring_das.pdf` |
| 7. Combinatorics | [[combinatorics]] | `kombinatorik_das.pdf` |

## The central analogy

The thread running through the second half of the module is the parallel between the
integers and the polynomials:

| | $\mathbb{Z}$ | $K[x]$ |
|---|---|---|
| size measure | absolute value $\lvert a\rvert$ | degree $\deg f$ |
| division with remainder | yes | yes (over a field) |
| "indecomposable" | prime | irreducible |
| quotient | $\mathbb{Z}_n$ | $K[x]_g$ |
| quotient is a field $\iff$ | $n$ prime | $g$ irreducible |
| units | $\gcd(a,n)=1$ | $\gcd(f,g)=1$ |
| computing an inverse | extended Euclid | extended Euclid |

See [[residue-class-rings]], [[polynomial-rings]], [[irreducibility-and-fields]].

## The four recurring techniques

1. **Tick off the axioms.** Proving something is a structure means checking closure,
   associativity, identity, inverses and commutativity in turn — or producing *one*
   counterexample. → [[properties-of-operations]],
   [[checking-properties-of-operations]], [[field-or-not]]
2. **Extended Euclid.** One algorithm, three uses: gcd, inverse in $\mathbb{Z}_n$, inverse
   in $K[x]_g$. → [[laws-of-gcd]], [[computing-inverses]]
3. **Mathematical induction.** Base case, hypothesis, step — in the two flavours
   summation formula and inequality. → [[mathematical-induction]]
4. **Recognise the model, read off the formula.** Combinatorics is classification, not
   calculation. → [[urn-model]], [[box-model]]

## Exam map

| Problem | Topic | Preparation |
|---|---|---|
| 1 | propositional logic / sets | [[laws-of-propositional-logic]], [[checking-tautologies]] |
| 2 | induction | [[mathematical-induction]] plus the five worked examples |
| 3 | combinatorics | [[counting-exercises]], [[double-counting]] |
| 4 | relations, Hasse diagrams, permutations | [[checking-relation-properties]], [[hasse-diagrams-of-divisors]], [[computing-with-permutations]] |
| 5 | $\mathbb{Z}_n$: units, inverses, powers | [[determining-units-and-zero-divisors]], [[computing-inverses]], [[modular-exponentiation]] |
| 6 | polynomial rings, finite fields | [[computing-in-polynomial-rings]], [[finite-fields]], [[field-or-not]] |

Cutting across these: [[algebraic-structures]] (structure proofs, homomorphisms) shows up
as a sub-question in several problems.

## Quality of the sources

The summaries are handwritten lecture notes and tutorial solutions. They are sound in
substance but contain **arithmetic and transcription errors**. Every computation in this
wiki was verified independently; every divergence is marked on the page with a
`> [!warning] Error in the source` callout.

| Source | errors found | of which substantive |
|---|---|---|
| Rechengesetzte | 2 | 0 (typos) |
| Induktion | 1 | 0 |
| Algebraische Strukturen | 4 | 1 ([[subgroup-proofs]], $D_3$ instead of $C_3$) |
| relation/permutation | 0 | – (2 spots illegible in the scan) |
| $\mathbb{Z}_n$ | 4 | 2 (wrong power, wrong modulus) |
| Polynomring | 2 | **2** (GF(16) product; $x^3+x+2$ over $\mathbb{Z}_3$ is **reducible**) |
| Kombinatorik | 4 | 1 (undefined multinomial coefficient) |

**So do not revise blindly from the summaries** — the two errors in the polynomial-ring
notes would produce wrong exam answers. Details: [[finite-fields]], [[field-or-not]].

## Next steps

Sensible extensions of this wiki — these require new sources or new queries, they cannot
be derived from what is already here:

- Ingest past exams with model solutions as further sources, to harden the
  problem-type tables.
- Generate a query page "formula sheet for the cheat sheet" from the existing pages.
- The Stirling numbers $S(n,k)$ still have no recurrence in the wiki — the sources give
  none.

## Sources

- all seven PDFs in `raw/` — see [[index]], section *Sources*
