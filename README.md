# CTU KMD Semestral Project — Primary Source Distribution (MILP in PuLP)

This repository contains my **semestral project for CTU (Faculty of Transportation Sciences)**.

## Problem (Lecture 10 — Distribution system with a primary source)
We solve a **two-echelon distribution system**:
- **Primary source (PZ)** → **candidate warehouses (L1–L4)** → **customers (Z1–Z7)**

Goal: **minimize total cost**:
- transport cost (level 1 and level 2),
- fixed operating cost of opened warehouses.

The model is formulated as a **Mixed-Integer Linear Program (MILP)** and solved using **PuLP**.

## Model overview
**Decision variables**
- \(x_{ij}\in\{0,1\}\): customer \(j\) assigned to warehouse \(i\)
- \(y_i\in\{0,1\}\): warehouse \(i\) is opened

**Key constraints**
- warehouse capacity
- each customer assigned exactly once
- linking \(x_{ij}\le y_i\)
- special rule: customers 1–3 cannot be supplied from the same warehouse

## Repository contents
- `Semestralka_KMD_Primarni_zdroj_PuLP.ipynb` — full solution (model + results + interpretation)
- `diagram.jpg` — solution/network diagram

## How to run
1. Create environment (recommended):
   ```bash
   pip install pulp
