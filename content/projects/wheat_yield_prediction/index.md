---
title: Validating Remote Sensing and Machine Learning Approaches for CIMMYT Wheat Yield Prediction
date: 2026-08-22
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/wheat_yield_prediction_gee
  - type: pdf
    url: https://raw.githubusercontent.com/AaronScherf/wheat_yield_prediction_gee/master/reports/Aaron_M_Scherf_Final_Thesis.pdf
tags:
  - Python
  - Machine Learning
  - Remote Sensing
---

My master's thesis for UC Berkeley's Master of Development Practice program (Spring 2020, advised by Professor David Zilberman): testing whether satellite-derived environmental data and open-source machine learning can predict wheat yields in untested locations as well as manually collected trial data and standard genotype-by-environment models.

<!--more-->

Crop breeding research is good at identifying which genetic crosses raise yield, but far weaker at predicting "which variety wins where" once a new environment lacks prior field trials — a gap that hits hardest in the low-income regions most exposed to climate change, where running additional trials is expensive. This thesis asks whether Google Earth Engine's free environmental data, paired with open-source machine learning tools, can substitute for costly manually collected trial data as a low-cost, reproducible alternative for out-of-sample yield prediction.

The analysis combined CIMMYT international wheat trial yield and environment data with Earth Engine variables (soil moisture, vapor pressure, evapotranspiration, precipitation) and ICIS genotype pedigree data reduced to principal components. Four models were trained to predict yields on a holdout sample of fields: a Bayesian genotype-by-environment linear mixed model (BGLR) as the field's standard approach, and three machine learning alternatives — random forest, XGBoost, and a multi-layer perceptron — each run across combinations of environment data source (CIMMYT vs. Earth Engine) and with or without pedigree information.

The machine learning models, particularly random forest, consistently outperformed the linear mixed model (R² around 0.82 vs. 0.11–0.26) while running on free Google Colab resources; the BGLR model, by contrast, needed a terabyte-RAM virtual machine just to invert the genetic covariance matrices. Remote sensing data improved accuracy for the linear model but not for the machine learning models, and the two data sources relied on different features — CIMMYT models leaned on altitude and row spacing, Earth Engine models on soil moisture and vapor pressure. The results suggest an open-source pipeline built on Earth Engine and machine learning can meaningfully substitute for expensive manual trial data in resource-limited settings, though full reproducibility remains constrained by restricted access to genotype pedigree data. Full data, methodology, and results are in the linked thesis and repository.
