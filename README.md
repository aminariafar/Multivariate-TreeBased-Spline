# 🌳 Multivariate Tree-Based Spline (MTS): A Tree-Guided Spline / GAM Modeling Framework

This repository contains the implementation and experimental evaluation of a **new spline-based modeling approach**, called **Multivariate-TreeBased-Spline (MTS)**, developed as part of a research collaboration with [**Dr. Abdollah Safari**](https://science.ut.ac.ir/~a.safari).  
The method extends classical spline models (and their multivariate generalization, **Generalized Additive Models — GAMs**) by introducing a **decision-tree–guided partitioning** of the feature space, followed by **local polynomial modeling within each leaf**.

The project includes:
- Implementation of multiple **MTS variants**  
- Synthetic data generators for controlled simulation studies  
- Extensive comparison against **LinearGAM** (from the `pygam` package) and **GLMTree** model (implemented based on partykit::glmtree in R language) across many experimental settings

---

## ✨ Key Contents

### Jupyter Notebook
- **`spline_tree.ipynb`** — Main notebook containing:
  - Implementation of the MTS model and its variants  
  - Data-generation utilities for correlated and uncorrelated feature scenarios  
  - Experimental comparisons with GAM, GLMTree, MARS, and SMART models  
  - Visualization of model performance, error behavior, and computational cost  

### Model Highlights
- **Tree-structured partitioning**: A decision tree groups samples into local regions.  
- **Local spline approximation**: Within each leaf, a polynomial/spline model is fitted.  
- **GAM interpretation**: The model behaves as a structured, piecewise GAM-like estimator.  
- **Multiple variants explored**: Different polynomial degrees, leaf complexities, and design choices.

Variants with inadequate empirical performance were excluded from the final comparisons but are kept in the repository for completeness.

---

## 🧱 Repository Structure
```
MTS/
├── spline_tree.ipynb        # Main research notebook: models, simulations, comparisons
├── nparrs/                  # Stored NumPy arrays for the result history of experiments
└── README.md                # Project description
```

---

## 🧪 Experiments & Evaluation

The project includes several controlled simulation environments, designed to compare MTS to classical models which perform subgroup specific regression: GAM, GLMTree, MARS, and SMART.

### Experimental Scenarios
- **Synthetic datasets** with adjustable:
  - Noise structure  
  - Feature correlation  
  - Dimensionality  
  - Nonlinearity levels  
- Comparison across:
  - **Polynomial degrees** (1, 2, 3, 4…)  
  - **Sample sizes** (N = 50, 200, 1000, 10000)  
  - **Model complexity** (# of leaves, fitting time, MSE errors)

### Metrics Studied
- Mean Squared Error (MSE)  
- Training time  
- Number of leaf partitions  
- Behavior under correlated vs. independent features  

These experiments reveal strengths and limitations of MTS across regimes and help identify the variants with the best empirical performance.

---

## 🎯 Research Context

This repository is a research project on **hybrid statistical–machine learning models**, combining interpretability of GAMs with flexibility of tree-based partitioning.  
It aims to provide:

- A reproducible benchmarking framework  
- A foundation for publishing MTS as a novel modeling approach  
- Insight into how structural partitioning improves spline-based regression  
