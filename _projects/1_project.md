---
layout: page
title: Paralog Interaction Browser
description: An interactive web platform developed as part of my PhD research to explore predicted synthetic lethal dependencies between paralogs across cancer cell lines. The platform supports target prioritization and design libraries for combinatorial CRISPR screens by making prediction scores accessible to experimental and computational researchers.
img: assets/img/publication_preview/paralogmap.png
importance: 1
category: projects
related_publications: true
---

## Overview

The **Paralog Interaction Browser** ([paralogmap](https://cancergenetics.github.io/paralogmap/)) is a
publicly accessible web platform I built to help experimental scientists translate machine-learning
predictions of synthetic lethality into concrete CRISPR screen designs. It exposes the output of a
classifier that predicts, for each of ~36,000 paralog pairs, whether the pair is likely to be
synthetic lethal in each of 1,005 cancer cell lines.

- **Live platform:** [cancergenetics.github.io/paralogmap](https://cancergenetics.github.io/paralogmap/)
- **Source code:** [github.com/cancergenetics/paralogmap](https://github.com/cancergenetics/paralogmap)
- **Underlying analysis:** [github.com/cancergenetics/context_specific_paralog_SL](https://github.com/cancergenetics/context_specific_paralog_SL)
- **Preprint:** [bioRxiv 10.64898/2026.01.19.700065](https://doi.org/10.64898/2026.01.19.700065) — currently under review at *Genome Medicine*

## Motivation

Combinatorial CRISPR screens have shown that many paralog pairs are synthetic lethal, but that these
effects are highly context-specific — a pair that is essential in one cell line may be dispensable
in another. To use paralogs as therapeutic targets, we need to know **which pairs are lethal in
which contexts**. The Paralog Interaction Browser exposes those cell-line-specific predictions in a
format that biologists can query directly.

## What it does

- **Search by gene, pair, or cell line** — look up predictions for any paralog pair in any of the
  1,005 profiled cell lines.
- **Rank candidate targets** — sort pairs by predicted synthetic lethality score to prioritise
  hits for combinatorial CRISPR screens.
- **Explore feature contributions** — see which of the 16 input features (expression, essentiality,
  PPI-partner behaviour, etc.) drive each prediction, via SHAP values.
- **Design targeted screens** — filter to specific cancer types or genetic backgrounds so
  experimental collaborators can build focused libraries without any coding.

## Technical details

- **Model:** supervised classifier (Random Forest) trained on published combinatorial CRISPR screens,
  with 16 engineered features per pair per cell line
- **Data:** DepMap essentiality, CCLE transcriptomics, somatic mutation profiles, STRING
  protein–protein interaction networks, Gene Ontology annotations
- **Validation:** independent held-out screens; agreement between our predictions and published
  experiments approaches the agreement observed across experiments themselves
- **Deployment:** static site (GitHub Pages) with pre-computed predictions served client-side for
  fast, dependency-free access
