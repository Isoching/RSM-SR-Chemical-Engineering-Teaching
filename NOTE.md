# Teaching notes: RSM and SR in chemical engineering

## What is included

This teaching collection pairs four self-contained Jupyter notebooks with a written modelling guide and a lecture deck. The notebooks move from a local polynomial response surface to increasingly structured equation searches. The Word guide explains the four notebook cases in more depth. The slide deck provides a broader symbolic regression lecture using a Peaks function and a conceptual green-methanol process; it is complementary to the four notebook exercises.

| File | Level and method | Main question |
| --- | --- | --- |
| [01_RSM_Batch_Esterification.ipynb](01_RSM_Batch_Esterification.ipynb) | Introductory RSM | Which temperature, alcohol-to-acid ratio, and catalyst loading improve fixed-duration batch yield? Fits and checks a quadratic surface, then verifies a recommended point against the teaching generator. |
| [02_RSM_Selective_CSTR.ipynb](02_RSM_Selective_CSTR.ipynb) | Advanced RSM | How do desired-product yield and reactor productivity trade off? Fits a concentration surrogate, derives related outputs from physical identities, and examines a finite sampled Pareto set. |
| [03_SR_Pipe_Pressure_Loss.ipynb](03_SR_Pipe_Pressure_Loss.ipynb) | Introductory SR | Which multiplicative relation describes pressure loss for a specified viscous-flow setting? Searches 729 supplied integer-exponent structures and fits a coefficient for each. |
| [04_SR_Humid_CO2_Adsorption.ipynb](04_SR_Humid_CO2_Adsorption.ipynb) | Advanced SR | Which supplied equilibrium and transient forms describe CO₂ uptake in humid gas? Fits and compares 18 physical templates and tests held-out operating conditions. |
| [RSM_SR_Chemical_Engineering_Modelling_Guide.docx](RSM_SR_Chemical_Engineering_Modelling_Guide.docx) | Companion guide | Definitions, assumptions, worked results, limitations, and teaching questions for the four cases. |
| [Symbolic_Regression_Chemical_Engineering_Teaching.pptx](Symbolic_Regression_Chemical_Engineering_Teaching.pptx) | Lecture slides | Formula search, validation, a restricted-library Peaks example, and system-level reasoning for green methanol. |

## Suggested learning path

1. Read the introductory RSM notebook to see how a specified polynomial family is fitted, validated, and used to recommend an operating point.
2. Work through the CSTR case to see why linked outputs and engineering objectives require more than a high overall fit score.
3. Compare that with the pipe case, where the candidate *structure* is selected from a restricted equation grammar.
4. Use the adsorption case to discuss nonlinear fitting, whole-condition data splits, physical limits, and extrapolation.
5. Use the guide for derivations and interpretation. Use the slides to introduce broader SR concepts and process-level verification.

## Running the notebooks

Each `.ipynb` is designed to run in Google Colab: upload the notebook, use a CPU runtime, and choose **Runtime → Run all**. Save your own copy before making changes. The core exercises generate their data inside the notebook and need no external dataset, process simulator, API key, GPU, or Julia installation. Their setup cells check Python dependencies and install missing packages when needed. The two SR notebooks include a separate **optional** PySR extension; that extension may need additional setup and is not part of the core run.

Saved outputs make the worked editions readable without rerunning them. To retain your edits and newly generated results, download both the edited notebook and its exported results archive before leaving a temporary runtime.

## How to interpret the results

- All numerical chemical parameters and observations in the notebooks are teaching assumptions. They are not experimental or plant data.
- RSM coefficients describe the stated local operating domain. A symbolic expression is likewise supported only over its tested domain and under its stated assumptions.
- Training fits numerical constants; validation selects a model or structure; untouched test data assess the frozen choice. Any separate challenge set reports extrapolation and should be discussed separately from in-domain performance.
- The two core SR exercises use restricted candidate sets. Their results should not be presented as evidence that unrestricted genetic programming or PySR recovered a law.
- Check physical bounds, units, conservation, numerical stability, and the original model or new observations before using an equation to make an engineering decision.

## Rights and use

The companion guide states: © 2026 Yuanjing Zhao, University of Surrey. All rights reserved; teaching use only. This repository does not provide an open-source license. Contact the rights holder before redistribution or adaptation beyond the permissions already available to you.
