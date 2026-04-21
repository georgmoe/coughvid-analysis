---
name: notebook-data-analysis-setup
description: 'Set up a reproducible VS Code data analysis notebook workflow. Use when creating a new analysis notebook, preparing Python environments with venv and pip, loading datasets, structuring exploratory analysis, or adding quality checks before sharing results.'
argument-hint: 'Goal and data source (VS Code-only notebook setup with venv + pip)'
user-invocable: true
disable-model-invocation: false
---

# Notebook Data Analysis Setup

## What This Skill Produces
A ready-to-run notebook setup with:
- A VS Code-only notebook workflow
- A validated Python environment and kernel
- A starter notebook structure for loading, profiling, cleaning, and visualizing data
- Basic reproducibility and quality checks

## When to Use
Use this skill when you need to:
- Start a new data analysis notebook quickly
- Make sure notebook execution is stable and reproducible
- Avoid environment and kernel mismatch issues
- Prepare analysis that is easy to rerun and share

## Inputs To Gather
Collect these before setup:
- Analysis goal and expected output (EDA, model prep, reporting)
- Dataset path or source (local file, folder, URL, DB extract)
- Python environment strategy (existing venv or create new)
- Key libraries needed (for example pandas, numpy, matplotlib, seaborn, plotly, scikit-learn)

## Decision Flow
1. Choose environment strategy:
- If project already has a working environment, reuse it.
- If environment is missing or broken, create a new isolated environment.

2. Choose data loading path:
- If dataset is local, validate path and sample-read first rows.
- If remote, validate connectivity and cache to a local data folder.

3. Choose output expectations:
- If exploratory only, prioritize profiling and quick plots.
- If handoff/reporting, add markdown narrative and deterministic execution checks.

## Procedure
1. Confirm scope and constraints
- Record goal, timeline, and expected deliverables.
- Confirm data availability and size constraints.

2. Prepare environment
- Create or select Python `venv` environment.
- Install core notebook packages and required analysis libraries.
- Register/select the correct kernel for the notebook.

3. Initialize notebook skeleton
- Add sections in this order:
  1. Title and analysis objective
  2. Imports and display settings
  3. Config and paths
  4. Data load
  5. Data quality checks
  6. Exploratory analysis and visualizations
  7. Summary and next steps

4. Add robust data loading cell
- Validate file paths.
- Load a small preview first.
- Print row/column counts, dtypes, and missing-value summary.

5. Add baseline quality checks
- Check duplicates, null rates, and suspicious ranges.
- Document assumptions directly in markdown cells.

6. Add exploratory visuals
- Start with distribution, correlation, and target-specific plots.
- Keep plotting code deterministic and labeled.

7. Reproducibility pass
- Run all cells top-to-bottom on a clean kernel.
- Ensure no hidden state dependencies.
- Ensure outputs and markdown conclusions are aligned.

8. Share-ready cleanup
- Remove dead code and noisy debug outputs.
- Keep only meaningful cells and concise commentary.

## Completion Criteria
A setup is complete when all are true:
- Notebook runs end-to-end without manual intervention.
- Environment and kernel are clearly identified.
- Data source and key assumptions are documented.
- Core EDA outputs are present and interpretable.
- Next analytical steps are explicitly listed.

## Common Failure Modes
- Kernel points to wrong environment.
- Notebook relies on state from out-of-order execution.
- Data path hard-coded to machine-specific absolute paths.
- Missing dependency pinning causes non-reproducible runs.

## Quick Prompt Examples
- /notebook-data-analysis-setup Set up a VS Code-only notebook for CSV-based EDA on customer churn data.
- /notebook-data-analysis-setup Configure a new environment and notebook structure for time-series sensor analysis.
- /notebook-data-analysis-setup Prepare a reproducible notebook for a graded university analysis assignment.
