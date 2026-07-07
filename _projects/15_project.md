---
layout: page
title: Druggable synthetic lethal paralogs
description: PhD project code for systematically identifying approved small-molecule drugs associated with synthetic lethal paralogs
img: assets/img/publication_preview/druggable_paralogs.jpeg
importance: 5
category: projects
related_publications: true
---

## Overview

`druggable_paralogs` is the code accompanying my PhD work on **systematic identification of
small-molecule drugs associated with synthetic lethal paralog targets**. It integrates
approved-drug and target data from Open Targets, bioactivity measurements from ChEMBL, and
paralog synthetic lethality predictions to pinpoint paralog pairs that are both druggable and
therapeutically relevant.

- **Repository:** [github.com/naroddaldal/druggable_paralogs](https://github.com/naroddaldal/druggable_paralogs)

## What it does

- Preprocesses paralog pair data from De Kegel et al. (2021), integrating sequence and
  structural similarity scores and mapping identifiers across HGNC, Ensembl, and UniProt.
- Characterises the landscape of approved small-molecule drugs that target paralog pairs, and
  tests for paralog enrichment within each protein family using Fisher's exact test.
- Retrieves pChEMBL and pKi bioactivity measurements from ChEMBL 36, classifies approved drugs
  by their paralog-targeting pattern (single-member vs. co-targeting), and compares potency
  across paralog pairs.
- Integrates druggable pairs with synthetic lethal predictions and combinatorial CRISPR screen
  data to prioritise therapeutically relevant paralog pairs.

## Why it matters

Paralog synthetic lethality is a promising route to expand the druggable cancer genome, but
translating predicted vulnerabilities into therapies depends on whether tractable small-molecule
chemistry already exists. This project bridges that gap by cross-referencing predicted SL
paralog pairs with the approved-drug and bioactivity landscape, surfacing pairs where a
therapeutic starting point is already in hand.
