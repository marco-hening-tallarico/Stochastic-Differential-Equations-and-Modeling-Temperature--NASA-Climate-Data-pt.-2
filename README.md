# Stochastic Differential Equations and Temperature — NASA Climate Data (pt. 2)

This repository explores the Ornstein–Uhlenbeck (OU) stochastic process as a simple model for temperature dynamics, using NASA climate datasets as observations. The work is implemented in Python within Jupyter Notebook(s) and demonstrates parameter estimation, simulation, and comparison between model realizations and observed temperature time series.

## Table of contents
- [Project goals](#project-goals)
- [What’s included](#whats-included)
- [Getting started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Quick start](#quick-start)
- [Usage](#usage)
- [Data sources](#data-sources)
- [Methodology (brief)](#methodology-brief)
- [Reproducing results](#reproducing-results)
- [Suggested requirements](#suggested-requirements)
- [Citation](#citation)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Project goals
- Demonstrate how the Ornstein–Uhlenbeck process can be used to model mean-reverting temperature anomalies.
- Estimate OU parameters (mean reversion rate, long-term mean, volatility) from NASA climate data.
- Simulate OU trajectories and compare them to observed temperature series.
- Provide notebooks and code suitable for teaching, experimentation, and reproducible analysis.

## What’s included
- Jupyter Notebook(s) implementing:
  - Data ingestion and preprocessing
  - Parameter estimation for the OU process
  - Simulation and visualization of model realizations
  - Comparison with NASA temperature observations

(Notebook filenames and exact structure are in the repository — open the notebooks to explore each step.)

## Getting started

### Prerequisites
- Git
- Python 3.8+ recommended
- Jupyter (or JupyterLab)

### Quick start
Clone the repository:
```bash
git clone https://github.com/marco-hening-tallarico/Stochastic-Differential-Equations-and-Modeling-Temperature--NASA-Climate-Data-pt.-2.git
cd Stochastic-Differential-Equations-and-Modeling-Temperature--NASA-Climate-Data-pt.-2
```

Create and activate a virtual environment (optional but recommended):
```bash
python -m venv venv
# on macOS / Linux
source venv/bin/activate
# on Windows (PowerShell)
venv\Scripts\Activate.ps1
```

Install dependencies (if `requirements.txt` is present):
```bash
pip install -r requirements.txt
```
Or install the likely dependencies directly:
```bash
pip install numpy scipy pandas matplotlib jupyter notebook xarray netCDF4
```

Start Jupyter:
```bash
jupyter notebook
# or
jupyter lab
```
Open the main notebook(s) and run the cells.

## Usage
- Follow the notebook(s) to:
  - Load and preprocess NASA temperature data
  - Estimate OU model parameters from the time series
  - Simulate sample paths from the fitted OU model
  - Compare simulations and diagnostics with observed data (plots, residuals)

Tips:
- Use smaller time ranges for quick iterations.
- If working with large NetCDF datasets, consider using xarray for convenient I/O and resampling.

## Data sources
This project uses publicly available NASA climate/temperature datasets. Common NASA sources include:
- NASA GISS Surface Temperature (GISTEMP): https://data.giss.nasa.gov/gistemp/
- NASA Earthdata: https://earthdata.nasa.gov/

If the notebooks download data automatically, be aware that some NASA services require registration or API tokens. Check the notebook cells for download instructions or local data file expectations.

## Methodology (brief)
- The Ornstein–Uhlenbeck (OU) process is a mean-reverting stochastic differential equation often written as:
  dX_t = θ(μ − X_t) dt + σ dW_t
  where θ is the rate of mean reversion, μ the long-term mean, σ the volatility, and W_t a Wiener process.
- Parameter estimation is typically done via maximum likelihood on discretely observed data or via method-of-moments (e.g., using lagged covariances).
- After estimating θ, μ, σ, the model is simulated to produce sample trajectories for visual and statistical comparison with observations.

## Reproducing results
1. Ensure required Python packages are installed.
2. Open the notebook(s) in Jupyter and run all cells in order.
3. If any external data download steps are included, confirm the downloaded files exist or provide local paths where the notebook expects data.
4. For deterministic outputs, set random seeds where the notebooks perform stochastic simulations.

## Suggested requirements
Below is a minimal requirements list you can place in `requirements.txt`:

```text
numpy
scipy
pandas
matplotlib
jupyter
xarray
netCDF4
```

Add any extra libraries used in your notebooks (e.g., seaborn, statsmodels, dask) as needed.

## Citation
If you use this repository or the notebooks in your work, please cite:
- Uhlenbeck, G. E., & Ornstein, L. S. (1930). On the theory of Brownian motion. Physical Review, 36(5), 823–841.
- This repository: marco-hening-tallarico/Stochastic-Differential-Equations-and-Modeling-Temperature--NASA-Climate-Data-pt.-2 (GitHub).

## Contributing
Contributions, issues, and feature requests are welcome.
- Suggestions: open an issue describing the change or improvement.
- Code contributions: fork the repository, create a branch, add changes, and open a pull request.
- Add a `requirements.txt` and `LICENSE` if you want to make the project easier for others to reuse.

## License
No license file is included by default. If you want this project to be reusable, consider adding a LICENSE (e.g., MIT). Without a license, reuse is limited. To use the MIT license, add a `LICENSE` file containing the MIT license text.

## Contact
Maintainer: [marco-hening-tallarico](https://github.com/marco-hening-tallarico)

---

If you'd like, I can:
- Create and commit a `README.md` file to the repository,
- Draft a `requirements.txt` with exact pinned versions,
- Add a `LICENSE` file (e.g., MIT),
- Or open a pull request with these changes. Tell me which you'd like next.
