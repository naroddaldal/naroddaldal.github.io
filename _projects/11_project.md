---
layout: page
title: Systematic enrichment of protein stability datasets
description: MSc thesis code for rebalancing protein-stability datasets to reduce bias in ΔΔG predictors (JCIM 2022)
img: assets/img/publication_preview/gror.jpeg
importance: 6
category: projects
related_publications: false
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

- Curates the PON-tstab data set down to 1,451 mutations across 89 proteins by resolving
  repetitions, residue-numbering mismatches, and missing PDB information.
- Introduces a ternary labelling (neutral, destabilising, stabilising) with neutral defined as
  ΔΔG ∈ [−0.5, 0.5] kcal/mol, so the dense neutral zone can be diagnosed as a bias rather than
  merged into destabilising mutations.
- Encodes mutations with either the 20-letter alphabet or a 4-letter reduced alphabet grouped by
  side-chain biochemistry (aliphatic / aromatic / polar / charged), and optionally sub-groups
  them by secondary structure (helix / sheet / loop, from DSSP) and three bins of relative
  solvent-accessible surface area.
- From every 2 kcal/mol window of each subgroup, selects three mutations (min, median, max
  ΔΔG), systematically diluting the neutral peak.
- Produces five enriched subsets (20L, 4L, 4L/SS, 4L/ASA, 4L/SS/ASA) with reduced kurtosis and
  skewness and more balanced amino-acid frequencies than the parent PON-tstab.

## Why it matters

Benchmarking 11 stability predictors (DeepDDG, mCSM, INPS-3D, I-Mutant2.0/3.0, SDM, MAESTRO,
PoPMuSiC, DUET, iStable, iDeepDDG) on the curated PON-tstab shows that every predictor makes
its smallest errors in the dense neutral zone, systematically under-estimates destabilising
mutations, and over-estimates stabilising ones — regressing toward ΔΔG ≈ 0. The paper argues
that peakedness (kurtosis) of the ΔΔG distribution is a data-set bias in its own right,
distinct from the well-known destabilising/stabilising asymmetry (skewness). Errors on the
enriched subsets were higher than on the parent set, confirming that the workflow concentrates
the difficult-to-predict mutations — the ones with extreme ΔΔG that actually matter for
disease variants.
