---
title: Predicting Wheat Yields in New Environments
summary: "Compare satellite data, field records, and prediction models to investigate which wheat varieties may perform well where trials are limited."
date: 2026-08-22
lastmod: 2026-10-16
links:
  - type: site
    icon: brands/github
    label: GitHub
    url: https://github.com/AaronScherf/wheat_yield_prediction_gee
  - type: pdf
    url: https://raw.githubusercontent.com/AaronScherf/wheat_yield_prediction_gee/master/reports/Aaron_M_Scherf_Final_Thesis.pdf
image:
  caption: 'Illustration of the model comparison and satellite-data workflow; measured results are reported in the thesis.'
tags:
  - Python
  - Machine Learning
  - Remote Sensing
---

Choosing a wheat variety is partly a question of where it will grow. My master's thesis tested whether satellite measurements of the environment and accessible machine learning tools could help predict yields where field-trial information is limited. I compared those measurements with field records, using wheat trials from CIMMYT, an international crop-research organization.

<!--more-->

The results separated two questions that can easily get mixed together. Machine learning models outperformed the study's linear mixed-model baseline on held-out observations. Satellite data helped that baseline, but the machine learning models performed better with the manually collected environmental data. A stronger model and a more accessible data source did not automatically make the best combination.

[[Insert Image: Replace the current illustrative montage with a compact results chart made using standard plotting tools from Table 6 of the linked thesis, printed page 34, PDF page 42. Compare environment-only holdout R-squared values: field records—random forest 0.829, linear mixed model 0.113; satellite data—random forest 0.746, linear mixed model 0.243. Use these exact values, a common axis, large labels, and no invented scatter points or map heat spots. Keep the existing featured image until its replacement is approved. Suggested caption: "Changing the model and changing the data source had different effects in this study's holdout sample." Suggested alt text: "Random forest outperformed the linear mixed model for both data sources; satellite data improved the linear model but reduced random forest performance." Save the approved chart as featured.jpg or featured.png in this page bundle and remove this brief.]]

## What was compared

Google Earth Engine supplied environmental measurements such as soil moisture, precipitation, and vapor pressure. Field records supplied another view of growing conditions and management. I also tested adding pedigree information describing relationships between wheat varieties.

Four approaches predicted yields: a Bayesian linear mixed model, random forest, gradient boosting, and a neural network. Fifteen percent of observations were held out for the final comparison, with varieties represented across that sample. This tests predictions within the study's data; use in new regions would need further validation.

For a direct comparison using environmental data alone:

| Environmental information | Random forest R² | Linear mixed-model R² |
| --- | --- | --- |
| Field records | 0.829 | 0.113 |
| Satellite-derived data | 0.746 | 0.243 |

R² measures how much of the variation in the held-out yields the predictions account for relative to predicting the average. It is not the percentage accuracy of an individual yield prediction. The [thesis, Table 6](https://raw.githubusercontent.com/AaronScherf/wheat_yield_prediction_gee/master/reports/Aaron_M_Scherf_Final_Thesis.pdf#page=42) gives the full comparison, including pedigree information.

## Accessibility mattered too

The machine learning models ran on freely available Google Colab resources, though some calculations took hours. The mixed model's large genetic covariance matrices required a specialized machine with roughly a terabyte of memory. Computing requirements were therefore part of the comparison, alongside prediction quality.

The code is public, but restricted pedigree data prevents full reproduction from public inputs alone. The project is a research proof of concept, with further work needed on location precision, model settings, and validation before using its predictions to make planting decisions.

This was my Spring 2020 thesis for UC Berkeley's Master of Development Practice, advised by Professor David Zilberman. The [repository](https://github.com/AaronScherf/wheat_yield_prediction_gee) contains the code and full report.
