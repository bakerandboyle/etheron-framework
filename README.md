# The Octonionic Origin of the Standard Model Parameters

**Reproducibility script for 41 zero-parameter predictions from G₂ geometry**

[![](https://zenodo.org/badge/DOI/10.5281/zenodo.1928853.svg)](https://doi.org/10.5281/zenodo.1928853) 
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Overview

This repository contains the reproducibility script for the paper:

> S. Baker, "The Octonionic Origin of the Standard Model Parameters," Zenodo (2026).

The script takes **five integers** and **one dimensional anchor** as input and derives **41 predictions** for Standard Model parameters — masses, mixing angles, coupling constants, and the gravitational constant — with **zero fitted parameters**.

```
INPUTS:  {3, 4, 7, 2, 503}  +  m_e = 0.511 MeV
OUTPUT:  41 predictions across 22 orders of magnitude
FIT:     χ²/dof = 0.66  (p = 0.88)  for 22 independent comparisons
```

## Quick Start

```bash
python predictions.py
```

**Requirements:** Python 3.8+, NumPy, SciPy. No other dependencies.

```bash
pip install numpy scipy
```

## The Five Integers

| Symbol | Value | Geometric meaning |
|--------|-------|-------------------|
| D_pos  | 3     | Spatial dimensions |
| D_st   | 4     | Spacetime dimensions |
| D_phase | 7    | Phase space dimensions of the G₂ manifold |
| n_top  | 2     | Topological winding number (spin-½) |
| b₃     | 503   | Third Betti number of the G₂ manifold |

Everything else — the fine structure constant, the Casimir ratio σ = 2/3, the Koide angle δ = 2/9, Newton's gravitational constant, all 41 predictions — is derived from these five numbers and the electron mass (which sets the dimensional scale).

## Sample Output

```
PREDICTIONS TABLE:
  #  Observable             Predicted    Experimental    Comparison
----------------------------------------------------------------------
  1  1/α                       137.04          137.04       0.2 ppm
  2  sin²θ_W                  0.22222         0.22290         -1.7σ
  3  m_p/m_e                   1836.2          1836.2       1.1 ppm
  4  m_τ (MeV)                 1777.0          1776.9         +1.0σ
  5  sin θ_C                  0.22500         0.22500         +0.0σ
  ...
 39  m_H (GeV)                 125.00          125.11         -1.0σ
 40  f_π (MeV)                  93.00           92.20         0.86%
 41  m_ρ (MeV)                 766.86          775.30         1.09%
----------------------------------------------------------------------
SUMMARY:
  Combined χ² = 14.6 for 22 d.o.f.
  χ²/d.o.f. = 0.66
  p-value ≈ 0.88
```

## What the Script Computes

**Lepton sector:** Tau mass (Koide formula), proton-electron mass ratio (6π⁵ identity)

**Quark sector:** Six mass ratios from integer expressions, pion mass, neutron-proton splitting, Delta baryon mass, heavy quark masses (cross-sector Koide)

**Mixing angles:** Four PMNS parameters, Cabibbo angle, CKM CP phase, η̄ — all as ratios of the five integers

**Gauge sector:** Weinberg angle, electroweak scale, W boson mass, Higgs boson mass (λ = 4/31), gauge coupling ratio, hypercharge normalisation

**Gravity:** Newton's constant from G = αℏc/(m_e² φ^{n_G}), absolute electron mass

**Neutrinos:** Mass splitting ratio (= 34), absolute mass scale (seesaw), normal ordering, Σm_ν

**Beyond SM:** No proton decay, no monopoles, no SUSY, θ_QCD = 0

## How It Works

The script has four sections:

1. **INPUTS** (5 integers + 1 mass anchor)
2. **DERIVED CONSTANTS** (σ, δ, α, φ, n_G, M₀ — all computed, none fitted)
3. **41 PREDICTIONS** (each a closed-form expression of the above)
4. **OUTPUT** (comparison table with pulls, ppm, χ²)

Every formula is a direct transcription of the corresponding equation in the paper. The script contains no hidden parameters, no optimisation loops, and no fitting routines.

## Falsification

Five predictions are testable by experiments currently running:

| Prediction | Experiment | Timeline | Falsified if |
|---|---|---|---|
| m_τ = 1776.99 ± 0.05 MeV | Belle II | ~2027 | m_τ < 1776.87 or > 1777.12 MeV |
| Normal neutrino ordering | JUNO | ~2030 | Inverted ordering confirmed |
| Δm²₃₁/Δm²₂₁ = 34 | JUNO | ~2030 | Ratio outside 33.5–34.5 |
| sin²θ₂₃ = 9/16 | DUNE / Hyper-K | ~2030 | sin²θ₂₃ < 0.52 or > 0.60 |
| Σm_ν = 59–61 meV | CMB-S4 | ~2030 | Σm_ν > 80 meV |

## Validation

The script and the paper have been independently validated using:

- **Baker Sympy MCP** — symbolic verification of all algebraic identities to arbitrary precision
- **Baker KB** — epistemological status checking against a knowledge base of 5,000+ results spanning 14 research epochs
- **Independent reimplementation** — all 41 formulae verified by a second instance

The validation reports are available in the `validation/` directory.

## Repository Structure

```
├── README.md                 This file
├── predictions.py            The reproducibility script (sole deliverable)
├── LICENSE                   MIT License
└── validation/
    ├── validation_report_v14.md    First validation pass (3 errors, 5 warnings)
    ├── revalidation_report_v15.md  Second pass (2 cosmetic issues)
    └── code_validation_report.md   Script validation (3 bugs fixed)
```

## Citation

If you use this script or build on this work, please cite:

```bibtex
@article{baker2026octonionic,
  title   = {The Octonionic Origin of the Standard Model Parameters},
  author  = {Baker, Steve},
  year    = {2026},
  doi     = {10.5281/zenodo.1928853},
  note    = {41 zero-parameter predictions from G₂ holonomy geometry}
}
```

## Author

**Steve Baker** — Launceston, UK

## License

MIT License. See [LICENSE](LICENSE) for details.

