# rSLDS Analysis of MPO Neural Activity During Aggression

## Overview

This repository contains the complete analysis pipeline for modeling neural population dynamics in the medial preoptic area (MPO) during aggressive behavior in mice. We use Recurrent Switching Linear Dynamical Systems (rSLDS) to identify low-dimensional latent structure in calcium imaging data and systematically optimize model parameters using variance explained (VE) as the selection criterion.

## Key Findings

- **Optimal model**: K=3 discrete states, D=24 latent dimensions
- **Variance explained**: 91.08% (single bout), 93.79% (best bout)
- **Distributed encoding**: No single latent dimension dominates (max VE = 8.0%)
- **Individual bouts**: All 6 bouts achieve VE ≥ 89.91% (mean = 91.89% ± 1.20%)
- **Concatenated bouts**: Only 77.50% VE, suggesting bout-specific latent trajectories

The main analysis notebook (ve_optimization.ipynb) is organized as follows:

Section	Description
1. Setup:	Import libraries and define utility functions for rSLDS fitting and variance explained computation
2. Data Loading:	Load rawdata_combined.mat, extract MPO_cno condition, and identify first aggression bout
3. Experiment 1:	Fixed K=3, D=2-10: Establish baseline VE progression
4. Experiment 2:	Grid search K=2-5, D=2-8: Identify optimal (K,D) combination
5. Experiment 3:	Multi-seed validation: Test robustness of top configurations
6. Experiment 4:	High D search (10-20): Approach 90% VE target
7. Experiment 5:	Extended D search (20-24): Achieve 90% VE target at D=24
8. Experiment 6:	All 6 bouts analysis: Compare individual vs. concatenated bout performance
9. Visualization:	Generate energy landscapes, ELBO curves, and per-latent VE distributions
