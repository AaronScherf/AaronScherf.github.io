---
title: Novel Omnibus Normality Test
summary: "Detect patterns in how data depart from a bell-shaped distribution, and compare the proposed test with Shapiro–Wilk in small-sample simulations."
date: 2026-08-22
lastmod: 2026-10-16
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/Novel-Omnibus-Normality-Test-and-Power-Comparison-with-the-Shapiro-Wilk-Test
  - type: pdf
    url: https://raw.githubusercontent.com/AaronScherf/Novel-Omnibus-Normality-Test-and-Power-Comparison-with-the-Shapiro-Wilk-Test/main/MATH_Final_Thesis.pdf
image:
  caption: 'Illustration of the power comparisons; the thesis contains the original simulation figures and conditions.'
tags:
  - Statistics
  - R
  - Mathematics
---

My mathematics thesis explored a way to test whether data depart from a bell-shaped, or normal, distribution. It transforms an ordered sample into a pattern of departures from what normal data would produce, then looks for structure beyond random fluctuation. The aim was to detect different kinds of departure through one flexible test.

<!--more-->

In the small-sample simulations, the method performed similarly to the established Shapiro–Wilk test for two families of distributions, but fell behind for two others. The result was a proof of concept with room to investigate the construction further. It did not establish a generally stronger normality test.

[[Insert Image: Replace the current illustrative four-panel montage with a readable crop of the thesis's actual power-comparison figures, or a chart recreated from its published simulation outputs using standard plotting tools. Prefer one panel where the methods are close and one where they differ, with large labels identifying the proposed PGLS test and Shapiro–Wilk. Preserve the original axes and values; do not generate synthetic scientific curves. Keep the existing featured asset until the replacement is approved. Suggested caption: "Similar performance in some tested distributions, lower detection rates in others: samples of 20 observations and 10,000 simulations per tested setting." Suggested alt text: "Two original simulation panels compare the proposed normality test with Shapiro–Wilk, showing that their relative performance depends on the tested distribution." Save the approved figure as featured.jpg or featured.png in this page bundle and remove this brief.]]

## Turning a sample into a pattern

An ordered sample contains information about where it departs from the expected shape. After the transformation, normal samples fluctuate around zero. Other distributions can produce a systematic bend or a different pattern of departures. Keeping their direction as well as their size is the useful part of the approach.

I fitted those departures with a penalized generalized least squares model, or PGLS. The penalty discourages the model from simply tracing every noisy point, much as smoothing a jagged line can reveal its broader shape. The model also accounts for how the transformed observations vary together. Its fitted coefficients supply a measure of departure, and simulations of normal samples establish a rejection threshold.

## What the simulations showed

The comparison used samples of 20 observations and 10,000 simulations per tested setting. **Power** is the proportion of non-normal samples a test correctly identifies under those conditions.

| Simulated distribution | Proposed test compared with Shapiro–Wilk |
| --- | --- |
| t-distribution | Similar, generally slightly lower power |
| Generalized Pareto | Similar patterns across the tested shape settings |
| Gamma | Lower power, by about 10–20 percentage points in the reported comparisons |
| Chi-square | A larger gap, favoring Shapiro–Wilk over most tested settings |

As distributions became harder to distinguish from normal, detection became difficult for both methods. The [thesis results and conclusion](https://raw.githubusercontent.com/AaronScherf/Novel-Omnibus-Normality-Test-and-Power-Comparison-with-the-Shapiro-Wilk-Test/main/MATH_Final_Thesis.pdf#page=14) describe these conditions and the remaining choices: how strongly to smooth, which patterns to fit, and how to construct the final statistic.

This was my master's thesis at Indiana State University, advised by Dr. Mark Inlow. The [repository](https://github.com/AaronScherf/Novel-Omnibus-Normality-Test-and-Power-Comparison-with-the-Shapiro-Wilk-Test) includes the report and R implementation.
