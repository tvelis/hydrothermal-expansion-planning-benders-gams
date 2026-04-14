# Hydrothermal Expansion Planning with Benders Decomposition (GAMS)

This repository contains the original optimization model developed for my 2009 undergraduate thesis:

### “Planificación de la Expansión de un Sistema Hidrotérmico”
Universidad Centroamericana José Simeón Cañas (UCA)

## Overview

The model solves a long-term hydrothermal generation expansion planning problem using:

- Benders decomposition
- Mixed-integer optimization
- Hydrothermal dispatch simulation
- Candidate project selection under investment constraints

The case study is based on El Salvador’s electric power system.

---

## Mathematical Structure

### Master Problem
Determines:

- Which candidate plants are built
- In which year they enter service

Decision variables are binary.

Examples:
- Coal plants
- LNG combined cycles
- Hydro projects (Chaparral, Cimarrón)

---

### Subproblem
Determines:

- Monthly hydrothermal dispatch
- Reservoir operation
- Thermal generation levels
- Operating cost minimization

---

## Benders Decomposition Logic

Each iteration:

1. Master proposes investment plan.
2. Subproblem evaluates operation cost.
3. Dual variables generate Benders cuts.
4. Cuts are added to master problem.
5. Process repeats until convergence.

---

## Case Study Results

Optimal expansion plan includes projects such as:

- Chaparral Hydro
- Chinameca Geothermal
- Cimarrón Hydro
- Coal Steam Plants
- LNG Combined Cycle

---

## Repository Structure

```text
/
├── model/
│   ├── main.gms
│   ├── master.gms
│   ├── slave.gms
│   ├── cuts.gms
│   └── data.inc
├── data/
├── docs/
│   ├── thesis_2009.pdf
│   └── diagrams/
├── results/
└── README.md
