# Triadic macrostates and community evolution in temporal networks

Code and results for:

> Chandrika V., Nair L. S., Davis N. *Higher-order triadic structure adds no predictive signal beyond mean reversion in the evolution of network communities.* (submitted)

Every number in the paper is produced by the two notebooks below from the raw, public SNAP files. Nothing is hard-coded.

## Contents

| Path | What it is |
|---|---|
| `notebooks/01_main_pipeline_v3.ipynb` | Full pipeline: downloads 8 SNAP networks, builds sliding-window snapshots, detects and tracks communities, computes triadic macrostates, selects windows by an outcome-blind yield rule, and runs purged rolling-origin evaluation, ablation, SHAP, mechanism tests M1–M4, HMM regimes, survival, RF vs LSTM, cross-network transfer, random-effects meta-analysis and robustness sweeps. |
| `notebooks/02_diagnostics_v3_1.ipynb` | Exploratory diagnostics (run after notebook 01): mean reversion of size changes, label reliability across Louvain seeds, seed-averaged reversal, and a two-variable mean-reversion model. |
| `results/main/` | All tables (`table_*.csv`) and run metadata written by notebook 01 for the reported run. |
| `results/diagnostics/` | Diagnostics output (notebook 02). |

## How to reproduce

1. Open a notebook in Google Colab (`File → Upload notebook`) and choose **Runtime → Change runtime type → CPU**.
2. Run **Runtime → Run all**. Notebook 01 takes about 1.5–3 h; notebook 02 takes about 45 min.
3. Each notebook writes its results to a folder (`results_macrostates/` and `results_diagnostics/`) and offers a zip download.

Set `SYNTHETIC_SMOKE_TEST = True` in the first code cell to check the whole pipeline in a few minutes on synthetic networks, with no downloads.

Locally: `pip install -r requirements.txt`, then run the notebooks with Jupyter.

## Data

All networks are public, from the Stanford Large Network Dataset Collection (https://snap.stanford.edu/data): email-Eu-core-temporal, CollegeMsg, soc-sign-bitcoinotc, soc-sign-bitcoinalpha, sx-mathoverflow, soc-redditHyperlinks (body and title), sx-askubuntu, sx-superuser. The notebooks download them automatically.

## Citation

Please cite the paper above (and this archive's Zenodo DOI) if you use this code.
