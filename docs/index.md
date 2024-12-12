---
title: "Classifying Company Performance"
author: "Arthur Johnson"
output: 
  html_document:
    theme: cosmo
    highlight: tango
    self_contained: true
    keep_md: true
---

- [Data Description](data.md)
- [Methodology](methodology.md)
- [Results](results.md)
- [Conclusion](conclusions.md)
- All code: [Code](https://github.com/arthurjohnson2026/statsfinal.github.io)



# Classifying Company Performance through PCA, Clustering, and Factor Analysis

This document explores the analysis of SEC 10-K financial filings, aiming to classify company performance using various multivariate techniques like PCA, clustering, and factor analysis.

- Utilized R for analysis

- Utilized Prinicipal Component Analysis, Heirarchical Clustering, Exploratory and Confirmatory Factor Analysis, MANOVA.

- Data: [Financial Modeling Prep](https://site.financialmodelingprep.com/)

## Introduction

### Motivation

- Annual 10-K filings provide critical insights:
  - Financial metrics like earnings reports, debt, and revenue.
  - Thoroughly analyzed and highly influential for investors.
- **Objective**: Use multivariate analysis to identify key financial metrics associated with a firm's annual stock market performance.

**Key Questions**:
- Can multivariate analysis reveal the most critical financial ratios for predicting stock price changes?
- How can these insights inform investment decisions?

## Key Findings

- **Principal Components and Noise:** Using PCA, eight components explained about 65% of variance, indicating substantial complexity and noise in the data, making it challenging to derive clear, stable groupings.  
- **Latent Factors via Factor Analysis:** EFA and CFA revealed four main latent constructs—operational scale, financial stability, profitability, and growth potential—though model fit and interpretability remained areas for improvement.  
- **Sector-Based Differences:** MANOVA showed statistically significant differences across sectors for most financial metrics, suggesting that industry context plays a crucial role in firms’ financial characteristics.

## Future Work

- **Refine Scope and Preprocessing:** Narrow the analysis to a single sector and apply more robust data cleaning and dimensionality reduction methods to improve clarity and interpretability.  
- **Longitudinal and Advanced Modeling:** Conduct year-to-year comparisons, consider panel data with fixed effects, and explore alternative modeling techniques (e.g., more flexible factor structures, advanced time-series analyses) to better capture trends and enhance model fit.

## Literature/Bibliography

Title: "Estimating Latent Asset-Pricing Factors"
Authors: Martin Lettau and Markus Pelger
Journal Published: Not specified (working paper on SSRN)
Year Published: 2019 (Draft dated January 10)
DOI: https://ssrn.com/abstract=3175556 


---
