# PMO isolation policy

Curated materials on isolation-policy analysis via branching-process
probability-of-major-outbreak (PMO) methodology.

## Contents

- **`current_work.ipynb`** — the current state of the analysis. Population-sampled PMO,
  transmission risk, excess isolation burden, and their extensions (partial compliance,
  acquisition-side susceptibility, asymptomatic transmission), all built on 1000 simulated
  patients rather than a median-trajectory approximation. Every equation is written out in
  LaTeX immediately before the cell that uses it, with the source PDF's equation numbers
  cross-referenced throughout.
- **`future_work.ipynb`** — four directions this could be extended in, explained in text with
  no code: viral-kinetics model choice, behavioural (contact-rate) heterogeneity on top of
  the existing biological heterogeneity, detection-timing and compliance heterogeneity, and
  moving from a fixed isolation policy to a stochastic controlled branching process.
- **`generate_pmo_presentation_figures.ipynb`** — generates the standalone slide figures
  (schematics and annotated re-exports) under `fig/pmo_presentation/`.
- **`docs/post_isolation_pmo_methodology.pdf`** — the Hart et al. (2023) PNAS methodology
  this project implements and extends.
- **`data/Singapore-population-2023.csv`** — SingStat table M810731, the real Singapore
  resident age pyramid used to sample the simulated population (from Ejima et al. 2025's
  supplementary material).

## Reproducing

```bash
conda activate mcmc311   # numpy, scipy, matplotlib, scienceplots
jupyter nbconvert --to notebook --execute --inplace current_work.ipynb
jupyter nbconvert --to notebook --execute --inplace generate_pmo_presentation_figures.ipynb
```

`future_work.ipynb` has no code cells and doesn't need running.

## How the two notebooks relate

`current_work.ipynb` is what's done and verified. `future_work.ipynb` is what's next: none of
it is implemented yet, and each avenue there names the specific model parameter it would
extend (several of which `current_work.ipynb`'s Summary already lists as currently locked).
