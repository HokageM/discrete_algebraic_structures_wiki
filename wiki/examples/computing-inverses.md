---
type: example
title: Computing inverses in Z_n
aliases: [erweiterter Euklid, extended Euclid, extended Euclidean algorithm, modular inverse, Lemma von Bezout, Inverses in Z_n berechnen]
tags: [number-theory, example]
sources: [raw/Zn_das.pdf]
created: 2026-09-30
updated: 2026-09-30
status: solid
---

# Computing inverses in $\mathbb{Z}_n$

Exam problems of the type "Compute the inverse of $a$ in the residue class ring
(Restklassenring) $\mathbb{Z}_n$." The tool is always the **extended Euclidean
algorithm (erweiterter euklidischer Algorithmus)**.

## The procedure

**Downward** — Euclidean algorithm, until the remainder is $0$:
$$n = q_1 a + r_1, \quad a = q_2 r_1 + r_2, \quad \dots, \quad r_{k-1} = q_{k+1} r_k + 0$$
The last nonzero remainder is $\gcd(a,n)$. It must be $1$, otherwise no inverse exists
(then $a$ is a [[units-and-zero-divisors|zero divisor (Nullteiler)]]).

**Upward** — back-substitution, until
$$1 = x\cdot n + y\cdot a$$
is reached. Modulo $n$ the first summand drops out:
$$1 \equiv y\cdot a \pmod n \quad\Longrightarrow\quad a^{-1} = y$$

If $y$ is negative, add $n$: the source explicitly notes
$-1 \equiv 50 \pmod{51}$.

## 1. $23^{-1}$ in $\mathbb{Z}_{51}$

**Downward:**
$$51 = 2\cdot23 + 5$$
$$23 = 4\cdot5 + 3$$
$$5 = 1\cdot3 + 2$$
$$3 = 1\cdot2 + 1$$
$$2 = 2\cdot1 + 0 \quad\Rightarrow\quad \gcd = 1 \;✓$$

**Upward:**
$$1 = 3 - 1\cdot2$$
$$= 3 - 1(5 - 1\cdot3) = -1\cdot5 + 2\cdot3$$
$$= -1\cdot5 + 2(23 - 4\cdot5) = 2\cdot23 - 9\cdot5$$
$$= 2\cdot23 - 9(51 - 2\cdot23) = -9\cdot51 + 20\cdot23$$

Modulo $51$:
$$1 \equiv 20\cdot23 \quad\Longrightarrow\quad \boxed{23^{-1} = 20 \text{ in } \mathbb{Z}_{51}}$$

**Check:** $23\cdot20 = 460 = 9\cdot51 + 1$ ✓

## 2. $33^{-1}$ in $\mathbb{Z}_{61}$

**Downward:**
$$61 = 1\cdot33 + 28, \quad 33 = 1\cdot28 + 5, \quad 28 = 5\cdot5 + 3,$$
$$5 = 1\cdot3 + 2, \quad 3 = 1\cdot2 + 1, \quad 2 = 2\cdot1 + 0$$

**Upward:**
$$1 = 3 - 1\cdot2 = 3 - (5-3) = -1\cdot5 + 2\cdot3$$
$$= -1\cdot5 + 2(28 - 5\cdot5) = 2\cdot28 - 11\cdot5$$
$$= 2\cdot28 - 11(33 - 1\cdot28) = -11\cdot33 + 13\cdot28$$
$$= -11\cdot33 + 13(61 - 1\cdot33) = 13\cdot61 - 24\cdot33$$

$$33^{-1} = -24 \equiv 61-24 = \boxed{37 \text{ in } \mathbb{Z}_{61}}$$

**Check:** $33\cdot37 = 1221 = 20\cdot61 + 1$ ✓

## 3. $36^{-1}$ in $\mathbb{Z}_{55}$

This problem appears twice in the source (p. 4 as a model example, p. 11 as an
exercise).

**Downward:**
$$55 = 1\cdot36 + 19, \quad 36 = 1\cdot19 + 17, \quad 19 = 1\cdot17 + 2,$$
$$17 = 8\cdot2 + 1, \quad 2 = 2\cdot1 + 0$$

**Upward:**
$$1 = 17 - 8\cdot2$$
$$= 17 - 8(19 - 1\cdot17) = -8\cdot19 + 9\cdot17$$
$$= -8\cdot19 + 9(36 - 1\cdot19) = 9\cdot36 - 17\cdot19$$
$$= 9\cdot36 - 17(55 - 1\cdot36) = -17\cdot55 + 26\cdot36$$

$$\boxed{36^{-1} = 26 \text{ in } \mathbb{Z}_{55}}$$

**Check:** $36\cdot26 = 936 = 17\cdot55 + 1$ ✓

## 4. The same algorithm for the gcd: $\gcd(45,12)$

$$45 = 3\cdot12 + 9, \quad 12 = 1\cdot9 + 3, \quad 9 = 3\cdot3 + 0
\quad\Rightarrow\quad \gcd(45,12) = 3$$

**Representation as a linear combination** (Bézout's lemma / Lemma von Bézout):
$$3 = 12 - 1\cdot9 = 12 - 1(45 - 3\cdot12) = -1\cdot45 + 4\cdot12$$

Here $\gcd = 3 \neq 1$ — so there is **no** inverse of $12$ in $\mathbb{Z}_{45}$.
This is the same algorithm, just with a different outcome. Cf. [[laws-of-gcd]], where
the remainder law (Restegesetz) $(a,b) = (b, a \bmod b)$ justifies the downward phase.

## Key points

- **Don't evaluate the rows!** In the upward phase, keep all products as they are and
  only combine them — otherwise you lose the structure.
- In each upward row, **exactly one** remainder is replaced by the equation one level
  up. That's the entire mechanism.
- **Always run a check**: $a \cdot a^{-1} \bmod n$ must give $1$. Costs ten seconds.
- Compute negative result $+\, n$.
- Clarify existence beforehand: $\gcd(a,n) = 1$ ⟺ $a$ is a
  [[units-and-zero-divisors|unit (Einheit)]].

## Related

- [[units-and-zero-divisors]] — when an inverse exists
- [[laws-of-gcd]] — the gcd laws behind the algorithm
- [[residue-class-ring]] — $\mathbb{Z}_n$
- [[modular-exponentiation]] — the other major computing technique in $\mathbb{Z}_n$
- [[euler-phi-function]] — how many invertible elements there are

## Sources

- `raw/Zn_das.pdf`, p. 2 (problem 5.3), p. 4, p. 5 (problem 3), p. 11 (exercise 11.1)
