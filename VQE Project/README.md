# VQE Approach to Prime Factorization on NISQ Hardware

This project is a replication and extension of the research conducted by **Sobhani, Chai, Hartung, and Jansen** in *Physical Review A 111, 042413 (2025)*. It implements a Variational Quantum Eigensolver (VQE) pipeline optimized for integer factorization on IBM's Noisy Intermediate-Scale Quantum (NISQ) devices.

## Highlights
* **Largest $n$ factored (Real Hardware):** 253 (on `ibm_fez`)
* **Largest $n$ factored (Ideal Simulation):** 1,048,561
* **Best Optimizer:** NFT (Nakanishi-Fujii-Todo) for $N \ge 13$ qubits
* **Innovation:** Implemented a **Mean-Field Initialization (S3)** strategy that boosted success rates to 80%.

## Methodology
The project encodes the factorization problem $(n - pq)^2$ into a Pauli-Z Hamiltonian. To overcome barren plateaus, we use:
* **CVaR (Conditional Value-at-Risk):** A cost function that averages only the top $\alpha$-fraction of best results.
* **Ansatz:** Hardware-efficient Linear-CNOT layers.
* **Cost Variants:** Comparison between Hamiltonian, Logarithmic, and Inverse cost functions.

## Results Summary
| Metric | Value |
| :--- | :--- |
| **Qubits Used** | Up to 16 free qubits |
| **Optimizers** | COBYLA, NFT |
| **Hardware** | IBM Fez |
| **Warm-start** | Mean-Field (S3), Multi-start, Hamiltonian pre-train |

## References
1. Sobhani et al., "Prime factorization using variational quantum eigensolver," *Phys. Rev. A 111, 042413 (2025)*.
2. Barkoutsos et al., "Improving variational quantum optimization using CVaR," *Quantum 4, 256 (2020)*.

---
**Author:** Mrudula A Mahindrakar
**Course:** ID5841: Quantum Computing Lab
