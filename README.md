<div align="center">

# Quantum Simulation of the Schwinger Model

### Executable Qiskit lecture notes for real-time lattice gauge theory simulation

[![Python](https://img.shields.io/badge/Python-3.x-blue)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)](https://jupyter.org/)
[![Qiskit](https://img.shields.io/badge/Qiskit-Quantum%20Simulation-6929C4)](https://www.ibm.com/quantum/qiskit)
[![Qiskit Aer](https://img.shields.io/badge/Qiskit%20Aer-Simulator-6929C4)](https://qiskit.github.io/qiskit-aer/)
[![PhysRevD](https://img.shields.io/badge/PhysRevD-10.1103%2FPhysRevD.103.L071502-blue)](https://doi.org/10.1103/PhysRevD.103.L071502)
[![PhysRevLett](https://img.shields.io/badge/PhysRevLett-10.1103%2FPhysRevLett.131.021902-red)](https://doi.org/10.1103/PhysRevLett.131.021902)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

<br>

**Schwinger model · Lattice gauge theory · Staggered fermions · Jordan-Wigner transformation · Adiabatic state preparation · Real-time dynamics · Chiral condensate · Qiskit**

<br>

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/IKEDAKAZUKI/Quantum-simulation-of-Schwinger-model/blob/main/Quantum_simulation_of_Schwinger_model.ipynb)

</div>

---

## Overview

This repository provides an executable lecture notebook for the **quantum simulation of the massive Schwinger model**, namely `1+1` dimensional quantum electrodynamics, using IBM Qiskit.

The notebook develops the physics and implementation step by step:

- continuum Schwinger-model Lagrangian,
- lattice Hamiltonian formulation,
- staggered fermion discretization,
- Jordan-Wigner transformation,
- spin-chain representation,
- Qiskit circuit implementation,
- Suzuki-Trotter real-time evolution,
- adiabatic state preparation,
- quench dynamics,
- θ-term driven phase-transition demonstration,
- measurement of observables such as the chiral condensate.

The goal is to give students and researchers a practical entry point into **digital quantum simulation of lattice gauge theories**.

---

## Scientific background

The Schwinger model is quantum electrodynamics in `1+1` spacetime dimensions. Despite its apparent simplicity, it captures several important features that make it a valuable testbed for high-energy physics and quantum simulation, including confinement, vacuum polarization, chiral condensates, topological terms, and real-time nonperturbative dynamics.

This tutorial is connected to the following representative works.

### Chern-Simons fluctuations and critical dynamics

> K. Ikeda, D. E. Kharzeev, and Y. Kikuchi,  
> **“Real-time dynamics of Chern-Simons fluctuations near a critical point,”**  
> *Physical Review D* **103**, L071502 (2021).  
> DOI: [10.1103/PhysRevD.103.L071502](https://doi.org/10.1103/PhysRevD.103.L071502)

### Jet production, entanglement, and vacuum modification

> A. Florio, D. Frenklakh, K. Ikeda, D. Kharzeev, V. Korepin, S. Shi, and K. Yu,  
> **“Real-Time Nonperturbative Dynamics of Jet Production in Schwinger Model: Quantum Entanglement and Vacuum Modification,”**  
> *Physical Review Letters* **131**, 021902 (2023).  
> DOI: [10.1103/PhysRevLett.131.021902](https://doi.org/10.1103/PhysRevLett.131.021902)

---

## Notebook

| Notebook | Description | Open |
|---|---|---|
| [`Quantum_simulation_of_Schwinger_model.ipynb`](Quantum_simulation_of_Schwinger_model.ipynb) | Lecture notebook for Qiskit-based simulation of the massive Schwinger model with a θ-term | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/IKEDAKAZUKI/Quantum-simulation-of-Schwinger-model/blob/main/Quantum_simulation_of_Schwinger_model.ipynb) |

---

## What you will learn

After working through the notebook, you should understand how to:

| Topic | What is covered |
|---|---|
| Schwinger model | Continuum `1+1` dimensional QED with mass, gauge field, and θ-term |
| Lattice Hamiltonian | Discretization, gauge links, electric fields, and Gauss-law constraint |
| Staggered fermions | Mapping a two-component Dirac fermion to lattice fermion degrees of freedom |
| Jordan-Wigner transformation | Mapping fermionic operators to Pauli operators |
| Spin Hamiltonian | Constructing the qubit Hamiltonian for the massive Schwinger model |
| Qiskit implementation | Building circuits for Hamiltonian time evolution |
| Suzuki-Trotter evolution | Simulating real-time dynamics with gate decompositions |
| Adiabatic state preparation | Preparing approximate ground states by slowly changing Hamiltonian parameters |
| Quench dynamics | Evolving out-of-equilibrium states in real time |
| Observables | Computing physical quantities such as the chiral condensate |
| Entanglement | Using reduced density matrices and entanglement entropy in quantum simulation |

---

## Model summary

The continuum Schwinger model is a `1+1` dimensional `U(1)` gauge theory with fermionic matter. A representative form of the Lagrangian density is

```math
\mathcal{L}
=
-\frac{1}{4} F_{\mu\nu}F^{\mu\nu}
+
\bar{\psi}
\left(
i\gamma^\mu \partial_\mu
-
g\gamma^\mu A_\mu
-
m
\right)
\psi
+
\frac{g\theta}{4\pi}
\epsilon^{\mu\nu}F_{\mu\nu}.
```

After discretization, staggered fermions, and a Jordan-Wigner transformation, the model can be written as a spin Hamiltonian built from Pauli operators. This makes it directly suitable for gate-based quantum simulation.

The notebook demonstrates how to translate the Hamiltonian into Qiskit circuits and how to extract real-time physical observables from measurement outcomes.

---

## Quick start

Clone the repository:

```bash
git clone https://github.com/IKEDAKAZUKI/Quantum-simulation-of-Schwinger-model.git
cd Quantum-simulation-of-Schwinger-model
```

Create a Python environment:

```bash
python3 -m venv .venv
source .venv/bin/activate
python3 -m pip install --upgrade pip
```

For Windows PowerShell:

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
```

Install the legacy-compatible Qiskit environment:

```bash
python3 -m pip install qiskit==0.44.3 qiskit-aer==0.12.2 numpy scipy matplotlib pylatexenc jupyter
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Then open:

```text
Quantum_simulation_of_Schwinger_model.ipynb
```

---

## Compatibility note

The notebook uses the classic Qiskit workflow based on:

```python
from qiskit import QuantumCircuit, QuantumRegister, ClassicalRegister
from qiskit import execute, Aer, BasicAer
```

For best reproducibility, use:

```text
qiskit==0.44.3
qiskit-aer==0.12.2
```

Modern Qiskit versions may require small import and backend-execution updates, especially for `execute`, `Aer`, and `BasicAer`.

---

## Running in Google Colab

The notebook can be opened directly in Google Colab:

```text
https://colab.research.google.com/github/IKEDAKAZUKI/Quantum-simulation-of-Schwinger-model/blob/main/Quantum_simulation_of_Schwinger_model.ipynb
```

When running in Colab, execute the package-installation cells at the beginning of the notebook before running the remaining cells.

---

## Main workflow

The notebook follows the structure below.

### 1. Define the Schwinger model

The continuum model is introduced as a massive `1+1` dimensional `U(1)` gauge theory with a θ-term.

### 2. Discretize the theory

The theory is placed on a lattice using staggered fermions and link variables.

### 3. Apply the Jordan-Wigner transformation

Fermionic degrees of freedom are mapped to qubit degrees of freedom using Pauli matrices.

### 4. Build the spin Hamiltonian

The lattice Hamiltonian is rewritten in terms of `X`, `Y`, and `Z` Pauli operators.

### 5. Implement time evolution

The Hamiltonian terms are decomposed into quantum gates and applied using Suzuki-Trotter time steps.

### 6. Prepare the ground state

An adiabatic state preparation protocol is used to approximate the interacting ground state.

### 7. Simulate a quench process

The system is evolved in real time after changing Hamiltonian parameters.

### 8. Measure physical observables

The notebook computes observables such as the chiral condensate from shot-based measurement results.

---

## Representative observables

The tutorial includes or motivates the computation of observables such as:

| Observable | Physical meaning |
|---|---|
| Chiral condensate | Vacuum structure and chiral symmetry response |
| Electric-field energy | Gauge-sector contribution to the Hamiltonian |
| Local charge | Matter distribution on the lattice |
| Entanglement entropy | Quantum correlation between subsystems |
| Time-dependent expectation values | Real-time response after quench or adiabatic evolution |

---

## Research context

This notebook can be used as an educational gateway to several active research directions:

- quantum simulation of lattice gauge theories,
- real-time nonperturbative quantum field dynamics,
- topological fluctuations and Chern-Simons diffusion,
- θ-vacua and critical behavior,
- jet fragmentation in the Schwinger model,
- vacuum modification by external sources,
- quantum entanglement in high-energy processes,
- near-term quantum algorithms for field theory.

---

## Repository structure

```text
.
├── Quantum_simulation_of_Schwinger_model.ipynb
├── LICENSE
└── README.md
```

---

## Suggested citation

If you use this notebook for teaching, research, or derivative lecture material, please cite this repository and the relevant papers below.

### Repository

```bibtex
@misc{IkedaSchwingerModelQiskitTutorial,
  author       = {Ikeda, Kazuki},
  title        = {Quantum Simulation of the Schwinger Model with Qiskit},
  year         = {2026},
  howpublished = {\url{https://github.com/IKEDAKAZUKI/Quantum-simulation-of-Schwinger-model}},
  note         = {Executable lecture notebook for digital quantum simulation of the massive Schwinger model}
}
```

### Chern-Simons fluctuations near a critical point

```bibtex
@article{PhysRevD.103.L071502,
  title = {Real-time dynamics of Chern-Simons fluctuations near a critical point},
  author = {Ikeda, Kazuki and Kharzeev, Dmitri E. and Kikuchi, Yuta},
  journal = {Phys. Rev. D},
  volume = {103},
  issue = {7},
  pages = {L071502},
  numpages = {7},
  year = {2021},
  month = {Apr},
  publisher = {American Physical Society},
  doi = {10.1103/PhysRevD.103.L071502},
  url = {https://link.aps.org/doi/10.1103/PhysRevD.103.L071502}
}
```

### Jet production, quantum entanglement, and vacuum modification

```bibtex
@article{PhysRevLett.131.021902,
  title = {Real-Time Nonperturbative Dynamics of Jet Production in Schwinger Model: Quantum Entanglement and Vacuum Modification},
  author = {Florio, Adrien and Frenklakh, David and Ikeda, Kazuki and Kharzeev, Dmitri and Korepin, Vladimir and Shi, Shuzhe and Yu, Kwangmin},
  journal = {Phys. Rev. Lett.},
  volume = {131},
  issue = {2},
  pages = {021902},
  numpages = {6},
  year = {2023},
  month = {Jul},
  publisher = {American Physical Society},
  doi = {10.1103/PhysRevLett.131.021902},
  url = {https://link.aps.org/doi/10.1103/PhysRevLett.131.021902}
}
```

---

## References

1. K. Ikeda, D. E. Kharzeev, and Y. Kikuchi,  
   **“Real-time dynamics of Chern-Simons fluctuations near a critical point,”**  
   *Physical Review D* **103**, L071502 (2021).  
   DOI: [10.1103/PhysRevD.103.L071502](https://doi.org/10.1103/PhysRevD.103.L071502)

2. A. Florio, D. Frenklakh, K. Ikeda, D. Kharzeev, V. Korepin, S. Shi, and K. Yu,  
   **“Real-Time Nonperturbative Dynamics of Jet Production in Schwinger Model: Quantum Entanglement and Vacuum Modification,”**  
   *Physical Review Letters* **131**, 021902 (2023).  
   DOI: [10.1103/PhysRevLett.131.021902](https://doi.org/10.1103/PhysRevLett.131.021902)

---

## License

This repository is released under the [MIT License](LICENSE).

Copyright (c) 2026 Kazuki Ikeda.

---

<div align="center">

**Quantum Simulation · Schwinger Model · Lattice Gauge Theory · Qiskit · Real-Time Dynamics**

</div>
