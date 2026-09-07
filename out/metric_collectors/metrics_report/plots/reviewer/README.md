# Final reviewer figures

These figures are generated directly from a collector output directory. Collector validation must be `PASS`, and rows are admitted only when normalized absolute `source_path` exactly matches an accepted manifest `metric_path`.

## Figures 1 and 2: Macro and support-weighted performance

All classification scores use `known-population-open-set-v1`. Precision, F1, recall, and one-vs-rest balanced accuracy use all valid truth events, including ungated background. Macro averages include only truth-present biological populations; weighted averages use their biological truth support. Cells show arithmetic means across accepted effective folds with a defined score for that metric, retaining zero scores and returning NA if none are defined. Labels show n = metric-specific defined/completed folds and c = completed/expected folds; undefined scores do not remove completion credit. Source TSVs report defined_fold_count separately from completed_case_count and expected_effective_case_count. Support-weighted recall measures biological recovery and is not full-event accuracy, which also credits correctly rejected background.

## Figure 3: Model-rejection event rate

The sum of `n_pred_zero_on_truth_positive` divided by the sum of `n_truth_positive` across accepted effective folds, using `run_metrics.tsv` directly.

## Figure 4: Completion coverage

Accepted effective cases divided by all requested effective cases derived from run status, including explicit `not_run` cases.

## Figure 5: Rare-population F1

Open-set per-population F1 for `<1%` and `1-5%` test-support buckets, split by training representation. Prevalence uses biological truth support, not the background-inclusive scoring denominator. Every qualifying accepted observation is retained as a jittered point; diamonds mark medians, labels show `n`, and violins require at least three observations.

## Figure 6: Represented-only sensitivity

Only population observations represented in their fold's training reference are retained. This is an observation-level filter and never removes an entire fold because another population was absent.

Accepted inputs: 1728 effective runs, 16 dataset parameterizations, 8 models, and 3 stratifications.

Each figure is saved as PDF, SVG, and 180 dpi PNG. Exact plotted data are in six source TSVs. Local assertions, dimensions, counts, input hashes, and output hashes are recorded in `validation-status.json`.
