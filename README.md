# Adaptive-RBDO-KAMRO

An adaptive reliability-based design optimization (RBDO) framework built on a Kriging surrogate model. The implementation follows the paper:

> Yuecheng Shen, Baoping Cai, Chuntan Gao, Xintong Wang, Yinhang Zhang, Xinquan Jia. "An adaptive Kriging-assisted reliability-based design optimization framework with reliability assurance and high efficiency." *Mechanical Systems and Signal Processing*, Vol. 242, 2026, 113651. https://doi.org/10.1016/j.ymssp.2025.113651.

## Project structure
- `PCH_example4.py`: End-to-end adaptive RBDO workflow with interactive data entry and visualization utilities.
- `numercial_exampl1.ipynb`: Notebook illustrating the numerical example from the paper.
- `requirements.txt`: Python dependencies for running the examples.
- `LICENSE`: MIT license.

## Installation
1. Create and activate a Python 3.9+ environment.
2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

## Usage
### Run the adaptive RBDO example
Execute the main script to launch the adaptive Kriging-assisted RBDO loop. The script starts with 30 predefined experimental samples and will prompt for additional CFD simulation results when needed.

```bash
python PCH_example4.py
```

During execution, you will be asked to provide:
- `P_outlet` (Pa)
- `M_outlet` (kg/s)

The program caches all inputs so you can stop and resume without losing previously entered data. At the end of each iteration it reports the current design, reliability metrics (β, Pf), and plots iteration histories when available.

### Explore the notebook
Open `numercial_exampl1.ipynb` in JupyterLab/Notebook to review the numerical example step by step.

## Key features
- Adaptive gradient estimation with `numdifftools` for efficient sensitivity analysis.
- Kriging surrogate modeling via `GPy` with Latin Hypercube Sampling (`pyDOE2`) for initial designs.
- Reliability evaluation using AMV and Monte Carlo simulation.
- Interactive workflow suitable for coupling with external CFD solvers.

## Reproducibility tips
- Set matplotlib backend to a non-interactive option (e.g., `Agg`) if running on a headless server.
- Keep the interactive prompts responsive by providing physically consistent `P_outlet` and `M_outlet` values.

## Citation
If you use this repository in academic work, please cite the paper above.
