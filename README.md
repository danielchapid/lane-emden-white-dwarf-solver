# Numerical Solver for the Lane-Emden Equation & Quantum Degeneracy in White Dwarfs

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)

## 🎯 Overview
This repository provides a numerical implementation and physical analysis of stellar hydrostatic equilibrium modeled by the **Lane-Emden equation** for various polytropic indices ($n$). 

The study models the interior of white dwarfs by coupling classical polytropic structures with quantum statistical mechanics, specifically analyzing the pressure exerted by completely degenerate non-relativistic and relativistic electron gases using Fermi-Dirac statistics.

---

## 🔬 Theoretical Framework

The Lane-Emden equation is a dimensionless form of Poisson's equation for a spherically symmetric, self-gravitating polytropic fluid:

$$\frac{1}{\xi^2} \frac{d}{d\xi} \left( \xi^2 \frac{d\theta}{d\xi} \right) + \theta^n = 0$$

Subject to boundary conditions at the stellar center:
$$\theta(0) = 1, \quad \left. \frac{d\theta}{d\xi} \right\vert{}_{\xi=0} = 0$$

### Key Topics:
1. **Coordinate Singularity at the Origin:** Numerical divergence at $\xi \to 0$ is resolved using a Taylor series expansion for initial step-sizes:
   $$\theta(\xi) \approx 1 - \frac{\xi^2}{6} + \frac{n \xi^4}{120} + \mathcal{O}(\xi^6)$$
2. **Numerical Integration:** System of coupled first-order ODEs integrated using a custom **4th-Order Runge-Kutta (RK4)** algorithm until reaching the stellar surface ($\theta(\xi_1) = 0$).
3. **Quantum Degeneracy Pressure:** Comparison between polytropes $n=1.5$ (non-relativistic degenerate Fermi gas, $P \propto \rho^{5/3}$) and $n=3.0$ (extreme relativistic limit, Chandrasekhar mass threshold).

---

## 📁 Repository Structure

```text
├── POSTER_ESTADÍSTICA.pdf           # Research poster on quantum degeneracy in white dwarfs
├── Proyecto_estadística_Final.ipynb # Jupyter notebook with RK4 solver, analysis, and visualizations
└── README.md                         # Project documentation
