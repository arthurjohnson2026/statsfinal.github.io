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

# Classifying Company Performance through PCA, Clustering, and Factor Analysis

This document explores the analysis of SEC 10-K financial filings, aiming to classify company performance using various multivariate techniques like PCA, clustering, and factor analysis.

## Introduction

### Motivation

- Annual 10-K filings provide critical insights:
  - Financial metrics like earnings reports, debt, and revenue.
  - Thoroughly analyzed and highly influential for investors.
- **Objective**: Use multivariate analysis to identify key financial metrics associated with a firm's annual stock market performance.

**Key Questions**:
- Can multivariate analysis reveal the most critical financial ratios for predicting stock price changes?
- How can these insights inform investment decisions?

**Dataset Overview**:
- Data Source: [Financial Modeling Prep](https://site.financialmodelingprep.com/)
- Data Scope:
  - **5 years**: 2014-2018
  - **226 financial metrics/ratios**
  - **3,786 companies** across **11 sectors**
- Target Variables:
  - **Percent Change in Stock Price (next year)**
  - Binary Indicator: **Up (1)** or **Down (0)**.
<img src="images/Screenshot 2024-12-11 at 6.25.31 PM.png" alt="Classification" width="600">

---

## Exploratory Data Analysis (EDA)

### Initial Observations

- **Challenges**:
  - The dataset contains **226 predictors**, posing computational challenges.
  - Many predictors have a significant number of **0's** and **NA's**.


<div style="display: flex; justify-content: space-between;">
    <img src="images/Screenshot 2024-12-11 at 6.25.44 PM.png" alt="Classification" width="600">
    <img src="images/Screenshot 2024-12-11 at 6.25.52 PM.png" alt="Classification" width="600">
</div>

- **Strategy**:
  - Implement thresholds to systematically remove variables with excessive missing or zero values.

### Variable Filtering Process

#### Missing Value Threshold:
- Removed columns above the 50th percentile for **NA dominance**:
  - Threshold: Columns with >5.9% NA values.

#### Zero-Dominance Threshold:
- Removed columns above the 60th percentile for **0 dominance**:
  - Threshold: Columns with >7.5% 0 values.

#### Results:
- Reduced predictors to **61 variables**, which were later refined to **15 key variables** for analysis.

### Outlier Removal

- Companies with **>500% stock price increase** were removed to reduce noise:
  - Rationale: **500%** is well above the industry average.
  - Impact: Only **21 companies** were excluded.

---

### Next Steps

- Perform **PCA** to reduce dimensionality and understand variance distribution.
- Utilize clustering and factor analysis to identify latent patterns in financial performance.

This analysis aims to bridge the gap between raw financial data and actionable insights for investors.

---
