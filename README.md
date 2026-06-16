# Electrochemical Materials Discovery via Scientific Machine Learning

**Muhammad Athar** — MPhil Inorganic & Analytical Chemistry, Quaid-i-Azam University  
 m.athar1515@gmail.com | 🔗 [LinkedIn](https://www.linkedin.com/in/athar-muhammad-51700121a) | 📄 [ResearchGate](https://www.researchgate.net/profile/Muhammad-Athar-31?ev=hdr_xprf&_tp=eyJjb250ZXh0Ijp7ImZpcnN0UGFnZSI6InB1YmxpY2F0aW9uIiwicGFnZSI6InB1YmxpY2F0aW9uIiwicG9zaXRpb24iOiJnbG9iYWxIZWFkZXIifX0)

---

## Research Overview

This repository documents my MPhil thesis work on **accelerating materials discovery for supercapacitor and electrocatalytic applications** by integrating wet-lab electrochemical experimentation with Scientific Machine Learning (SciML) algorithms.

> **Core Result:** Achieved a specific capacitance of **1576 F g⁻¹ at 1 A g⁻¹** using ML-optimized MnO₂–Kovar hybrid electrodes in 3M KOH electrolyte.

---

##  ML Pipelines

### 1. Bayesian Optimization with Gaussian Process (BO-GP)
- **Goal:** Map structural synthesis parameters → electrochemical performance
- **Method:** Gaussian Process surrogate function + Expected Improvement acquisition
- **Stack:** `scikit-learn`, `GPy`, `numpy`, `pandas`
- **Outcome:** Reduced experimental iterations by ~60% vs. grid search

```python
# Example: BO-GP surrogate model for capacitance prediction
from sklearn.gaussian_process import GaussianProcessRegressor
from sklearn.gaussian_process.kernels import Matern

kernel = Matern(length_scale=1.0, nu=2.5)
gpr = GaussianProcessRegressor(kernel=kernel, alpha=1e-6, normalize_y=True)
gpr.fit(X_train, y_train)
y_pred, sigma = gpr.predict(X_test, return_std=True)
```

### 2. Semi-Non-negative Matrix Factorization (Semi-NMF)
- **Goal:** Unsupervised decomposition of CV datasets to identify optimal precursor ratios
- **Input:** Cyclic Voltammetry current-potential matrices across synthesis configurations
- **Outcome:** Identified optimal ratio — `10 wt% MnO₂ + 90 wt% NiFe₂O₄/CoMn₂O₄`
- **Stack:** `numpy`, `scipy`, `matplotlib`, `UMAP`

### 3. SHAP Explainability Pipeline
- **Goal:** Feature importance analysis for electrochemical performance drivers
- **Features:** Synthesis temperature, sonication time, precursor wt%, anodization voltage
- **Stack:** `XGBoost`, `shap`, `matplotlib`

---

## Experimental Techniques

| Technique | Purpose |
|-----------|---------|
| Cyclic Voltammetry (CV) | Charge storage mechanism, capacitive vs. diffusive contributions |
| Galvanostatic Charge-Discharge (GCD) | Specific capacitance, energy & power density |
| Electrochemical Impedance Spectroscopy (EIS) | Charge-transfer resistance, Warburg diffusion |
| Powder XRD | Phase identification, crystallite size (Scherrer equation) |
| FESEM + EDS Mapping | Surface morphology, elemental distribution |
| XPS | Oxidation state confirmation, surface chemistry |
| FTIR | Functional group verification |
| UV-Vis | Optical bandgap estimation |

---

## Key Results

```
Electrode System:       MnO₂–Kovar Hybrid (Electrochemical Anodization + Co-precipitation)
Electrolyte:            3M KOH
Specific Capacitance:   1576 F g⁻¹ @ 1 A g⁻¹
Optimized by:           Semi-NMF on CV dataset matrix
Degradation Analysis:   EIS cyclic profiling over 5000 cycles
```

---

##  Repository Structure

```
 electrochemical-ml-discovery
├──  data/
│   ├── cv_raw/              # Raw cyclic voltammetry datasets
│   ├── eis_spectra/         # Electrochemical impedance data
│   └── gcd_profiles/        # Charge-discharge curves
├──  models/
│   ├── bo_gp_optimizer.py   # Bayesian Optimization pipeline
│   ├── semi_nmf.py          # Semi-NMF clustering on CV data
│   └── shap_analysis.py     # Feature importance with XGBoost + SHAP
├──  notebooks/
│   ├── 01_data_preprocessing.ipynb
│   ├── 02_bo_gp_optimization.ipynb
│   ├── 03_semi_nmf_clustering.ipynb
│   └── 04_results_visualization.ipynb
├──  characterization/
│   ├── xrd_analysis/        # Diffractogram fitting (OriginPro exports)
│   └── sem_images/          # FESEM micrographs
├── requirements.txt
└── README.md
```

---

##  Tech Stack

```
Python 3.10+         scikit-learn    TensorFlow      XGBoost
NumPy / Pandas       Matplotlib      SHAP            UMAP
GPy (Gaussian)       SciPy           OriginPro       ORCA / Gaussian
```

---

##  Publication

> S. Batool, I. Ud-Din, A. Zafar, **M. Athar**, et al. *Zinc(II) Derivatives of N,O Containing Schiff Bases: Synthesis, Characterization, Computational and Biological Studies.* **Journal of Coordination Chemistry**, 76(9–10), 1189–1213 (2023).  
> DOI: [10.1080/00958972.2023.2230607](https://doi.org/10.1080/00958972.2023.2230607)

---

##  Education

- **MPhil Chemistry** — Quaid-i-Azam University (2024–2026) | *Ranked 3rd Nationwide, MPhil Entrance Exam*
- **BS Chemistry** — Quaid-i-Azam University (2021–2023) | *HEC Merit Scholarship*
- **BSc Chemistry** — Gomal University (2019–2021) | *4th Position Overall, Gold Medalist Track*

---

##  Contact

Open to research collaborations, internships, and R&D opportunities in materials science, energy storage, and scientific ML.  
 **m.athar1515@gmail.com**
