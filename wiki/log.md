# Log

## [2026-09-30] setup | wiki initialised
- Created the schema `CLAUDE.md`, set up the directory structure `raw/` + `wiki/`.

## [2026-09-30] ingest | Rechengesetzte_das.pdf
- Source: 5-page scan with no text layer; pages rendered to PNG with PyMuPDF and read as images.
- Created: [[algebraic-laws]], [[laws-of-propositional-logic]], [[laws-of-sets]],
  [[laws-of-natural-numbers]], [[laws-of-integers]], [[laws-of-gcd]]
- Updated: [[index]]
- Deviation from the schema: the five tables of laws live under `theorems/` rather than
  `definitions/`, since they are laws and not definitions of concepts.
- Flagged (typos in the source, p. 4): `(a+b)*c = a*c + a*c` should read `a*c + b*c`;
  the condition `if a != 0` on `a*1 = a` is superfluous. Both documented in
  [[laws-of-integers]].
- Gaps: no proofs in the source; lcm, the additive inverse and the classification as
  ring/lattice are all missing. To be filled in when ingesting
  `Algebraische_strukturen_das.pdf` and `Induktion_das.pdf`.
- Schema extended with section 10 (handling scanned PDFs).

## [2026-09-30] ingest | Induktion_das.pdf
- Source: 4-page scan (2 exam problems with handwritten solutions, 2 tutorial pages).
  A different kind of source from the tables of laws: worked problems rather than reference.
- Created: [[mathematical-induction]], [[induction-sum-of-odd-squares]],
  [[induction-telescoping-sum]], [[induction-sum-of-squares]],
  [[induction-2n-geq-n-squared]], [[induction-factorial-geq-2n]]
- Updated: [[index]], [[laws-of-natural-numbers]], [[laws-of-integers]] (backlinks)
- Flagged: slip of the pen on p. 2, base case: `1/(2*1+3)` instead of `1/(2*1+1)`;
  documented in [[induction-telescoping-sum]].
- Observation: the telescoping sum appears twice (exam p. 2 and tutorial p. 3) - merged
  into a single page.
- Gaps: the source never states the induction principle itself; strong induction is missing.

## [2026-09-30] ingest | Algebraische_strukturen_das.pdf
- Source: 14-page scan; overview sheets (partly duplicated: p.1 = p.11, p.2 = p.7+p.9)
  plus exam and tutorial problems with handwritten solutions.
- Created: [[algebraic-structures]], [[properties-of-operations]],
  [[group-like-structures]], [[ring-like-structures]], [[substructures]],
  [[homomorphism]], [[checking-properties-of-operations]], [[submonoid-proofs]],
  [[subgroup-proofs]], [[homomorphism-proofs]], [[klein-four-group]]
- Updated: [[index]], [[algebraic-laws]], [[laws-of-integers]],
  [[laws-of-natural-numbers]] (open questions closed, backlinks)
- Synthesis: the open question from the algebraic-laws ingest is answered - the five
  tables of laws can now be classified as monoid / integral domain / field.
  Table in [[algebraic-structures]].
- Flagged (errors in the source): p.4 `4^(i*j)` instead of `4^(i+j)`; p.4 invertible
  elements without sign (`a = 2^k` instead of `a = +-2^k`); p.12 ambient structure
  `Q\{0}` although 0 lies in U; p.14 the justification `b not in Q` is wrong;
  p.13 the rotation group wrongly called `D_3` (it is C_3 = A_3).
- Gaps: kernel/image, normal subgroups, cosets, Lagrange's theorem and order are all missing.

## [2026-09-30] ingest | relation_und_permutation_das.pdf

**Source:** `raw/relation_und_permutation_das.pdf` (15 pages, pure image scan, rendered with pymupdf)

**Content:** Two exams (problems 1 and 2) plus tutorial sheets on relations (UE2, UE3),
formal theorems (UE1) and permutations (UE9).

**New pages (12):**
- concepts/relations-and-permutations.md (hub)
- definitions/relation.md
- definitions/properties-of-homogeneous-relations.md
- definitions/equivalence-relation.md
- definitions/hasse-diagram.md
- definitions/permutation.md
- definitions/signum.md
- examples/checking-relation-properties.md
- examples/equivalence-relation-proofs.md
- examples/hasse-diagrams-of-divisors.md
- examples/computing-with-permutations.md
- examples/checking-tautologies.md

**Updated pages (4):** theorems/laws-of-propositional-logic.md,
examples/subgroup-proofs.md, examples/klein-four-group.md,
definitions/group-like-structures.md -- new cross-references in each.

**Verification:** The permutation product in problem 1.5 (pi*tau and tau*pi, degree 9)
was recomputed element by element and is correct. This pins down the source's
convention: composition from right to left.

**Open points:** The two-line notations on p. 7 and p. 15 are not unambiguously legible
in the scan (the bottom rows appear non-bijective). Marked as transcription uncertainty,
not as an error in the source. Likewise the entry "20" in the list of 2-permutations
of 4 on p. 13 (probably "23").

## [2026-09-30] ingest | Zn_das.pdf

**Source:** `raw/Zn_das.pdf` (13 pages, pure image scan)

**Content:** Two exams (problem 5 in each, 16 points) with identical structure,
plus tutorials 10-12 on residue class rings.

**New pages (8):**
- concepts/residue-class-rings.md (hub)
- definitions/residue-class-ring.md
- definitions/units-and-zero-divisors.md
- theorems/fermats-little-theorem.md
- theorems/euler-phi-function.md
- examples/determining-units-and-zero-divisors.md
- examples/computing-inverses.md
- examples/modular-exponentiation.md

**Updated pages (3):** definitions/ring-like-structures.md,
theorems/laws-of-gcd.md, definitions/equivalence-relation.md.

**Verification:** All 13 computations in the source were recomputed independently during
the ingest. Every inverse checked via a*a^{-1} = 1, every phi value via the product
formula, every power additionally via the order of the base.

**Errors found in the source (4):**
- p. 6: sign error in the phi(176) manipulation (the result 80 is correct).
- p. 8: the zero-divisor list of Z_6 first given as "0,2,3", correct is "2,3,4" (corrected later in the source itself).
- p. 10: "mod 13" instead of "mod 17" in a Z_17 computation.
- p. 12: the first computation of 67^33 mod 13 gives 6, correct is 5 (the second computation on the same page is right).
This is the densest source for errors so far; noted accordingly on the hub page.

## [2026-09-30] ingest | polynomring_das.pdf

**Source:** `raw/polynomring_das.pdf` (10 pages, pure image scan)

**Content:** Two exams (problem 6, 18 points) plus tutorials 10-12 on polynomial rings,
quadratic field extensions, finite fields and irreducibility.

**New pages (7):**
- concepts/polynomial-rings.md (hub)
- definitions/polynomial-ring.md
- definitions/quadratic-field-extension.md
- theorems/irreducibility-and-fields.md
- examples/computing-in-polynomial-rings.md
- examples/finite-fields.md
- examples/field-or-not.md

**Updated pages (3):** definitions/ring-like-structures.md,
definitions/residue-class-ring.md, definitions/units-and-zero-divisors.md.

**Guiding idea of the chapter:** the analogy Z <-> K[x], Z_n <-> K[x]_g, prime <-> irreducible.
Worked out as a table on the hub page and linked to concepts/residue-class-rings.md.

**Verification:** All computations recomputed independently.

**Errors found in the source (2 substantive, 2 notational):**
- p. 5: in f*h over GF(16) a +1 is lost during reduction. The source gets x,
  correct is x+1.
- p. 10: g = x^3+x+2 over Z_3 is called irreducible because g(2)=12 is not reduced.
  In fact 12 = 0 mod 3, so x=2 is a root and g = (x+1)(x^2+2x+2) is reducible.
  Z_3[x]_g is NOT a field. Recomputed and confirmed by expansion.
- p. 7: for two inverses the conjugate is written on the left-hand side (results correct).
- p. 9: zero divisors of x^2-4 given as "(x+2),(x+2)" instead of (x-2),(x+2).

Both substantive errors arise from forgetting to reduce the coefficients.

## [2026-09-30] ingest | kombinatorik_das.pdf

- Source: raw/kombinatorik_das.pdf (11 pages, pure scan with no text layer)
- New pages: concepts/combinatorics, definitions/urn-model, definitions/box-model,
  definitions/partitions-and-stirling-numbers, definitions/multinomial-coefficient,
  examples/counting-exercises, examples/double-counting
- Updated: definitions/permutation (backlinks), concepts/relations-and-permutations
  (cross-connection), index.md
- Content: urn model (2x2) and box model (4x4, the twelvefold way), integer and set
  partitions (P, p, S, B), multinomial coefficient, two exam sets for problem 3,
  tutorials 5 and 6, double counting via incidence matrices.
- Verification: both model tables checked cell by cell (all 20 entries correct);
  all counting coefficients and divisibility arguments recomputed independently.
- Errors found in the source and documented:
  - p. 1: both kinds of partition written P(n,k) (the table on p. 2/6 correctly
    distinguishes P(n,k) unordered from p(n,k) ordered).
  - p. 3: words over {0,1,2} called "binary words" (the alphabet has 3 symbols).
  - p. 9: r_1 = (1 2 3 / 1 2 1) is not a permutation; correct is (1 2 3 / 3 2 1).
  - p. 10: C(10;5,2,2,1,1) is undefined, since 5+2+2+1+1 = 11, not 10. The correct
    computation as a sum over the five cases gives 83160 - the same value as for
    length 11, justified by a bijection (append the missing letter).
- With this, all 7 sources in raw/ are ingested.

## [2026-09-30] lint | first full health check

- Trigger: all 7 sources in raw/ are ingested.
- Checked: 60 pages for dead wikilinks, orphan pages and stubs.
- Result: 0 dead links, 0 orphan pages, 0 stubs (< 1200 bytes).
- Fixed: concepts/polynomial-rings had no inbound links other than index.md -
  added a cross-connection from concepts/residue-class-rings (analogy Z_n <-> K[x]_g).
- New: wiki/overview.md as the start page - module storyline, the central analogy
  Z <-> K[x], four recurring techniques, exam map (problems 1-6),
  error tally across all sources.
- index.md now points to overview at the top.
- Known gaps (deliberate, as the sources do not cover them): recurrence for the
  Stirling numbers S(n,k); no past-exam model solutions as a cross-check.

## [2026-09-30] refactor | wiki translated to English

- Trigger: user asked for the whole wiki to be in English, including filenames.
- Renamed 54 of 57 content pages to English kebab-case filenames via git mv
  (permutation, relation and signum already had English names). All 60 files had their
  wikilinks rewritten to the new targets; 0 dead links afterwards.
- Translated all 57 content pages plus index.md, overview.md, log.md and CLAUDE.md
  from German to English. Six parallel agents handled the page bodies, batched by
  directory; index, overview, log and schema were done directly.
- Translation contract: wikilink targets, LaTeX, notation and every mathematical claim
  left byte-identical. Only prose, headings, titles and tags were changed.
- Section headings now follow the English schema: Definition / Intuition / Examples /
  Counterexamples / Properties / Related / Sources for definitions; Statement /
  Hypotheses / Proof idea / Application / Related theorems / Sources for theorems;
  Problem / Solution / What it shows / Sources for examples; Core idea / Connections /
  Open questions / Sources for concepts.
- German terms retained: as an italic gloss in parentheses on first mention of each
  term, and in the aliases field, so the pages still map onto the German lecture.
- Frontmatter tags normalised to a single English vocabulary
  (basics->foundations, field->fields, rings->ring-theory, groups->group-theory).
- CLAUDE.md updated: naming convention is now English, page-format section names
  rewritten, new section 11 "Language" fixes the English-wiki / German-source contract
  and records that notation follows the module, not English convention.
- Verification: 60 pages, 0 dead wikilinks, 0 orphans; automated scan for untranslated
  German prose returned 0 hits; all 9 warning callouts and 22 inferred callouts intact;
  the substantive source corrections (GF(16) product, x^3+x+2 reducible over Z_3,
  ABRAKADABRA 83160) spot-checked and unchanged.
- raw/ filenames deliberately left in German; they are the immutable sources.
