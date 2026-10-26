---
type: example
title: Counting exercises (exam and tutorial problems)
aliases: [Abzählaufgaben, Klausuraufgabe 3, Zählkoeffizienten, counting coefficients]
tags: [combinatorics, exam]
sources: [raw/kombinatorik_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Counting exercises

The combinatorics problem of the exam ("problem 3") is a list of short questions where
**only the counting coefficient (Zählkoeffizient)** must be given — not evaluated. Each
question is an entry from [[urn-model]] or [[box-model]].

## Exam set A (alphabet $\{0,1,2\}$)

| # | Question | Answer | Justification |
|---|---|---|---|
| 1 | words of length 10 over $\{0,1,2\}$ | $3^{10}$ | variation, $n^k$ with $n=3$, $k=10$ |
| 2 | words of length 10 with 4 zeros, 3 ones, 3 twos | $C(10;4,3,3)$ | [[multinomial-coefficient]], $4{+}3{+}3=10$ ✓ |
| 3 | 3-element subsets of $\{1,\dots,10\}$ | $\binom{10}{3}$ | combination |
| 4 | 4-element subsets of $\{1,\dots,10\}$ containing $1$ | $\binom{10-1}{4-1}=\binom93$ | the $1$ is fixed, $3$ remain to choose from $9$ |
| 5 | maps $\{1,\dots,10\}\to\{1,\dots,6\}$ | $k^n = 6^{10}$ | $n=10$ balls, $k=6$ boxes, arbitrary |
| 6 | injective maps $\{1,\dots,6\}\to\{1,\dots,10\}$ | $(k)_n = (10)_6$ | $n=6$, $k=10$, injective |
| 7 | surjective maps $\{1,\dots,10\}\twoheadrightarrow\{1,\dots,6\}$ | $k!\,S(n,k) = 6!\,S(10,6)$ | [[partitions-and-stirling-numbers]] |
| 8 | bijective maps on $\{1,\dots,10\}$ | $n! = 10!$ | $n=k$ |
| 9 | words from the letters of MOJOJOJO | $C(8;1,4,3)$ | $\mathrm M^1\mathrm O^4\mathrm J^3$ |
| 10 | $12$ as a sum of 3 positive integers | $P(12,3)$ | unordered integer partition (Zahlpartition) |

**On 4:** The rule "one element is forced" always means: strike the element, shrink the
underlying set (Grundmenge) and the selection size by 1 each.

> [!inferred] not from the summaries
> The numeric value for 10 is $P(12,3) = 12$: namely $10{+}1{+}1$, $9{+}2{+}1$, $8{+}3{+}1$,
> $8{+}2{+}2$, $7{+}4{+}1$, $7{+}3{+}2$, $6{+}5{+}1$, $6{+}4{+}2$, $6{+}3{+}3$,
> $5{+}5{+}2$, $5{+}4{+}3$, $4{+}4{+}4$. The exam asks for the coefficient, not the value.

> [!warning] Terminology error in the source (p. 3)
> Question 2 calls the words over $\{0,1,2\}$ "binary words" (Binärwörter). The alphabet
> has three characters; "binary" is wrong here. The calculation is unaffected.

## Exam set B (alphabet $\{0,1\}$)

| # | Question | Answer |
|---|---|---|
| 1 | binary words of length 10 | $2^{10}$ |
| 2 | binary words of length 10 with 7 zeros and 3 ones | $\binom{10}{7}=\binom{10}{3}=C(10;7,3)$ |
| 3 | maps $\{1,\dots,10\}\to\{1,\dots,7\}$ | $7^{10}$ |
| 4 | injective maps $\{1,\dots,7\}\to\{1,\dots,10\}$ | $(10)_7$ |
| 5 | surjective maps $\{1,\dots,10\}\twoheadrightarrow\{1,\dots,7\}$ | $7!\,S(10,7)$ |
| 6 | bijective maps on $\{1,\dots,10\}$ | $10!$ |
| 7 | words from SOMMERSEMESTER | $C(14;3,1,3,4,2,1)$ |

**On 2:** Here three viewpoints coincide — a binary word with 3 ones, a 3-element subset
of the positions, a multinomial coefficient with two groups. That is the translation
trick described in [[urn-model]].

**On 7:** SOMMERSEMESTER has 14 letters with profile
$\mathrm S^3\mathrm O^1\mathrm M^3\mathrm E^4\mathrm R^2\mathrm T^1$; check:
$3{+}1{+}3{+}4{+}2{+}1 = 14$ ✓. The source numbers the letters for this:
$1\,2\,3\,3\,4\,5\,1\,4\,3\,4\,1\,6\,4\,5$.

Part 8 (set system) and the 3-partitions of 4 are covered in
[[double-counting]] resp. [[partitions-and-stirling-numbers]].

## Exercise 5 ②: the same number, four phrasings

| Question | Answer |
|---|---|
| 4-element subsets of $\{1,\dots,10\}$ | $\binom{10}{4}$ |
| binary words of length 10 with 4 ones | $\binom{10}{4}$ |
| 4-element subsets of $\{1,\dots,10\}$ containing $1$ | $\binom93=\binom{10-1}{4-1}$ |
| binary words of length 10 with 4 ones, starting with $1$ | $\binom93$ |

The first position is fixed: $1\,\underbrace{\_\;\_\;\_\;\_\;\_\;\_\;\_\;\_\;\_}_{9 \text{ positions, } 3 \text{ ones}}$

The point of the exercise is to practice the translation *subset $\leftrightarrow$
binary word* — both pairs of rows are the same question.

## Exercise 6 ②: all surjective $\{1,2,3\}\twoheadrightarrow\{a,b\}$

$n = 3$, $k = 2$, balls and boxes distinguishable, surjective ($n \ge k$ ✓):

$$k!\cdot S(n,k) = 2!\cdot S(3,2) = 2\cdot 3 = 6$$

$$\begin{pmatrix}1&2&3\\a&a&b\end{pmatrix}\;
\begin{pmatrix}1&2&3\\a&b&a\end{pmatrix}\;
\begin{pmatrix}1&2&3\\b&a&a\end{pmatrix}\;
\begin{pmatrix}1&2&3\\b&b&a\end{pmatrix}\;
\begin{pmatrix}1&2&3\\b&a&b\end{pmatrix}\;
\begin{pmatrix}1&2&3\\a&b&b\end{pmatrix}$$

All six are listed — three each with two $a$'s and two $b$'s. The two constant maps
$aaa$ and $bbb$ are rightly missing: they are not surjective.

## Exercise 6 ③: symmetries of the equilateral triangle

All maps of the triangle onto itself are the $3$-permutations of $3$, i.e.
$(3)_3 = 3! = 6$ pieces:

| | Permutation | Kind |
|---|---|---|
| $\mathrm{id}$ | $\begin{pmatrix}1&2&3\\1&2&3\end{pmatrix}$ | identity |
| $\delta_1$ | $\begin{pmatrix}1&2&3\\2&3&1\end{pmatrix}$ | rotation $120°$ |
| $\delta_2$ | $\begin{pmatrix}1&2&3\\3&1&2\end{pmatrix}$ | rotation $240°$ |
| $r_1$ | $\begin{pmatrix}1&2&3\\3&2&1\end{pmatrix}$ | reflection |
| $r_2$ | $\begin{pmatrix}1&2&3\\1&3&2\end{pmatrix}$ | reflection |
| $r_3$ | $\begin{pmatrix}1&2&3\\2&1&3\end{pmatrix}$ | reflection |

> [!warning] Error in the source (p. 9)
> For $r_1$ it states $\begin{pmatrix}1&2&3\\1&2&1\end{pmatrix}$. That is not a
> permutation: $3$ is never hit, $1$ twice. The only missing reflection is
> $\begin{pmatrix}1&2&3\\3&2&1\end{pmatrix}$ (fixed point $2$) — that is the correct one.

These six maps form the dihedral group $D_3 \cong S_3$; the three rotations alone form
the cyclic subgroup $C_3$ — see [[computing-with-permutations]] and
[[subgroup-proofs]].

## Exercise 6 ③ (ii): maps as words

A word $x_1x_2\dots x_k$ over the alphabet $\underline n$ is the same as a map
$f: \underline k \to \underline n$ with $x_i = f(i)$.

- **all** $f:\underline 2\to\underline 4$: $n^k = 4^2 = 16$
- **injective** $f:\underline 3\to\underline 4$: $(n)_k = (4)_3 = 4\cdot3\cdot2 = 24$

The source works this out with a decision tree: for $f:\underline 2\to\underline 4$
each of the 2 positions has 4 options; under injectivity, the choices shrink by 1 at each
step.

## Exercise 6 ④: license plates

$1$ to $3$ letters (from $26$) followed by $4$ digits (from $10$). The three cases are
mutually exclusive, so the addition rule applies:

$$26\cdot 10^4 \;+\; 26^2\cdot 10^4 \;+\; 26^3\cdot 10^4$$

Each summand is a product of two variations (letters times digits).

## Related

- [[urn-model]], [[box-model]] — the formula tables
- [[multinomial-coefficient]], [[partitions-and-stirling-numbers]]
- [[double-counting]] — the second problem type on the exam
- [[permutation]], [[computing-with-permutations]]
- [[combinatorics]] — chapter overview

## Sources

- `raw/kombinatorik_das.pdf`, p. 3, p. 4, p. 7, p. 9, p. 10, p. 11
