# Maximum Cut Problem (MaxCut) with Variational Quantum Imaginary Time Evolution (varQITE)

This repository demonstrates how to utilise [IonQ Forte][1]'s cutting-edge quantum computing platform to solve instances of the [NP-hard][2] combinatorial optimization problem known as the **Maximum Cut (MaxCut)** using a [novel variational Quantum Imaginary Time Evolution (varQITE)][4] algorithm developed by IonQ in collaboration with Oak Ridge National Labs (ORNL).

---

## Table of Contents

* [Overview](#overview)
* [The Problem: MaxCut 101](#the-problem-maxcut-101)
* [Why Quantum?](#why-quantum)
* [varQITE Method](#varqite-method)
* [Getting Started](#getting-started)
* [Example Usage](#example-usage)
* [Results](#results)
* [References](#references)

---

## Overview

The **Maximum Cut Problem (MaxCut)** is a benchmark problem in combinatorial optimization. It has broad applications, including:

* **Circuit Design (VLSI)** – optimizing the layout of circuit components
* **Social Networks** – identifying communities
* **Computer Vision** – image segmentation

MaxCut asks:

> Given a graph $G = (V, E)$, partition the vertex set $V$ into two sets $S$ and $T$ to maximize the number of edges crossing the partition.

Think of it as slicing a graph into two groups to cut through as many edges as possible.

---

## Why Quantum?

Classical methods for MaxCut can struggle with large, complex graphs due to exponential scaling. Quantum algorithms, particularly **variational approaches**, offer a promising path to explore new optimization strategies that are computationally intractable classically.

---

## varQITE Method

**Variational Quantum Imaginary Time Evolution (varQITE)** is a quantum algorithm that approximates the evolution of a quantum system in imaginary time to efficiently converge to the ground state of a Hamiltonian.

For MaxCut, the problem Hamiltonian is constructed from the graph, and varQITE is used to iteratively evolve the quantum state toward the optimal cut.

**Highlights:**

* Combines quantum state preparation with classical optimization
* Utilises IonQ’s high-fidelity qubits
* Demonstrated to outperform standard classical heuristics on benchmark instances

---

## Getting Started

### Requirements

* Python 3.9+
* [IonQ Forte SDK](https://ionq.com/forte)
* Standard scientific libraries: `numpy`, `scipy`, `networkx`, `matplotlib`

```bash
git clone https://github.com/<your-repo>.git
cd <your-repo>
pip install -r requirements.txt
```

---

## Example Usage

```python
import networkx as nx
from varQITE_maxcut import MaxCutSolver

# Create a sample graph
G = nx.cycle_graph(6)

# Solve MaxCut using varQITE
solver = MaxCutSolver(graph=G)
best_cut, max_edges = solver.solve()
print(f"Optimal partition: {best_cut}, Cut edges: {max_edges}")
```

You can see the algorithm converge over iterations in the notebook `MIT_Hackathon_2025_IonQuHack2025.ipynb`.

---

## Results

* Graphs up to **20 nodes** solved with **optimal or near-optimal cuts**
* High convergence speed compared to classical heuristics
* Visualizations of the cut for sample graphs included in the notebook

---

## References

https://ionq.com/forte

https://en.wikipedia.org/wiki/NP-hardness

https://en.wikipedia.org/wiki/Maximum_cut

https://arxiv.org/pdf/2404.16135
