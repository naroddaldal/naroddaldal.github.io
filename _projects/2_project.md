---
layout: page
title: Short talk — CRISPR and Beyond, Wellcome Genome Campus, 2025
description: A predicted cancer dependency map for paralog pairs
img: assets/img/publication_preview/crispr_conference.JPG
importance: 2
category: presentations
related_publications: true
---

## Overview

Invited short talk at **CRISPR and Beyond: Perturbations at Scale to Understand Genomes** (Wellcome
Genome Campus, Hinxton, 2025) presenting the machine-learning framework behind the
[Paralog Interaction Browser](https://cancergenetics.github.io/paralogmap/).

- **Conference:** [CRISPR and Beyond — Perturbations at Scale to Understand Genomes](https://coursesandconferences.wellcomeconnectingscience.org/event/crispr-and-beyond-perturbations-at-scale-to-understand-genomes-20250520/)
- **Format:** invited short talk
- **Companion platform:** [cancergenetics.github.io/paralogmap](https://cancergenetics.github.io/paralogmap/)
- **Preprint:** [bioRxiv 10.64898/2026.01.19.700065](https://doi.org/10.64898/2026.01.19.700065) — currently under review at *Genome Medicine*

## Abstract

Combinatorial CRISPR screens have shown that many paralog pairs are synthetic lethal, but that
these effects are highly context-specific. In this talk I presented a machine-learning classifier
that predicts cell-line-specific synthetic lethality between paralog pairs, using features derived
from cell-line-specific expression, essentiality, and protein–protein interaction partners. The
model generalises across three prediction scenarios — same pairs in unseen cell lines, new pairs
in seen cell lines, and entirely uncharacterised pairs in unseen cell lines — and its agreement
with independent combinatorial CRISPR screens approaches the agreement observed across experiments.
I concluded by demonstrating the [Paralog Interaction Browser](https://cancergenetics.github.io/paralogmap/),
a web platform that exposes predictions for 1,005 cell lines as a resource for the community to
prioritise targets and design more focused combinatorial screens.
