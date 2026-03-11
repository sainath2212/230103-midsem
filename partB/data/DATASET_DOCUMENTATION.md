# Dataset Documentation

## Checkerboard Dataset (Synthetic)

**What:** A 2D binary classification dataset where positive and negative classes are arranged in a checkerboard (grid) pattern. This creates a complex, non-linear decision boundary that cannot be captured by a linear classifier.

**How it is generated:** Using a custom function that divides the 2D unit square into a grid of cells, alternating class labels. Points are sampled uniformly within each cell and assigned the corresponding label.

**Parameters:**
- `n_samples`: Number of data points (default: 2000)
- `grid_size`: Number of divisions per axis (default: 4, creating a 4×4 checkerboard)
- `noise`: Standard deviation of Gaussian noise added to features (default: 0.0)
- `random_state`: Seed for reproducibility (default: 42)

**Why this dataset:**
The paper (Wang et al., JMLR 2012) uses the Checkerboard dataset extensively in their experiments (Section 7, Tables 3–6, Figures 2, 4–6). It is a standard synthetic benchmark for kernel SVM methods because:
1. The non-linear decision boundary requires a kernel (e.g., RBF) to achieve good separation.
2. The structured pattern allows controlled evaluation of how well a model captures complex boundaries.
3. Different grid sizes can increase or decrease classification difficulty.

**Limitations compared to the paper's dataset:**
- The paper uses up to 10 million Checkerboard examples; we use ~2000 for CPU feasibility.
- The paper also evaluates on 14 other datasets (USPS, Letter, Covertype, etc.); we focus on Checkerboard only.

**Usage in notebooks:**
- `task_2_1.ipynb`: Dataset generation and preprocessing
- `task_2_2.ipynb`: BPegasos implementation and training
- `task_2_3.ipynb`: Results and comparison
- `task_3_1.ipynb`: Ablation experiments
- `task_3_2.ipynb`: Failure mode analysis (with modified parameters)
