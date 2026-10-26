# DAS Wiki — Schema

An LLM-maintained knowledge base for **Diskrete Algebraische Strukturen (DAS)** at TUHH,
built from the user's own module summaries.

**Role split:** The user curates sources and asks questions. The LLM writes and maintains
*every* file under `wiki/`. The user never edits `wiki/` by hand; the LLM never edits `raw/`.

---

## 1. Directory layout

```
raw/                  Immutable sources: the user's module summaries (PDF scans). READ-ONLY.
.render/              Gitignored cache of PDF pages rendered to PNG. Derived, disposable.
wiki/
  index.md            Catalog of every wiki page, by category. Updated on every ingest.
  log.md              Append-only chronological record of ingests, queries, lint passes.
  overview.md         The "map of the module": big picture, how topics connect.
  definitions/        One page per definition/structure (group, ring, field, ...).
  theorems/           One page per theorem/lemma/corollary (Lagrange’s theorem, ...).
  examples/           Worked examples and counterexamples that span several definitions.
  concepts/           Cross-cutting themes (homomorphisms, quotients, order, ...).
  topics/             Per-chapter / per-lecture-topic syntheses.
  queries/            Filed answers to the user's questions (comparisons, analyses, cheat sheets).
CLAUDE.md             This file.
```

Create directories lazily — only when the first page of that kind is written.

## 2. Naming & linking conventions

- Filenames: lowercase, hyphenated, **English** term as canonical name:
  `definitions/normal-subgroup.md`, `theorems/lagranges-theorem.md`.
- Links: Obsidian wikilinks, `[[normal-subgroup]]` or `[[normal-subgroup|normal subgroup]]`.
  Every technical term that has a page **must** be linked on first mention in a page body.
- Language: the wiki is written entirely in **English** — page bodies, headings, titles and
  frontmatter. The module itself is taught in German, so on **first mention** of a technical
  term give the German original in parentheses and italics, e.g. "residue class ring
  (*Restklassenring*)"; afterwards use the English term only. Keep the German term in the
  `aliases` field so search works in both languages.
- Math: LaTeX in `$...$` / `$$...$$`. Use the module's notation exactly as it appears in the
  source summaries; do not silently substitute alternative notation. Note the module writes
  `$(a,b)$` for `gcd(a,b)`.

## 3. Page formats

Every page starts with YAML frontmatter:

```yaml
---
type: definition | theorem | example | concept | topic | query | overview
title: Normal subgroup
aliases: [normal subgroup, Normalteiler]
tags: [group-theory]
sources: [raw/summary-03-gruppen.pdf]
created: 2026-09-30
updated: 2026-09-30
status: stub | solid | needs-review
---
```

`tags` are lowercase and hyphenated: `group-theory`, `ring-theory`, `relations`, `logic`,
`set-theory`, `number-theory`, `induction`, `polynomials`, `combinatorics`, `exam`, `chapter`.

**definitions/** — sections in this order:
`## Definition` (formal statement, verbatim-faithful to the source) ·
`## Intuition` (plain-language) · `## Examples` · `## Counterexamples` ·
`## Properties` · `## Related` (wikilinks) · `## Sources`

**theorems/** —
`## Statement` · `## Hypotheses` · `## Proof idea` (sketch; full proof only if the source
has one) · `## Application / typical exam problem` · `## Related theorems` · `## Sources`

**examples/** — `## Problem` · `## Solution` (steps) · `## What it shows`
(which definitions/theorems it illustrates, as wikilinks) · `## Sources`

**concepts/ & topics/** — `## Core idea` · `## Connections` (wikilinked map of the
definitions/theorems involved) · `## Open questions` · `## Sources`

Optional sections used where needed: `## Cross-connections` (links to other chapters),
`## Contradictions`, `## Note on the source`.

Rules:
- A page may be a **collection of laws** rather than a single theorem (e.g. the tables of
  algebraic laws, *Rechengesetze*). These go in `theorems/` with the theorem format, not in
  `definitions/`.
- Never invent mathematical content not present in a source. If something is inferred or
  filled in from general knowledge, mark it inline: `> [!inferred] not from the summaries`.
- Where a source is wrong, do **not** silently fix it. Put the corrected version in the body
  and document the discrepancy in a `> [!warning] Error in the source (p. N)` callout with
  the reasoning, and flag it in `log.md`.
- If a new source contradicts an existing page, do **not** overwrite. Add a
  `## Contradictions` section stating both claims with their sources, and flag it in `log.md`.
- Keep pages short and atomic. Split rather than let a page sprawl.

## 4. Operation: Ingest

Trigger: user drops a summary into `raw/` and says "ingest <file>".

1. Read the source fully.
2. Report back to the user: a short list of the definitions, theorems, and examples found,
   and which are **new** vs. already covered. Wait for the user's go-ahead or corrections.
3. Write/update pages:
   - one page per new definition and per new theorem;
   - extend existing pages with new examples, properties, and cross-links;
   - write/update the `topics/` page for the chapter;
   - add backlinks on every related page touched (links must be bidirectional).
4. Update `wiki/index.md`.
5. Append to `wiki/log.md`.
6. Summarise to the user: pages created, pages updated, contradictions or gaps found.

Default is **one source at a time, with the user in the loop** at step 2.

## 5. Operation: Query

1. Read `wiki/index.md` first, then drill into the relevant pages. Use grep over `wiki/`
   for terms not in the index.
2. Answer with wikilink citations to the pages used, plus the `raw/` source when the claim
   is a direct mathematical statement.
3. If the wiki cannot answer it, say so explicitly — do not fill the gap from general
   knowledge without labelling it as such.
4. Offer to file substantial answers into `wiki/queries/` as a new page, then update
   `index.md` and `log.md`.

## 6. Operation: Lint

On request ("lint the wiki"), check and report (do not auto-fix without asking):
- contradictions between pages;
- terms used but lacking a page;
- orphan pages (no inbound wikilinks);
- missing backlinks / broken wikilinks;
- `status: stub` pages that a later source could now fill;
- definitions with no example, theorems with no proof idea;
- topics in the module the sources have not covered yet.

End with a short list of suggested next questions or missing summaries.

## 7. index.md format

```markdown
# Index

Catalog of every page in the DAS wiki. Start here: [[overview]]. Chronology: [[log]].

## Concepts
- [[algebraic-laws]] — one-line summary. (1 source)

## Theorems
...
## Definitions
- [[group]] — set with an associative operation, an identity and inverses. (2 sources)
## Examples
## Topics
## Queries
## Sources (raw/)
- `raw/summary-03-gruppen.pdf` — chapter 3, ingested 2026-09-30
```

## 8. log.md format

Append-only. Every entry starts with the exact prefix `## [YYYY-MM-DD] <op> | <subject>`
so `grep "^## \[" wiki/log.md | tail -5` works. Entries are written in English and in plain
ASCII (the file is appended to from PowerShell, where non-ASCII is unreliable).

```markdown
## [2026-09-30] ingest | summary-03-gruppen.pdf
- Created: [[group]], [[subgroup]], [[lagranges-theorem]]
- Updated: [[index]], [[topics/group-theory]]
- Flagged: the term "order" is used inconsistently in the source
```

Ops: `ingest`, `query`, `lint`, `refactor`.

## 9. Git

Commit after each completed operation. Message: `ingest: summary-03-gruppen` /
`query: normal subgroup vs. subgroup` / `lint: 2026-09-30`. Never commit anything
outside `raw/`, `wiki/`, and this file.

## 10. Reading the sources (scanned PDFs)

The sources are **scanned PDFs with no text layer** — text extraction returns nothing.
Each page is a single embedded image. Before ingesting, render the pages and read them
as images:

```powershell
py -3.13 -c "import pymupdf,sys; d=pymupdf.open(sys.argv[1]); [p.get_pixmap(dpi=140).save(sys.argv[2]+'\\p%02d.png'%i) for i,p in enumerate(d)]" raw\<file>.pdf .render\<file>
```

Then view each PNG with the image viewer. Requires `pymupdf` (`py -3.13 -m pip install pymupdf`).

Rules for scanned sources:
- Always check first whether a text layer exists (`page.get_text()`); only render if empty.
- Transcribe formulas into LaTeX **verbatim**, including the source's own notation quirks
  (e.g. `(a,b)` for `ggT(a,b)`).
- Cite page numbers in English: `` `raw/<file>.pdf`, p. 3 `` (the sources write *S.* for
  *Seite*; the wiki writes *p.*).
- The sources are handwritten and **contain errors**. Independently verify every
  computation before writing it into the wiki. Where the source is wrong, write the
  corrected version in the main body and document the discrepancy plus the reasoning in a
  `> [!warning] Error in the source (p. N)` callout (or a `## Contradictions` section for a
  genuine conflict between sources), set `status: needs-review` if unresolved, and flag it
  in `log.md`.
- `.render/` is a disposable cache, never committed, never cited.

## 11. Language

The wiki is in **English**, the sources are in **German**. Concretely:

- Everything the LLM writes — page bodies, titles, headings, filenames, log entries,
  index entries — is English.
- `raw/` filenames stay as they are (`Rechengesetzte_das.pdf`, `Zn_das.pdf`, ...) and are
  never renamed.
- Quotations from a source may stay in German; mark them as quotes.
- On first mention of a technical term on a page, give the German original in italics in
  parentheses — "box model (*Fächermodell*)" — so the page maps onto the German lecture.
  Also put the German term in `aliases`.
- Mathematical notation follows the module, not the English convention: `$(a,b)$` means
  `gcd(a,b)`, `$(n)_k$` is the falling factorial, `$C(k; h_1,\dots,h_n)$` is the
  multinomial coefficient. Do not "translate" notation.

