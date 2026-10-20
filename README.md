# 2D Magnetism Lab: From Quantum DFT to Thermodynamics

[![GitHub Pages](https://img.shields.io/badge/Live-Demo-brightgreen?style=for-the-badge&logo=github)](https://Asif-Iqbal-Bhatti.github.io/2d-magnetism-lab/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)
[![Physics: 2D Magnetism](https://img.shields.io/badge/Physics-2D%20Magnetism-cyan?style=for-the-badge)](https://doi.org/10.1038/nature22391)
[![Materials Project](https://img.shields.io/badge/Materials%20Project-API%20Enabled-purple?style=for-the-badge)](https://materialsproject.org)

An interactive, research-grade computational materials physics laboratory and simulator exploring **two-dimensional magnetism in monolayer Chromium Triiodide ($\text{CrI}_3$)** and related van der Waals magnets.

Based on the pedagogical framework of **Prof. Yen Lee Loh** (*"Determination of Magnetic Transitions: Monte Carlo Simulations"*, TÜBİTAK Workshop 2021).

---

## 🌟 Live Interactive Demo

Launch the simulator directly in your browser with zero installation:  
👉 **[Launch 2D Magnetism Lab](https://Asif-Iqbal-Bhatti.github.io/2d-magnetism-lab/)**

---

## 🔬 Scientific Premise & Core Features

### 1. The Physics Question: Why Does 2D Magnetism Exist?
In 1966, the **Mermin-Wagner Theorem** proved that continuous $SO(3)$ spin rotational symmetry forbids spontaneous magnetic order in 2D at any finite temperature ($T > 0$) due to divergent long-wavelength Goldstone spin waves (magnons, $\omega \propto k^2$):
$$n_{\text{magnon}} \sim \int \frac{k\,dk}{e^{D k^2 / k_B T} - 1} \approx \frac{k_B T}{D} \int \frac{dk}{k} \longrightarrow \infty \implies T_c \equiv 0\text{ K}$$

Yet in 2017, physicists discovered that monolayer $\text{CrI}_3$ is ferromagnetic up to **$T_c \approx 45\text{ K}$** (*Huang et al., Nature*). 
This lab demonstrates how relativistic **spin-orbit coupling (SOC)** from heavy Iodine ligands ($Z=53$) induces an out-of-plane **Magnetic Anisotropy Energy (MAE)** barrier ($K \approx 31.4\text{ K}$), opening a spectral gap $\Delta \sim 2K$ in the spin-wave dispersion that cuts off the infrared divergence and rescues finite-temperature ferromagnetism!

### 2. The 5-Attempt Progression
* **Attempt 1: Honeycomb Ising ($J_1$ only)** $\to T_c \approx 22\text{ K}$ (minimal cell misses 2nd-neighbor superexchange).
* **Attempt 2: Supercell Ising ($J_1, J_2$)** $\to T_c \approx 140\text{ K}$ ($J_2 \approx 30.9\text{ K}$ dominates, but 1D Ising overshoots).
* **Attempt 3: Classical Isotropic Heisenberg** $\to T_c = 0\text{ K}$ (**Mermin-Wagner Theorem** destroys 2D continuous order).
* **Attempt 4: Anisotropic Heisenberg (MAE / SOC)** $\to T_c \approx 50\text{ K}$ (easy-axis gap restores order, matching experiment!).
* **Attempt 5: Quantum Corrections ($S=3/2$)** $\to T_c \approx 45\text{ K}$ (zero-point fluctuations trim $T_c$ to exact match).

### 3. Interactive Features & Tools
* **3D Crystal Viewport with Orbit Controls**: Click & drag to rotate (pitch & yaw), scroll to zoom, right-drag to pan. Presets for 3D Perspective, Top ($c$-axis), Side ($a/b$-profile), and Auto-Rotate.
* **Real-Time Metropolis Monte Carlo (60 FPS)**: High-performance simulation supporting both Ising ($\pm 1$) and 3D Heisenberg continuous vectors ($\vec{S} \in S^2$) using the exact **Rodrigues rotation formula** for strict detailed balance.
* **Materials Project REST API & 2D Library**: Connect your free Materials Project API key to fetch live DFT data, or select from pre-loaded 2D magnets: $\text{CrI}_3$, $\text{CrBr}_3$, $\text{CrCl}_3$, $\text{Fe}_3\text{GeTe}_2$, and $\text{Cr}_2\text{Ge}_2\text{Te}_6$.
* **High-DPI Scientific Charts**: Real-time order parameter $|M(t)|$ and phase diagram $M(T)$ with live pulsing state cursor and theoretical MFT / Onsager curves.
* **DFT Linear Regression Lab**: Interactive matrix showing feature vectors $X_b$, DFT energies, and live least-squares solver.
* **MAE & Anisotropy Lab**: Interactive polar angle $\theta$ slider visualizing $E_{\text{MAE}}(\theta) = E_0 + K \sin^2\theta$.
* **Binder Cumulant Crossing**: Finite-size scaling showing $B(T, L) = \langle M^4 \rangle / \langle M^2 \rangle^2$ intersection at $T_c$.

---

## 🚀 How to Run Locally

Because the application is 100% self-contained in a single file (`index.html`), simply clone the repository and open `index.html` in any web browser:

```bash
git clone https://github.com/Asif-Iqbal-Bhatti/2d-magnetism-lab.git
cd 2d-magnetism-lab
# Open index.html in your browser:
# On Windows / WSL:
explorer.exe index.html
# On macOS:
open index.html
# On Linux:
xdg-open index.html
```

---

## 📚 Scientific References & Citations

1. **Yen Lee Loh**, *"Determination of Magnetic Transitions: Monte Carlo Simulations,"* Magnetic Properties from First Principles, TÜBİTAK Workshop, Nov 24-26 (2021).
2. **B. Huang, G. Clark, E. Navarro-Moratalla, et al.**, *"Layer-dependent ferromagnetism in a van der Waals crystal of $\text{CrI}_3$,"* *Nature* **546**, 270–273 (2017). DOI: [10.1038/nature22391](https://doi.org/10.1038/nature22391).
3. **N. D. Mermin and H. Wagner**, *"Absence of Ferromagnetism or Antiferromagnetism in One- or Two-Dimensional Isotropic Heisenberg Models,"* *Phys. Rev. Lett.* **17**, 1133 (1966). DOI: [10.1103/PhysRevLett.17.1133](https://doi.org/10.1103/PhysRevLett.17.1133).
4. **C. Domb**, *"On the theory of cooperative phenomena in crystals,"* *Adv. Phys.* **9**, 149 (1960). DOI: [10.1080/00018736000101199](https://doi.org/10.1080/00018736000101199).
5. **A. Jain et al.**, *"Commentary: The Materials Project: A materials genome approach to accelerate materials innovation,"* *APL Materials* **1**, 011002 (2013). Materials Project ID: [`mp-1213805`](https://materialsproject.org/materials/mp-1213805/).

---

## 📄 License

This project is open-source under the [MIT License](LICENSE).
