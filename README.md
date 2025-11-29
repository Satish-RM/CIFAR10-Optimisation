# CIFAR-10: Gradient vs Metaheuristics vs Multi-Objective (COMM062)

**Goal.** Compare a CNN baseline to gradient-free optimisation on the last layer (PSO, DE) and a multi-objective trade-off (NSGA-II), under fair evaluation budgets.

**Highlights**
- Reproducible splits and cached features (no test leakage).
- Comparable evaluation budgets across optimisers (e.g., 1,500 evals each).
- Read-only reporting notebook that generates the figures and tables used in the report.

## Quickstart (Colab or local)
- Open `notebooks/01_baseline.ipynb` and run all. It trains the full CNN and the last-layer GD baseline; caches features to `./cache/`.
- `02_pso.ipynb` and `03_de.ipynb` run PSO/DE on the frozen last layer.
- `04_nsga2.ipynb` runs NSGA-II (accuracy vs weight norm) and saves the Pareto front.
- `05_reporting.ipynb` is read-only: loads artefacts and produces `results/*.png` and `results/summary_metrics.csv`.

## Repo map
- `notebooks/` — main workflow (clean, step-by-step).
- `results/` — small, human-readable artefacts for the report (kept in git).
- `cache/`, `checkpoints/` — heavy artefacts (ignored).
- `docs/` — outline, experiments log, and figure mapping.
- `tests/` + `ci.yml` — smoke tests to keep the project tidy.

## Reproducibility
- Fixed seed (`SEED=1337`), fixed train/val/test protocol.
- Evaluation budgets: PSO/DE count each fitness call, including initial population.

## License
MIT
