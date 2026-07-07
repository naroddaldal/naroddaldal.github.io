---
layout: page
title: Cell-line-specific paralog SL classifier
description: PhD project code for predicting cell line specific synthetic lethality between paralog pairs
img: assets/img/publication_preview/slpredictor.jpeg
importance: 4
category: projects
related_publications: true
---

## Overview

`context_specific_SL_prediction` is the code accompanying my PhD work on **systematic
prioritisation of context-specific paralog pair vulnerabilities in cancer**. It implements a
random forest classifier that predicts, for each of ~33,000 paralog pairs across 1,005 DepMap
cancer cell lines, the probability that the pair is synthetic lethal in that specific cell
line. Predictions are exposed through the companion
[Paralog Interaction Browser](https://cancergenetics.github.io/paralogmap/).

- **Repository:** [github.com/naroddaldal/context_specific_SL_prediction](https://github.com/naroddaldal/context_specific_SL_prediction)
- **Preprint:** Kebabci, Ajmal, Adams & Ryan, *Systematic prioritisation of context-specific paralog pair vulnerabilities in cancer* — currently under review at *Genome Medicine*
- **Web platform:** [cancergenetics.github.io/paralogmap](https://cancergenetics.github.io/paralogmap/)
- **Predictions & data:** [Figshare 10.6084/m9.figshare.31058182](https://doi.org/10.6084/m9.figshare.31058182)

## What it does

- Integrates cell-line-specific features (paralog expression, essentiality, copy number,
  mutation status from DepMap) with cell-line-agnostic features (sequence identity,
  protein–protein interaction and Gene Ontology network features) into a single classifier.
- Provides two modelling strategies: a **contextualised model** that refines predictions from
  a prior context-agnostic classifier, and a **full model** that jointly trains on all
  features.
- Ships four cross-validation strategies for realistic evaluation — random splits, unseen
  cell lines, unseen paralog pairs, and unseen cell-line × pair combinations — plus external
  validation against Klingbeil, Parrish, Harle, and Gonatopoulos-Pournatzis screens.
- Generates 33.5 million cell-line-specific SL predictions, powering disease-stratified
  prioritisation across 26 cancer types in the web resource.

## Why it matters

Paralog synthetic lethality is highly context-specific, but experimentally mapping tens of
thousands of pairs across a thousand cell lines is impractical. The full model reaches
ROC AUC ≈ 0.87–0.93 across evaluation scenarios, with precision/recall on independent screens
matching the reproducibility observed *between* independent experimental studies —
suggesting predictions are as accurate as current screen data allows. Applied to HER2-amplified
breast cancer, the model recovers known synergies (EGFR–ERBB2, AKT1–AKT2, ERBB2–ERBB3) and
prioritises novel biomarker-associated vulnerabilities that replicate in HER2-amplified
gastro-oesophageal models.
