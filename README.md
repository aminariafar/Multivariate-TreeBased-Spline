# 🌳 TreeSpline: A Tree-Guided Spline / GAM Modeling Framework

This repository contains the implementation and experimental evaluation of a **new spline-based modeling approach**, called **TreeSpline**, developed as part of a research collaboration with **Dr. Abdollah Safari**.  
The method extends classical spline models (and their multivariate generalization, **Generalized Additive Models — GAMs**) by introducing a **decision-tree–guided partitioning** of the feature space, followed by **local polynomial modeling within each leaf**.

The project includes:
- Implementation of multiple **TreeSpline variants**  
- Synthetic data generators for controlled simulation studies  
- Extensive comparison against **LinearGAM** from the `pygam` package across many experimental settings

---

## ✨ Key Contents

### Jupyter Notebook
- **`spline_tree.ipynb`** — Main notebook containing:
  - Implementation of the TreeSpline model and its variants  
  - Data-generation utilities for correlated and uncorrelated feature scenarios  
  - Experimental comparisons with GAM and polynomial baselines  
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
TreeSpline/
├── spline_tree.ipynb        # Main research notebook: models, simulations, comparisons
├── nparrs/                  # Stored NumPy arrays for the result history of experiments
└── README.md                # Project description
```

---

## 🧪 Experiments & Evaluation

The project includes several controlled simulation environments, designed to compare TreeSpline to classic GAM approaches.

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

These experiments reveal strengths and limitations of TreeSpline across regimes and help identify the variants with the best empirical performance.

---

## 🎯 Research Context

This repository is part of an ongoing research project on **hybrid statistical–machine learning models**, combining interpretability of GAMs with flexibility of tree-based partitioning.  
It aims to provide:

- A reproducible benchmarking framework  
- A foundation for publishing TreeSpline as a novel modeling approach  
- Insight into how structural partitioning improves spline-based regression  

---

## 🚀 Goals & Future Work
- Refinement of TreeSpline variants with adaptive leaf modeling  
- Formal theoretical analysis  
- Integration with `sklearn`-style API for broader usability  
- Expanded benchmarking on real datasets  

---

If you’d like to enhance this README, I can add:
- Example usage code  
- Diagrams explaining the method  
- A “How to run the experiments” section  
- Badges (e.g., Python version, license, etc.)
