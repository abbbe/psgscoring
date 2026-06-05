# Binder launch — SpO2 / HB diagnostics notebook

Click the badge below to open `spo2_hb_diagnostics.ipynb` in a
fresh Jupyter environment running in the cloud. No install required.

[![Launch in Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/abbbe/psgscoring/feat/golden-hb-by-method?urlpath=lab/tree/binder/spo2_hb_diagnostics.ipynb)

First launch builds the Docker image and takes 2–5 minutes. After
that it caches for a few hours and starts in seconds. Sessions time
out at ~10 min idle, hard-limit ~1 hr.

## What's in this folder

| File | Role |
|---|---|
| `spo2_hb_diagnostics.ipynb` | The notebook — interactive view of psgscoring's HB pipeline on the 6 synthetic golden cases. |
| `requirements.txt` | Python dependencies pulled by Binder before the notebook runs. |
| `postBuild` | Editable install of the local `psgscoring` package after `requirements.txt` is processed. |
| `runtime.txt` | Pins the Python version Binder uses (3.11). |

## Running locally instead

The notebook is location-agnostic — it walks parents until it finds
the `psgscoring` package. To run from your own checkout:

```sh
pip install -e . -r binder/requirements.txt
jupyter lab binder/spo2_hb_diagnostics.ipynb
```

## Updating the badge URL

The badge above points to a specific branch (`feat/golden-hb-by-method`).
When the branch is merged or renamed, change `feat/golden-hb-by-method`
in the badge URL to the target branch (e.g. `main`). Same for the
notebook path if the file moves.

## Notes

- Binder's filesystem is ephemeral — visitor edits are lost when the
  session closes. The "Download" button in JupyterLab saves a local
  copy.
- Cold-start performance is dominated by `mne`'s install. If you want
  faster launches, pin a wheel-only build of `mne` in
  `requirements.txt`.
