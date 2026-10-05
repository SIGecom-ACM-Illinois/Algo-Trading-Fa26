# Algo-Trading-Fa26

SIGecom @ Illinois algo-trading project, Fall 2026. We build and test trading strategies in Python using [Alpaca](https://alpaca.markets) paper trading accounts (simulated money, real market data).

**New here?** Follow the setup steps below, then open [`alpaca_paper_trading_intro.ipynb`](alpaca_paper_trading_intro.ipynb). It walks you through creating your Alpaca paper account and placing your first trades.

> **Just want to try it in your browser?** You can skip installing anything and run the notebook in Google Colab. See [Option C](#option-c-google-colab-no-install).

---

## 1. Install the tools

You need three things: **Git**, **Python 3.9 or newer**, and an editor. We recommend **VS Code**.

### Git
Download it from **https://git-scm.com/downloads** and install with the default options.
Check it worked by running this in a terminal:
```bash
git --version
```

### Python
Download it from **https://www.python.org/downloads/**.
- **Windows:** on the first screen of the installer, check **"Add python.exe to PATH"** before you click Install.
- **macOS:** the python.org installer works well. After installing, use `python3` wherever this README says `python`.

Check it worked:
```bash
python --version
```

### VS Code (recommended)
VS Code is a free editor that runs Jupyter notebooks, manages Python environments, and has Git built in, so you can do everything for this project in one place.

1. Follow the official download and setup guide for your OS: **https://code.visualstudio.com/docs/setup/setup-overview**
   - Direct download page: https://code.visualstudio.com/download
2. Open VS Code, go to the **Extensions** panel (`Ctrl+Shift+X`, or `Cmd+Shift+X` on Mac), and install:
   - **Python** (by Microsoft)
   - **Jupyter** (by Microsoft)

New to Python in VS Code? Microsoft's [Python tutorial](https://code.visualstudio.com/docs/python/python-tutorial) is a good 10-minute intro.

> Prefer another editor? PyCharm, or JupyterLab in the browser (see [Option B](#option-b-jupyterlab-in-the-browser)), works fine too.

---

## 2. Clone the repo

"Cloning" downloads a copy of the repository to your computer and keeps it connected to GitHub, so you can pull updates later.

### Option A: from VS Code
1. Open VS Code and press `Ctrl+Shift+P` (`Cmd+Shift+P` on Mac) to open the Command Palette.
2. Type **Git: Clone** and press Enter.
3. Paste this URL:
   ```
   https://github.com/SIGecom-ACM-Illinois/Algo-Trading-Fa26.git
   ```
4. Pick a folder to save it in, then click **Open** when VS Code asks.

### Option B: from a terminal
```bash
cd path/to/where/you/keep/projects
git clone https://github.com/SIGecom-ACM-Illinois/Algo-Trading-Fa26.git
cd Algo-Trading-Fa26
code .   # opens the folder in VS Code (optional)
```

### Getting updates later
When new material is added, run this from inside the repo folder (or use **Source Control → Pull** in VS Code):
```bash
git pull
```

---

## 3. Set up a Python environment

A **virtual environment** keeps this project's packages separate from everything else on your computer. Run these from inside the `Algo-Trading-Fa26` folder. In VS Code you can open a terminal with ``Ctrl+` `` (backtick).

**Windows (PowerShell):**
```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```
> If PowerShell says running scripts is disabled, run `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned` once, then try activating again.

**macOS / Linux:**
```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

You'll see `(.venv)` at the start of your terminal prompt when the environment is active.

### Add your Alpaca keys
Copy `.env.example` to a new file named `.env` and paste in your Alpaca **paper** API keys. The intro notebook explains how to get them. `.env` is git-ignored, so **never** rename it or commit it.

---

## 4. Using Jupyter notebooks

A Jupyter notebook (`.ipynb`) mixes **text cells** (explanations) and **code cells** (Python you can run one piece at a time). Variables stick around between cells, which makes notebooks great for exploring data and trying ideas step by step.

### Option A: in VS Code (recommended)
1. Open `alpaca_paper_trading_intro.ipynb` from the Explorer sidebar.
2. Click **Select Kernel** in the top-right corner, choose **Python Environments**, and pick the one ending in **`.venv`**.
3. Run a cell by clicking the ▶ next to it or pressing **`Shift+Enter`** (runs the cell and moves to the next one).
4. Use **Run All** in the toolbar to run everything top to bottom, or **Restart** to clear all variables and start fresh.

More detail: [Jupyter notebooks in VS Code](https://code.visualstudio.com/docs/datascience/jupyter-notebooks).

### Option B: JupyterLab in the browser
With your virtual environment active:
```bash
pip install jupyterlab
jupyter lab
```
A browser tab opens. Double-click the notebook in the file list on the left. Run cells with `Shift+Enter`.

### Option C: Google Colab (no install)
[Google Colab](https://colab.research.google.com) runs notebooks in your browser on Google's servers, for free, with just a Google account. You can skip sections 1–3 entirely.

1. Download the notebook: on GitHub, open [`alpaca_paper_trading_intro.ipynb`](alpaca_paper_trading_intro.ipynb) and click the **Download raw file** button (the ⬇ icon at the top right of the file view).
2. Go to **https://colab.research.google.com**, then choose **File → Upload notebook** and select the file you downloaded.
3. Run cells with `Shift+Enter` or the ▶ button. The first code cell installs the packages for you.
4. There's no `.env` file in Colab. When the notebook asks for your **API Key ID** and **Secret Key**, paste them into the prompt boxes. They aren't saved in the notebook.

New to Colab? Start with Google's [Welcome to Colab](https://colab.research.google.com/notebooks/intro.ipynb) tutorial notebook.

> **Colab notes:** your copy is saved to your Google Drive (in a `Colab Notebooks` folder), not to this repo, so re-download notebooks from GitHub when new material is posted. Colab also disconnects after a period of inactivity, which clears your variables, so just re-run the cells from the top.

### Notebook tips
- **Run cells in order.** A cell can depend on variables created by earlier cells. If you get a `NameError`, you probably skipped one.
- **`[*]` next to a cell** means it's still running. A number like `[5]` means it finished.
- **Stuck or confused state?** Restart the kernel and run all cells from the top.
- **Your own experiments:** make a copy of a notebook (e.g. `intro_yourname.ipynb`) before editing heavily, so `git pull` doesn't conflict with your changes.

---

## Repo contents

| File | What it is |
|---|---|
| `alpaca_paper_trading_intro.ipynb` | Start here: Alpaca paper account setup and API basics |
| `requirements.txt` | Python packages for the project |
| `.env.example` | Template for your Alpaca API keys (copy it to `.env`) |
