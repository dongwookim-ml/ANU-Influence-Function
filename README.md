# Understanding Influence Functions

Slide deck and supporting materials for a research talk by **Dongwoo Kim** (Visiting Fellow, ANU School of Computing; Associate Professor, POSTECH).

**Title:** *Understanding Influence Functions: From Edge Edits in Graphs to Group Influence in LLMs*

## Scope

The deck is organized into three parts:

1. **Theory of Influence Functions** — the classical parameter-space influence of a training point on a test prediction, derivations, and practical challenges.
2. **Graph / GNN Influence** — extending influence functions to edge edits, where message passing couples every node's gradient and breaks the standard i.i.d. derivation.
3. **Second-Order Group Influence for LLMs** — using group-level influence (including pairwise interaction terms) to guide data selection for large language models.

## Repository layout

- [main.tex](main.tex) — Beamer slide deck (16:9, Pittsburgh theme, beaver colors). Primary deliverable.
- [main.pdf](main.pdf) — Built slides.
- [references.bib](references.bib) — Shared BibTeX bibliography.
- [annotate-equations.sty](annotate-equations.sty) — Local style file for colored equation annotations used throughout the slides.
- [figures/](figures/) — PDF/PNG figures.
- [references/](references/) — Reference PDFs.

## Building

Requires a TeX distribution with `latexmk` and `pdflatex`, plus `biber`/`bibtex`.

```bash
# One-shot build
latexmk -pdf main.tex

# Continuous build (rebuilds on save)
latexmk -pdf -pvc main.tex

# Clean auxiliary files
latexmk -c
```

The bibliography uses `biblatex` with the `bibtex` backend and `authoryear` style; `\citet` and `\citep` are available via `natbib=true`.

## Conventions

- `\emph{...}` renders as blue italic; `\remph{...}` renders as red italic.
- Math uses `amsmath`, `bm` for bold symbols, and `tikz` for diagrams.
- Equation call-outs use `annotate-equations` with colored boxes (`\eqnmarkbox`) and labeled annotations (`\annotate`).
