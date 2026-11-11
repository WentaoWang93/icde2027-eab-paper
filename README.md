# Maintaining Prediction Models After Policy Updates

Reproducibility materials for **Maintaining Prediction Models After Policy Updates: Evaluating and Verifying Monetary Input Adjustments** (Experiment, Analysis, and Benchmark).

Authors: Wentao Wang and Faguo Wu, Beihang University.
Contact: wentaowang93@buaa.edu.cn; faguo@buaa.edu.cn.

## Download the complete artifact

Open this repository's **Releases** page and download **all five** archives, `Policy_Update_Artifact_Part1.zip` through `Policy_Update_Artifact_Part5.zip` from release `artifact-v1`. The small repository source download is not the complete data package. The full archive contains the code, retained input data and source documents, prediction arrays, experimental plans, timestamp evidence, and numerical results.

Extract all five archives into the same directory, merging their `policy-update-artifact/` folders. Then:

```bash
cd policy-update-artifact/artifact
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements_all.txt
python code/verify_manifest.py
bash run_all.sh
```

Use Python 3.12 on Linux, with OpenSSL and g++ supporting OpenMP. Python package versions are pinned in `requirements.txt`; the recorded environment is in `ENVIRONMENT.json`. The default script recomputes released-score analyses and checks retained raw-data/refit evidence. `bash run_all.sh --full` additionally reruns model fits and requires substantially more computation. Read the original artifact README for each verification command's scope.

For a shorter score-level check:

```bash
python code/replay_synthesis_reading_package.py
```

This shorter check covers 315 historical cells, not the entire 350-cell inventory. It does not reconstruct raw source data or rerun model training. `VALIDATION.txt` records the checks performed during packaging and their limits.

## Contents

| Path | Contents |
| --- | --- |
| `paper/main.pdf` | Submission manuscript |
| `artifact/code/` | Data adapters, repair methods, analysis and verification scripts |
| `artifact/locked_experiments/`, `development/`, `decade/`, `osha2024/` | Original experiments and retained development analyses |
| `artifact/extension/`, `hmda/`, `hmda_expansion/`, `history_validation/` | Model, endpoint, mortgage and taxi extensions |
| `artifact/synthesis/`, `new_early_updates/` | Event-level synthesis, paired uncertainty, cross-fitting and early-year tests |
| `artifact/transfer_validation/`, `msha_validation/` | Transfer checks, mining data and sampled-label audits |
| `artifact/cost_validation/` | Exact-score reuse, timings and queried-label refinement |
| `artifact/protocols/`, `MANIFEST.json`, `DATA_PROVENANCE.md` | Historical plans, hashes and source/access records |

## Interpretation and provenance

The descriptive inventory comprises 350 cells sharing 37 agency-year updates and 19 source years. Cells are not independent policy events. The cost experiments reuse existing cohorts. Scientific failures and historical numerical corrections are retained.

Historical plans and source code are preserved byte-for-byte where bound by the original manifests and timestamps. They retain their original experiment identifiers and contemporaneous wording; they are not current submission instructions. Author information above supersedes historical author placeholders. No new preregistration or independent label custody is asserted by this packaging operation.

The auxiliary legal indicators are text-free derivatives. No licensed judgment text or login credentials are distributed. Their extraction from the original licensed corpus cannot be reproduced from the public indicators alone; see `artifact/DATA_PROVENANCE.md`. The main predictive benchmark uses the separate administrative datasets described in the manuscript.

The existing MIT license covers the software. Agency data and third-party documentation retain their own source terms; see `artifact/LICENSE`.
