<div align="center">

# Heuristics-based Resource Allocation in Software-defined Vehicles  

Ousman Khan and Alaa Khamis  

</div>  

## 📖 Overview  
The rapid transition toward **Software-defined Vehicles (SDVs)** introduces new challenges in allocating **mixed-criticality applications** to virtual machines (VMs) under strict **safety, redundancy, and dependency constraints**.  

- **Exact methods** like Integer Linear Programming (ILP) guarantee optimality, but scale poorly for hundreds of applications.  
- This project explores **heuristic strategies** that provide *strict feasibility* while maintaining *runtime scalability*.  

We implement and evaluate three heuristic methods:  
- ✅ **CSCH**: Constraint-Satisfying Constructive Heuristic  
- ✅ **CSCH-Guided**: Degree-aware variant of CSCH  
- ✅ **AGA**: Randomized multi-start Adaptive Genetic Algorithm  

---

## 🎯 Objectives  
- Ensure feasible allocation under **ISO 26262 safety requirements**  
- Minimize the number of VMs required  
- Scale up to **800 applications** under an **80-VM platform cap**  
- Compare **heuristics vs. exact solvers** in terms of *compactness* and *runtime efficiency*  

---

## 📊 Results Summary  

### Minimal Solutions  
Heuristic methods achieve **feasible solutions at scale**, requiring only a modest increase in VMs compared to exact solvers.  

| Apps | Variables | Constraints | Exact VMs | Heuristic VMs |
|------|-----------|-------------|-----------|---------------|
| 100  | 8320      | 142,661     | **15.3**  | 19.3          |
| 400  | 32,320    | 2,154,001   | **21.3**  | 44.3          |
| 800  | 64,320    | 8,577,761   | **24.3**  | 75.0          |

---

### Runtime Comparison (seconds)  
Heuristics achieve **2–3 orders of magnitude faster runtimes**, completing even the largest instances in sub-second (CSCH/CSCH-Guided) or a few seconds (AGA).  

| Apps | CPLEX | Gurobi | SCIP | CSCH | CSCH-Guided | AGA |
|------|-------|--------|------|------|-------------|-----|
| 100  | 0.48  | 0.33   | 0.98 | **0.007** | 0.009 | 0.140 |
| 400  | 14.95 | 9.63   | 20.78| **0.156** | 0.159 | 2.675 |
| 800  | 143.5 | 60.2   | 162.9| **0.641** | 0.605 | 9.745 |

---

## 🔑 Key Insights  
- **Exact solvers** → More compact solutions but poor scalability.  
- **Heuristics** → Slightly higher VM usage, but **runtime up to 1000x faster**.  
- **CSCH & CSCH-Guided** → Near-instant runtimes, highly predictable.  
- **AGA** → Greater solution diversity, suitable for moderately large instances.  

---

## 🛠️ Getting Started  

### Requirements  
- Python 3.9+  
- Common scientific libraries: `numpy`, `scipy`, `matplotlib`  
- (Optional) OR-Tools or ILP solvers (for baseline comparison)  


## 🔖 Citation

Plain text (IEEE style):

Ousman Khan and Alaa Khamis, "Heuristics-based Resource Allocation in Software-defined Vehicles," submitted to 2025 IEEE Global Conference on Artificial Intelligence and Internet of Things (GCAIoT).

BibTeX:
```
@article{khan2025sdv,
  title   = {Heuristics-based Resource Allocation in Software-defined Vehicles},
  author  = {Ousman Khan and Alaa Khamis},
  journal = {Submitted to 2025 IEEE Global Conference on Artificial Intelligence and Internet of Things (GCAIoT)},
  year    = {2025}
}
```

## 🙏 Acknowledgment  

We would like to thank **Fengjunjie Pan** for providing the original codebase and dataset that supported this research. We also acknowledge the support of the **Interdisciplinary Research Center for Smart Mobility and Logistics at KFUPM** under Grant INML2501: *Contextual Observability of Software-Defined Vehicles*.  
