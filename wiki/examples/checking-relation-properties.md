---
type: example
title: Checking relations for properties
aliases: [checking relation properties, Relationen auf Eigenschaften prüfen]
tags: [relations, example]
sources: [raw/relation_und_permutation_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Checking relations for properties

Worked problems on [[properties-of-homogeneous-relations]] and the
[[relation|relation product (Relationsprodukt)]]. The checking scheme is always: draw the
digraph, then read off the four properties from the picture and **justify each with a
concrete counterexample**.

## 1. $R = \{(a,a),(a,b),(a,c),(b,b),(b,c)\}$ on $A = \{a,b,c\}$

Digraph: loops at $a$ and $b$; arrows $a \to b$, $a \to c$, $b \to c$.

| | | Justification |
|---|---|---|
| reflexive | ✗ | $\neg\, cRc$ — the loop at $c$ is missing |
| transitive | ✓ | only path of length 2: $aRb \wedge bRc \Rightarrow aRc$ ✓ |
| symmetric | ✗ | $aRc$, but $\neg\, cRa$ |
| antisymmetric | ✓ | no double arrow between distinct nodes |

With $S = \{(c,b),(b,a),(b,c)\}$:
$$R \circ S = \{(a,a),(a,b),(a,c),(b,a),(b,b),(b,c)\}$$

## 2. $R = \{(a,a),(a,b),(a,c),(b,b),(b,c),(c,a),(c,b),(c,c)\}$ on $A = \{a,b,c\}$

| | | Justification from the source |
|---|---|---|
| reflexive | ✓ | all loops present: $aRa, bRb, cRc$ |
| transitive | ✗ | $bRc \wedge cRa$, but $\neg\, bRa$ |
| symmetric | ✗ | $aRb$, but $\neg\, bRa$ |
| antisymmetric | ✗ | $aRc \wedge cRa$ with $a \neq c$ |

For $S = \{(c,b),(b,b),(b,c)\}$:

| | | Justification |
|---|---|---|
| reflexive | ✗ | $\neg\, cRc$ |
| transitive | ✓ | $bRc \wedge cRb \Rightarrow bRb$ ✓ |
| symmetric | ✓ | $cRb$ and $bRc$ |
| antisymmetric | ✗ | $b \leftrightarrow c$ with $b \neq c$ |

$$R \circ S = \{(a,b),(a,c),(b,b),(b,c),(c,b),(c,c)\}$$

## 3. $R = \{(1,2)\}$ on $\{1,2\}$

| | | Justification |
|---|---|---|
| reflexive | ✗ | $\neg\, 1R1$ |
| transitive | ✓ | **vacuously true** — there is no path of length 2 |
| symmetric | ✗ | $1R2 \wedge \neg\, 2R1$ |
| antisymmetric | ✓ | only one simple arrow |

Notable: in the source, transitivity is first marked "No", then crossed out and
corrected to "Yes". The reason is the **empty premise**: the implication
$x\rho y \wedge y \rho z \Rightarrow x \rho z$ is true whenever the premise is never
satisfied.

## 4. $R = \{(1,2),(1,3),(2,4),(1,4)\}$ on $\{1,2,3,4\}$

| | | Justification |
|---|---|---|
| reflexive | ✗ | $\neg\, 1R1$ |
| transitive | ✓ | only path of length 2: $1R2 \wedge 2R4 \Rightarrow 1R4$ ✓ |
| symmetric | ✗ | $1R2 \wedge \neg\, 2R1$ |
| antisymmetric | ✓ | only simple arrows |

## 5. $S = \{(1,4),(2,1),(2,3),(3,2),(4,1)\}$ on $\{1,2,3,4\}$

| | | Justification |
|---|---|---|
| reflexive | ✗ | $\neg\, 1R1$ |
| transitive | ✗ | $1R4 \wedge 4R1$, but $\neg\, 1R1$ |
| symmetric | ✓ | all arrows are double arrows: $1 \leftrightarrow 4$, $2 \leftrightarrow 3$ |
| antisymmetric | ✗ | $1R4 \wedge 4R1$ with $1 \neq 4$ |

Here exactly reflexivity is missing to reach an [[equivalence-relation|equivalence]] —
and with it transitivity fails too. That is the typical case.

## 6. Inverse relation

For $R = \{(a,b),(b,b),(a,c),(b,c),(c,a)\}$:
$$R^{-1} = \{(b,a),(b,b),(c,a),(c,b),(a,c)\}$$
— all pairs reversed.

## What it shows

- **Every answer needs a justification**: for "yes" an argument covering all cases, for
  "no" a concrete counterexample. The source demonstrates this consistently.
- **Transitivity is the hardest point.** One must systematically go through all paths of
  length 2. If there are none, the property is automatically satisfied (case 3).
- Symmetry and antisymmetry are not opposites: example 5 is symmetric and not
  antisymmetric, example 4 the reverse, example 2 neither.

## Sources

- `raw/relation_und_permutation_das.pdf`, p. 2/4 (problem 2.2), p. 5/6 (problem 2.2),
  p. 9 (exercise 2.3), p. 10 (exercise 3.1), p. 11 (exercise 3.1, exercise 3.2)
