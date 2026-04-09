# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a LaTeX-based research presentation and paper project on **influence functions** — covering theory, applications to graphs/GNNs, and second-order group influence for LLM data selection. The main author is Dongwoo Kim (ANU & POSTECH).

## Repository Structure

- `main.tex` — Beamer slide deck (16:9, Pittsburgh theme, beaver colors). The primary deliverable.
- `meeting_notes/group_influence.tex` — Draft paper on group influence (ICML 2025 format).
- `references.bib` — Shared BibTeX bibliography (uses `biblatex` with `bibtex` backend in slides).
- `figures/` — PDF/PNG figures used in the slides.
- `papers/` — Reference PDFs.
- `annotate-equations.sty` — Local style file for equation annotations in Beamer.

## Build Commands

The project uses `pdflatex` via `latexmk`:

```bash
# Build slides
latexmk -pdf main.tex

# Continuous build (watches for changes)
latexmk -pdf -pvc main.tex

# Clean auxiliary files
latexmk -c

# Build meeting notes paper
cd meeting_notes && pdflatex group_influence.tex
```

## LaTeX Conventions

- Slides use `\emph{}` (blue italic) and `\remph{}` (red italic) for emphasis.
- Bibliography: `biblatex` with `authoryear` style and `\citet`/`\citep` citation commands.
- Math: heavy use of `amsmath`, `bm` for bold math symbols, `tikz` for diagrams.
- The slide deck is organized into three parts: (1) Theory of Influence Functions, (2) Graph/GNN Influence, (3) Second-Order Group Influence for LLMs.
