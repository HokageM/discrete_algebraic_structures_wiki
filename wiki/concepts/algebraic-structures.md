---
type: concept
title: Algebraic Structures
aliases: [algebraic structures, Algebraische Strukturen, Strukturübersicht]
tags: [algebraic-structures, overview]
sources: [raw/Algebraische_strukturen_das.pdf, raw/Rechengesetzte_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Algebraic Structures

## Core idea

An algebraic structure is a **set together with one or two operations**
(*Verknüpfungen*) that satisfy a fixed list of properties. The names (semigroup
(*Halbgruppe*), monoid, group (*Gruppe*), ring (*Ring*), field (*Körper*)) are nothing more
than abbreviations for such property lists.

This is the answer to the observation from [[algebraic-laws]]: there it stood out that
logic, sets, $\mathbb{N}$, $\mathbb{Z}$, and the gcd keep obeying the same laws. Instead of
proving each law five times, you name the lists of laws — and prove theorems once and for
all at that level.

## Connections

### The structure of the chapter

```
Properties of operations               ← the building blocks
  ├── one operation    → group-like structures
  │                        semigroup ⊃ monoid ⊃ group ⊃ abelian group
  └── two operations    → ring-like structures
                           ring ⊃ commutative ring ⊃ integral domain ⊃ field

Two tools for working with them:
  substructures     — proving structure by inheriting from above
  homomorphisms     — comparing structures with each other
```

Pages:

- [[properties-of-operations]] — closure (*Abgeschlossenheit*), associativity, identity element, inverses, commutativity
- [[group-like-structures]] — $(G, \circ)$: semigroup, monoid, group, abelian group
- [[ring-like-structures]] — $(R, +, \cdot)$: ring, integral domain, field
- [[substructures]] — submonoid, subgroup, subring
- [[homomorphism]] — mono-, epi-, iso-, endo-, automorphism

### The two basic techniques

Almost every problem in this chapter is one of two kinds:

| Question | Technique | Scheme | Examples |
|---|---|---|---|
| "Is $U$ a group / a monoid?" | [[substructures]] | 2–3 closure checks, the rest is inherited | [[submonoid-proofs]], [[subgroup-proofs]] |
| "Are $A$ and $B$ built the same way?" | [[homomorphism]] | compatibility + distinguished elements, possibly bijectivity | [[homomorphism-proofs]], [[klein-four-group]] |

Always preceding this is the question of which [[properties-of-operations|properties]]
the operation actually has — see [[checking-properties-of-operations]].

### Connection to the algebraic laws

The concrete law tables from [[algebraic-laws]] can now be classified:

| Concrete | Structure |
|---|---|
| $(\mathbb{N}_0, +, 0)$, [[laws-of-natural-numbers]] | commutative monoid (no inverse) |
| $(\mathbb{Z}, +, \cdot)$, [[laws-of-integers]] | commutative ring, even an integral domain |
| $(\mathbb{Q}, +, \cdot)$ | field |
| $\vee, \wedge$ on propositions, [[laws-of-propositional-logic]] | each a commutative, idempotent monoid |
| $\cup, \cap$ on sets, [[laws-of-sets]] | ditto |

The **cancellation law** in $\mathbb{Z}$ is exactly the zero-divisor-freeness that turns a
commutative ring into an integral domain.

> [!inferred] not from the summaries
> The source does not draw up this mapping table; it connects two chapters that are
> separate in the summaries. However, the individual classifications follow directly from
> comparing the two law tables.

## Open questions

- **Kernel and image** (*Kern und Bild*) of homomorphisms do not appear; neither do normal
  subgroups, cosets, quotient groups, or the theorem of Lagrange. Whether the module
  covers them is to be checked when ingesting the remaining sources.
- The source contains **no numbered definitions/theorems**, only overview sheets and
  exercises. A numbering like "Theorem 3.2" therefore possibly does not exist in the
  module.
- The term **order** (*Ordnung*, of a group or an element) is completely missing.
- The source repeats itself: p. 1 ≈ p. 11, p. 2 ≈ p. 7 + p. 9. The overview sheets exist
  in both a filled-in and a blank version.

## Sources

- `raw/Algebraische_strukturen_das.pdf`, p. 1–14
- `raw/Rechengesetzte_das.pdf` (for the mapping table)
