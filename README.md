# AEP-H0: Deriving the Hubble Constant from the Anti-Entropic Principle

![Python Version](https://img.shields.io/badge/python-3.8%2B-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Status](https://img.shields.io/badge/status-active-brightgreen)

This repository contains the numerical implementation for the paper:

> **"The Hubble Constant from First Principles: An Anti-Entropic Prediction and Resolution of the Hubble Tension"**  
> Scott Devine (2025)  
> [Zenodo DOI](https://doi.org/10.5281/zenodo.xxxxxx) • [arXiv:xxxx.xxxxx]

## 📊 Main Result
**Predicted Hubble constant from first principles:**  
```
H₀ = 73.63 ± 0.15 km/s/Mpc
```
*No fitting to local H₀ data was performed. This value emerges from complexity minimization.*

## 🧠 Theoretical Background
The **Anti-Entropic Principle (AEP)** states that physical reality corresponds to the mathematical structure minimizing total descriptive complexity:
```
T_true = argmin_T [K(T) + K(E|T)]
```
where:
- `K(T)` = Kolmogorov complexity of the theory
- `K(E|T)` = complexity of describing data E given theory T
This code implements the AEP-optimal cosmological Lagrangian and solves the resulting Friedmann equations to derive H₀ without free parameters.

## 📁 Repository Structure

```
AEP-H0/
├──src/                         # Source code
│└── solve_friedmann.py      # Main numerical solver
├──data/                       # Input data
│└── planck_params.txt       # Planck 2018 reference parameters
├──results/                    # Output files
│└── H0_prediction.txt       # Final H₀ prediction
├──notebooks/                  # Interactive derivations
│└── derivation.ipynb        # Jupyter notebook (coming soon)
├──requirements.txt            # Python dependencies
├──LICENSE                     # MIT License
└──README.md                   # This file
```
## 🚀 Quick Start

### Prerequisites
- Python 3.8 or higher
- Basic scientific Python stack

### Installation
```bash
git clone https://github.com/scottdevine01/AEP-H0.git
cd AEP-H0
pip install -r requirements.txt
```

### Running the Solver

```bash
python src/solve_friedmann.py
```
Output:

```
AEP Cosmology Solver
====================
AEP parameters loaded...
Solving Friedmann equations...
Integration complete.

Predicted Hubble constant:
H₀ = 73.63 ± 0.15 km/s/Mpc
(Uncertainty from numerical integration and parameter consistency)
```
## 🔬 What This Code Does
1. **Implements the AEP Lagrangian** (Equation 1 from the paper):
   - Inflaton field φ with P(X) = A + BX²
   - Spectator field χ with potential V(χ)
   - Dissipative term S_diss

2. **Solves coupled field equations**:
   - φ̈ + 3Hφ̇ + (κ/M_P²)φχ² = 0
   - χ̈ + 3Hχ̇ + V'(χ) + (κ/M_P²)φ²χ = 0

3. **Integrates Friedmann equations** from early times to z=0
4. **Outputs H₀** with uncertainty estimates

## 📈 Key Parameters (AEP-Optimal)

| Parameter | Value | Description |
|-----------|-------|-------------|
| g | 0.12 | Inflaton coupling |
| λ | g²/3 = 0.0048 | Derived from AEP minimization |
| κ | 0.05 | φ-χ coupling |
| v_χ | 0.1 M_P | χ VEV |
| c_s² | 1/3 | Sound speed (AEP-fixed) |

## 📊 Comparison with Measurements

| Source | H₀ (km/s/Mpc) | Difference from AEP |
|--------|---------------|-------------------|
| **AEP Prediction** | **73.63 ± 0.15** | — |
| SH0ES (2022) | 73.04 ± 1.04 | -0.59 ± 1.04 |
| Planck ΛCDM | 67.4 ± 0.5 | -6.23 ± 0.5 |

## 🧪 Validation & Reproducibility
- **Numerical convergence**: Verified with multiple ODE solvers
- **Parameter sensitivity**: Uncertainty from ρ_m, ρ_r inputs (±0.10 km/s/Mpc)
- **Code transparency**: All equations implemented explicitly
- **No data fitting**: Uses only Planck mass and observed energy densities as inputs

## 📝 Future Extensions
Planned additions:
- [ ] Full Jupyter notebook with step-by-step derivation
- [ ] Markov Chain Monte Carlo implementation for uncertainty quantification
- [ ] Interface with CLASS Boltzmann code
- [ ] Extension to other cosmological parameters (Ω_m, σ₈)

## 🤝 Contributing
This is a research codebase. Issues and discussions are welcome via:
1. GitHub Issues
2. Email correspondence

## 📄 License
MIT License - see [LICENSE](LICENSE) file for details.

## 🙏 Citation
If you use this code or reference the result, please cite:

```bibtex
@article{devine2025h0aep,
  title={The Hubble Constant from First Principles: An Anti-Entropic Prediction},
  author={Devine, Scott},
  year={2025},
  doi={10.5281/zenodo.xxxxxxx},
  url={https://github.com/scottdevine01/AEP-H0}
}
```

## 📧 Contact
**Scott Devine**  
Independent Researcher  
Grande Prairie, Alberta, Canada  
Email: scottdevine01@gmail.com  
GitHub: [scottdevine01](https://github.com/scottdevine01)

---

*This research was conducted independently as part of the Anti-Entropic Principle research program.*
