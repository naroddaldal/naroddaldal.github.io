---
layout: page
title: Paralog Interaction Browser
description: 
img: assets/img/publication_preview/paralogmap.png
importance: 1
category: projects
related_publications: true
---

## Overview

The **Paralog Interaction Browser** is a publicly accessible web platform developed as part of my PhD research to explore predicted synthetic lethal dependencies between paralogs across cancer cell lines. The platform supports target prioritization and design libra

- **Web platform:** [cancergenetics.github.io/paralogmap](https://cancergenetics.github.io/paralogmap/)

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