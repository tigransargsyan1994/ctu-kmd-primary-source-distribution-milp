# CTU KMD Semestral Project  
## Primary Source Distribution — MILP Model in PuLP

This repository contains my **semestral project for the Czech Technical University in Prague (CTU)**,  
Faculty of Transportation Sciences.

The project was developed within the course framework and implements a complete  
**two-echelon distribution optimization model** using Mixed-Integer Linear Programming (MILP).

---

## Problem Description  
*(Distribution System with a Primary Source)*

We consider a two-level distribution network:

**Primary Source (PZ)**  
→ **Candidate Warehouses (L1–L4)**  
→ **Customers (Z1–Z7)**

The objective is to determine:

- which warehouses should be opened,
- how customers should be assigned,
- while minimizing the total system cost.

---

## Objective Function

The model minimizes total cost consisting of:

1. **Level 1 transport cost**  
   (Primary Source → Warehouses)

2. **Level 2 transport cost**  
   (Warehouses → Customers)

3. **Fixed warehouse operating costs**

The problem is formulated as a **Mixed-Integer Linear Program (MILP)**  
and solved using the Python library **PuLP**.

---

## Model Overview

### Decision Variables

- **Assignment variable**

  $$
  x_{ij} \in \{0,1\}
  $$

  Binary variable equal to 1 if customer \( j \) is served by warehouse \( i \), and 0 otherwise.

- **Opening variable**

  $$
  y_i \in \{0,1\}
  $$

  Binary variable equal to 1 if warehouse \( i \) is opened, and 0 otherwise.

---

### Key Constraints

- **Warehouse capacity constraints**

- **Unique customer assignment**  
  Each customer is assigned to exactly one warehouse.

- **Linking constraint**

  $$
  x_{ij} \le y_i
  $$

  A customer can only be assigned to warehouse \( i \) if that warehouse is opened.

- **Special separation rule**  
  Customers 1–3 cannot be supplied from the same warehouse.

---

## Repository Structure

- `Semestralka_KMD_Primarni_zdroj_PuLP.ipynb`  
  → Full implementation (data, model formulation, solution, interpretation)

- `diagram.jpg`  
  → Visualization of the optimal distribution structure

---

## How to Run

### 1️⃣ Install dependencies

```bash
pip install pulp
