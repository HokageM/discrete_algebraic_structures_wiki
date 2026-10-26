---
type: definition
title: Equivalence relation
aliases: [equivalence relation, Äquivalenzrelation, Äquivalenzklasse, equivalence class, Quotientenmenge, quotient set]
tags: [relations, equivalence]
sources: [raw/relation_und_permutation_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Equivalence relation

## Definition

Let $\equiv\, \subseteq A \times A$ be a homogeneous [[relation|relation]] (*Relation*)
on $A$.

$\equiv$ is an **equivalence** (*Äquivalenz*) $:\Longleftrightarrow$

  (i) $\equiv$ is **reflexive** (*reflexiv*): $\forall x \in A\,[\,x \equiv x\,]$
  (ii) $\equiv$ is **transitive** (*transitiv*): $\forall x,y,z \in A\,[\,x \equiv y \wedge y \equiv z \Rightarrow x \equiv z\,]$
  (iii) $\equiv$ is **symmetric** (*symmetrisch*): $\forall x,y \in A\,[\,x \equiv y \Rightarrow y \equiv x\,]$

**Equivalence class** (*Äquivalenzklasse*) of $a \in A$:
$$\overline{a} = \{\, b \in A \mid a \equiv b \,\}$$

**Quotient set** (*Quotientenmenge*): the set of all equivalence classes
$$\overline{A} = A/\!\equiv$$

## Intuition

An equivalence relation **splits** the set into disjoint clumps. Within a clump
everything is related to everything, between two clumps nothing is related at all.

Example from the source: for $A = \{a,b,c,d,e,f,g,h,i\}$ with the classes
$$\overline{a} = \{a,b\} = \overline{b}, \qquad
\overline{c} = \{c,d,e\} = \overline{d} = \overline{e}, \qquad
\overline{g} = \{f,g,h,i\} = \overline{f} = \overline{h} = \overline{i}$$
the quotient set is
$$\overline{A} = A/\!\equiv \;=\; \{\overline{a}, \overline{c}, \overline{g}\}
= \bigl\{\{a,b\},\{c,d,e\},\{f,g,h,i\}\bigr\}.$$

Crucial: **one and the same class has several names.** $\overline{a}$ and $\overline{b}$
denote the same set. Every element of a class is an equally valid **representative**.

## Examples

1. **Same function value.** For $f : \mathbb{N}_0 \to \mathbb{N}_0$,
   $$x R y :\Longleftrightarrow f(x) = f(y)$$
   is always an equivalence. The classes are the preimages (fibers) of $f$. For
   $f(x) = 1$ if $x$ is even, $0$ otherwise, we get exactly two classes:
   $$\overline{0} = \{0,2,4,\dots\}, \qquad \overline{1} = \{1,3,5,\dots\}$$

2. **Divisibility of $a^2 - b^2$ by 3** on $\mathbb{Z}$.

Both worked out in detail in [[equivalence-relation-proofs]].

## Counterexamples

- $R = \{(1,2)\}$ is transitive and antisymmetric, but neither reflexive nor symmetric
  — not an equivalence.
- $S = \{(1,4),(2,1),(2,3),(3,2),(4,1)\}$ is symmetric, but neither transitive nor
  reflexive.

## Properties

- Equivalence classes are **either equal or disjoint**; they form a partition of $A$.
- The transition $A \rightsquigarrow A/\!\equiv$ is called **quotient formation**
  (*Quotientenbildung*). It is the construction principle behind $\mathbb{Z}_n$: there
  the classes are the residue classes (*Restklassen*) modulo $n$.

> [!inferred] not from the summaries
> The statement "equivalence classes form a partition" is only shown pictorially in the
> source (circles drawn around the clumps), not stated or proved. The connection to the
> construction of $\mathbb{Z}_n$ is also not made at this point.

## Related

- [[properties-of-homogeneous-relations]] — the three required properties
- [[relation]] — basic concept
- [[equivalence-relation-proofs]] — worked-out examples
- [[hasse-diagram]] — the counterpart: antisymmetry instead of symmetry
- [[residue-class-ring]] — the module's most important equivalence relation: $a \equiv b \pmod n$

## Sources

- `raw/relation_und_permutation_das.pdf`, p. 3, p. 4, p. 10, p. 12
