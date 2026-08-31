---
title: Novel Omnibus Normality Test
date: 2026-08-22
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/Novel-Omnibus-Normality-Test-and-Power-Comparison-with-the-Shapiro-Wilk-Test
  - type: pdf
    url: https://raw.githubusercontent.com/AaronScherf/Novel-Omnibus-Normality-Test-and-Power-Comparison-with-the-Shapiro-Wilk-Test/main/MATH_Final_Thesis.pdf
tags:
  - Statistics
  - R
  - Mathematics
---

My master's thesis in mathematics at Indiana State University, advised by Dr. Mark Inlow: the construction of a new omnibus normality test built on a penalized generalized least squares model, with its statistical power compared against the field-standard Shapiro-Wilk test.

<!--more-->

The Shapiro-Wilk test is the default choice for normality testing in most applied statistics, but it is only approximately omnibus — its power depends on assumptions about a sample's skew and kurtosis, and it struggles most on distributions that are nearly normal with a small amount of skew or kurtosis introduced. This thesis develops an alternative: an empirical process that standardizes and orders a sample, applies the probability integral transform, and subtracts the expected value of each order statistic to produce a zero-mean vector. Samples drawn from a normal distribution fluctuate randomly around zero under this transform, while non-normal samples show systematic, distribution-specific departures — the signal the new test is built to detect.

To turn that signal into a hypothesis test, the thesis models the departures with a penalized generalized least squares (PGLS) regression, using a penalty term motivated by smoothing splines to separate systematic departure from noise. The design matrix is built from the eigenvectors of the sample's covariance matrix, chosen because they point in the directions of maximal deviation from zero and are most informative precisely for near-normal samples where Shapiro-Wilk is weakest. A test statistic is then derived from the resulting PGLS coefficients.

Simulated power tests (10,000 iterations, n = 20) compared the PGLS test against Shapiro-Wilk across the t-, chi-square, gamma, and generalized Pareto distributions. PGLS matched Shapiro-Wilk closely for the t-distribution and generalized Pareto distribution, including in the near-normal skew/kurtosis regime where Shapiro-Wilk's power drops off sharply, while trailing it for the chi-square and gamma distributions. The results serve as a proof of concept rather than a finished, optimized test, with the choice of penalty weight, penalty matrix, design matrix, and test statistic all identified as open directions for future work. Full derivations, R implementation, and simulation results are in the linked thesis and repository.
