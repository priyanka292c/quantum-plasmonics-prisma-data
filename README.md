# Quantum Plasmonics & Photonic Entanglement: Open Research Data & Code Repository

[![PRISMA 2020](https://img.shields.io/badge/PRISMA-2020%20Compliant-blue.svg)](https://prisma-statement.org/)
[![Python 3.11+](https://img.shields.io/badge/Python-3.11%2B-green.svg)](https://www.python.org/)
[![Access: Open Academic](https://img.shields.io/badge/Access-Open%20Academic-success.svg)](#15--open-access--data-use-terms)
[![Repository: GitHub](https://img.shields.io/badge/GitHub-priyanka292c%2Fquantum--plasmonics--prisma--data-blue)](https://github.com/priyanka292c/quantum-plasmonics-prisma-data)

**Official Open Data & Computational Reproduction Repository** for the review article:
> **"Quantum Plasmonics in Nanostructured Optical Environments: Green-Tensor Formalisms, Quantum Coherence, Entanglement, and Emerging Platforms"**  
> *Target Journal*: **Photonics and Nanostructures – Fundamentals and Applications** (Elsevier)  
> *Authors*: **Priyanka** (Department of Physics and Astrophysics, University of Delhi) & **Ram Soorat\*** (School of Technology, Woxsen University)  
> *Correspondence*: `ram.soorat@woxsen.edu.in`  
> *Permanent Repository URI*: [https://github.com/priyanka292c/quantum-plasmonics-prisma-data](https://github.com/priyanka292c/quantum-plasmonics-prisma-data)

---

## Table of Contents
1. [Repository Purpose & Scientific Scope](#1-repository-purpose--scientific-scope)
2. [Repository Structure](#2-repository-structure)
3. [Python Version & Environment Requirements](#3-python-version--environment-requirements)
4. [Required Packages & Dependencies](#4-required-packages--dependencies)
5. [Installation Commands](#5-installation-commands)
6. [PRISMA 2020 Dataset Locations & Formats](#6-prisma-2020-dataset-locations--formats)
7. [How to Reproduce PRISMA Screening Counts](#7-how-to-reproduce-prisma-screening-counts)
8. [How to Reproduce Bibliometric & Publication Figures](#8-how-to-reproduce-bibliometric--publication-figures)
9. [How to Run Green-Tensor Calculations](#9-how-to-run-green-tensor-calculations)
10. [How to Reproduce Concurrence & Entanglement Calculations](#10-how-to-reproduce-concurrence--entanglement-calculations)
11. [How to Reproduce Dielectric Permittivity Fitting](#11-how-to-reproduce-dielectric-permittivity-fitting)
12. [Expected Output Files & Validation](#12-expected-output-files--validation)
13. [Reference & BibTeX Database Description](#13-reference--bibtex-database-description)
14. [Software Versions & Environmental Telemetry](#14-software-versions--environmental-telemetry)
15. [Open Access & Data-Use Terms](#15--open-access--data-use-terms)

---

## 1. 🎯 Repository Purpose & Scientific Scope

This repository provides full computational and evidentiary transparency for the review article *"Quantum Plasmonics in Nanostructured Optical Environments: Green-Tensor Formalisms, Quantum Coherence, Entanglement, and Emerging Platforms"*.

The scientific objective of this work is to bridge material electrodynamics and multi-qubit quantum information processing through a unifying physical mapping:
$$\varepsilon(\mathbf{r},\omega) \xrightarrow{\text{Helmholtz}} \overleftrightarrow{\mathbf{G}}(\mathbf{r},\mathbf{r}',\omega) \xrightarrow{\text{LDOS / Cross-terms}} (\gamma_{ij},\Omega_{ij}) \xrightarrow{\text{Master Eq.}} \hat{\rho}(t) \xrightarrow{\text{Tomography}} \left\{ \mathcal{C},\mathcal{N},S_{\rm CHSH},F_Q \right\}$$

This repository hosts:
1. The **complete PRISMA 2020 systematic screening workflow** covering 1,420 retrieved records down to 248 primary included peer-reviewed studies (2010--2026).
2. The **numerical open-quantum-system master equation solvers** for two-qubit collective Lindblad and concurrence dynamics.
3. The **calibrated empirical dielectric data** (Au, Ag, Al) and bounded weighted non-linear least-squares fitting scripts.
4. The **publication vector/raster figures** and the **curated BibTeX database** (`references_200.bib`, 246 indexed records).

---

## 2. 📂 Repository Structure

```text
quantum-plasmonics-prisma-data/
├── README.md                              # Comprehensive reproduction guide (this document)
├── references_200.bib                     # Master curated BibTeX database (246 verified records)
│
├── [PRISMA 2020 Systematic Review Datasets]
│   ├── prisma_search_log.csv              # Multi-stage screening audit log (1,420 -> 890 -> 478 -> 248)
│   └── prisma_included_studies_master.csv # Master dataset of 248 primary included studies with metrics
│
├── [Computational Solvers & Reproduction Scripts]
│   ├── qubit_concurrence_dynamics.py      # Collective Lindblad master equation solver for two-qubit concurrence
│   ├── fit_dielectric_drude_lorentz.py    # Multi-oscillator Drude-Lorentz bounded least-squares fitter
│   └── plot_review_figures.py             # Pipeline generating all review figures and supplementary plots
│
├── [Numerical Trajectories & Empirical Data]
│   ├── concurrence_dynamics_benchmark.csv # Time-resolved concurrence C(t), negativity N(t), purity Tr(rho^2)
│   └── raw_dielectric_data_au_ag_al.csv   # Empirical permittivity data (Johnson & Christy 1972, Palik 1985)
│
└── figures/                               # Publication-ready vector PDF/SVG and 300-dpi raster PNG figures
    ├── fig_review_1_concept.*             # Unifying Electrodynamics-to-Quantum Mapping
    ├── fig_review_2_green_tensor.*        # Dyadic Green Tensor & LDOS Formalism
    ├── fig_review_3_non_hermitian.*       # Exceptional Points, Chiral Routing & PT Symmetry
    ├── fig_review_4_experimental.*        # Experimental Nanogap Platforms & Confinement
    ├── fig1_roadmap_timeline.*            # Technology Roadmap 2010--2035 with 4-Tier Evidentiary Classification
    ├── fig3_spp_dispersion.*              # Polariton Dispersion & Ohmic Damping Relations
    ├── fig6_nonlocality_tunneling.*       # Hydrodynamic Non-locality & Quantum Electron Tunneling Regimes
    ├── fig7_review_purcell_vs_modevol.*   # Purcell Factor vs. Normalized Mode Volume Trade-off
    ├── fig8_ai_inverse_design.*           # Adjoint Sensitivity & FNO Neural Operator Surrogates
    ├── fig8_review_quantum_sensing.*      # Quantum Fisher Information & Quantum Metrology Bounds
    ├── figS1_prisma_flowchart.*           # PRISMA 2020 Systematic Flow Diagram
    ├── figS2a_au_permittivity.*           # Gold Multi-Oscillator Drude-Lorentz Permittivity Fits
    ├── figS2b_ag_al_permittivity.*        # Silver & Aluminum Multi-Oscillator Permittivity Fits
    └── figS3_publication_trends.*         # Search-Pool Annual Growth Dynamics (2010--2025)
