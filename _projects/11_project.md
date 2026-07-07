---
layout: page
title: gRoR — balanced protein stability datasets
description: Systematic ΔΔG enrichment code from my MSc thesis (JCIM 2022)
img: assets/img/publication_preview/gror.jpeg
importance: 4
category: projects
related_publications: true
---

## Overview

`gRoR` is the code accompanying my MSc work on **flattening the ΔΔG curve** in protein-stability
datasets. Most public stability datasets (S2648, PON-tstab, Sʸᵐ) are dominated by neutral
mutations concentrated near ΔΔG ≈ 0, which biases every predictor trained on them. `gRoR`
implements a systematic under-sampling strategy that groups mutations by biochemical and/or
structural similarity and then evenly samples across the ΔΔG range, producing subsets with less
peaked distributions and more balanced amino-acid frequencies.

- **Repository:** [github.com/naroddaldal/gRoR](https://github.com/naroddaldal/gRoR)
- **Paper:** Kebabci, Timucin & Timucin, *J. Chem. Inf. Model.* **62**, 1345–1355 (2022) —
  [10.1021/acs.jcim.2c00054](https://doi.org/10.1021/acs.jcim.2c00054)
- **Datasets:** curated PON-tstab and five enriched subsets on [OSF](https://osf.io/h98pn/)

## What it does

- Encodes mutations with either the 20-letter alphabet or a 4-letter reduced alphabet grouped by
  side-chain biochemistry (aliphatic / aromatic / polar / charged).
- Optionally sub-groups mutations by secondary structure (helix / sheet / loop, from DSSP) and
  relative solvent-accessible surface area (three bins).
- From every 2 kcal/mol window of each subgroup, selects three mutations (min, median, max ΔΔG),
  systematically diluting the neutral peak.
- Produces five enriched subsets (20L, 4L, 4L/SS, 4L/ASA, 4L/SS/ASA) with reduced kurtosis and
  skewness relative to the parent PON-tstab.

## Why it matters

Benchmarking 11 stability predictors (DeepDDG, mCSM, INPS-3D, I-Mutant2.0/3.0, SDM, MAESTRO,
PoPMuSiC, DUET, iStable, iDeepDDG) on the curated PON-tstab showed that all of them predict best
in the dense neutral region and systematically under-estimate destabilising and over-estimate
stabilising mutations. Errors on the enriched subsets were higher than on the parent set,
confirming that `gRoR` concentrates the difficult-to-predict mutations — the ones that actually
matter for disease variants.
