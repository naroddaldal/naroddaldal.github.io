---
layout: page
title: Paralog Interaction Browser
description: 
img: assets/img/publication_preview/paralogmap.png
importance: 1
category: projects
related_publications: false
---

## Overview

The **Paralog Interaction Browser** is a publicly accessible web platform developed as part of my PhD research to explore predicted synthetic lethal interactions between paralog pairs across cancer cell lines. The platform supports hypothesis generation, guide targeted combinatorial screening, and facilitate the identification of clinically actionable paralog targets.

- **Web platform:** [cancergenetics.github.io/paralogmap](https://cancergenetics.github.io/paralogmap/)
- **Repository:** [https://github.com/cancergenetics/paralogmap](https://github.com/cancergenetics/paralogmap)

## Motivation

Combinatorial CRISPR screens have shown that synthetic lethal interactions are enriched in paralog pairs, but they
are cell line specific — a pair that is synthetic lethal in one cell line may be not be synthetic lethal
in another. To identify paralogs as therapeutic targets, we need to know **which pairs are lethal in
which contexts**. The Paralog Interaction Browser exposes those cell-line-specific predictions in a
format that biologists, experimental scientists without coding experience can query directly.

## What it does

- **Search by gene, pair, or cell line** — look up predictions for any paralog pair in any of the
  +1,000 studied cell lines.
- **Rank candidate targets** — sort pairs by prediction score to prioritise
  hits for combinatorial CRISPR screens.
- **Design targeted screens** — filter to specific cancer types or genetic backgrounds so
  wet-lab scientists can build more focused combinatorial CRISPR screening libraries.