# Binomial Parameter Estimation: Frequentist, Bayesian and MCMC

A single notebook that estimates the success probability $p$ of a binomial from $k = 2$ successes in $n = 10$ trials, using three approaches:

1. **Frequentist Wilson score interval**, plus a coverage simulation: fix $p_{\text{true}}$, simulate many datasets, and check that about 95% of the intervals contain $p_{\text{true}}$.
2. **Conjugate Bayesian posterior**: a flat $\text{Beta}(1, 1)$ prior gives a $\text{Beta}(3, 9)$ posterior. A generative (rejection-sampling) simulation confirms the result.
3. **MCMC**: a random-walk Metropolis-Hastings sampler, checked against the analytical posterior.

Notebook: [`binomial_parameter_estimation_frequentist_bayesian_mcmc.ipynb`](binomial_parameter_estimation_frequentist_bayesian_mcmc.ipynb)

## Setup

Requires [uv](https://docs.astral.sh/uv/) (or use `python -m venv` and `pip`).

```bash
uv venv .venv
uv pip install --python .venv/bin/python -r requirements.txt
.venv/bin/python -m ipykernel install --user --name binomial-mcmc --display-name "Python (binomial-mcmc)"
```

## Running

- **VS Code:** open the folder, open the notebook, and select the `.venv` kernel (the workspace settings point to it), then **Run All**.
- **JupyterLab:** `.venv/bin/jupyter lab`
