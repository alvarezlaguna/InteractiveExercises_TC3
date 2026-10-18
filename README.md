# Interactive Kinetic Theory — Course Notebooks

A collection of interactive Jupyter notebooks for a course on the **kinetic theory
of plasmas**. Each notebook takes one problem, states it, and lets you *play* with the
relevant distribution functions: choose the species, temperature, density and drift
velocity and watch every curve respond.

## Contents

| Notebook | Topic |
|----------|-------|
| [`notebooks/01_drifting_maxwellian.ipynb`](notebooks/01_drifting_maxwellian.ipynb) | The drifting Maxwellian: two-term expansion, speed / energy / probability distributions |

More notebooks will be added following the same structure.

---

## Requirements

* [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or
  [Anaconda](https://www.anaconda.com/download) (or `mamba` / `micromamba`).
* A working internet connection for the first environment creation (packages are
  downloaded once and cached afterwards).

Everything else (Python, JupyterLab, NumPy, SciPy, Matplotlib, ipywidgets) is
installed automatically from `environment.yml`.

---

## Installation

The commands are identical on every platform; only the terminal differs.
Run them **from the repository root** (the folder that contains `environment.yml`).

### Linux / macOS

Open a terminal, then:

```bash
# 1. create the environment (only once)
conda env create -f environment.yml

# 2. activate it
conda activate ktic-interactive

# 3. launch JupyterLab
jupyter lab
```

If you use `mamba` (faster solver), simply replace `conda` with `mamba`:

```bash
mamba env create -f environment.yml
mamba activate ktic-interactive
```

### Windows

Open the **"Anaconda Prompt"** (or **"Miniconda Prompt"**) from the Start menu —
*not* the plain Command Prompt — so that `conda` is available.
`cd` into the repository folder, then run exactly the same commands:

```bat
:: 1. create the environment (only once)
conda env create -f environment.yml

:: 2. activate it
conda activate ktic-interactive

:: 3. launch JupyterLab
jupyter lab
```

Using **PowerShell** instead of the Anaconda Prompt? First enable conda for
PowerShell once:

```powershell
conda init powershell
```

Then close and reopen PowerShell and use the same commands as above.

> Tip (Windows): if you get an error that `conda` is not recognized, make sure you
> are in the Anaconda/Miniconda Prompt (or that `conda init` has been run for your shell),
> and that the Miniconda/Anaconda `Scripts` folder is on your `PATH`.

---

## Using the notebooks

1. `jupyter lab` opens a browser tab. In the file browser on the left, open the
   `notebooks/` folder and double-click a notebook.
2. Make sure the kernel (top-right of the notebook) is **ktic-interactive**.
3. Run the cells from top to bottom (`Run` ▸ `Run All Cells`).
4. Move the sliders — every figure below updates automatically.

The interactive widgets rely on `ipywidgets`. With the pinned versions from
`environment.yml` (ipywidgets ≥ 8) **no manual JupyterLab extension install is needed**.

---

## Updating or removing the environment

```bash
# update to match a modified environment.yml
conda env update -f environment.yml --prune

# remove it completely
conda env remove -n ktic-interactive
```

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| Widgets don't show up, or show `HBox(...)` as text | Make sure the notebook is using the `ktic-interactive` kernel and that `ipywidgets` is installed in that environment (`conda list ipywidgets`). |
| `conda: command not found` on Windows | Use the **Anaconda Prompt**, or run `conda init powershell` and reopen the shell. |
| Plots don't appear | Run the setup cells first (they contain the imports), then re-run the plotting cell. |
| Using VS Code instead of JupyterLab | Select the **ktic-interactive** environment as the notebook kernel (top-right kernel picker). |
