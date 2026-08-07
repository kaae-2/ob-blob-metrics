# Final reviewer figures

These figures are generated directly from a collector output directory. Collector validation must be `PASS`, and rows are admitted only when normalized absolute `source_path` exactly matches an accepted manifest `metric_path`.

## Figures 1 and 2: Macro and support-weighted performance

Arithmetic means across accepted effective folds for precision, F1, and recall. Macro recall equals balanced accuracy; support-weighted recall equals overall accuracy.

## Figure 3: Model-rejection event rate

The sum of `n_pred_zero_on_truth_positive` divided by the sum of `n_truth_positive` across accepted effective folds, using `run_metrics.tsv` directly.

## Figure 4: Completion coverage

Accepted effective cases divided by all requested effective cases derived from run status, including explicit `not_run` cases.

## Figure 5: Rare-population F1

Per-population F1 for `<1%` and `1-5%` test-support buckets, split by training representation. Every qualifying accepted observation is retained as a jittered point; diamonds mark medians, labels show `n`, and violins require at least three observations.

## Figure 6: Represented-only sensitivity

Only population observations represented in their fold's training reference are retained. This is an observation-level filter and never removes an entire fold because another population was absent.

Accepted inputs: 1728 effective runs, 16 dataset parameterizations, 8 models, and 3 stratifications.

Each figure is saved as PDF, SVG, and 180 dpi PNG. Exact plotted data are in six source TSVs. Local assertions, dimensions, counts, input hashes, and output hashes are recorded in `validation-status.json`.
