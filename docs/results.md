### Principal Component Analysis (PCA)
- Conducted on initial 61 variables
   - For 80% variance explained, would need 16 Principal Components
<img src="images/Screenshot 2024-12-11 at 6.27.00 PM.png" alt="drawing" width="600"/>
- Use 8 PC's based on Scree Plot
<img src="images/Survival_by_class.png" alt="drawing" width="600"/>
<img src="images/Screenshot 2024-12-11 at 6.26.53 PM.png" alt="drawing" width="600"/>
- 8 principal components explain approximately 65% of data variance



### Clustering Analysis
- Chosen to identify homogeneous groups of companies based on their financial profiles
- Helps provide insight into sector-independent “types” or “archetypes” within the sample
- Utilized Hierarchical Clustering based on PCA results
- Applied Minimax Linkage method
- Produced 6 uneven clusters
- Examined cluster means for key financial metrics, noting distinct differences in revenue and price changes across clusters
    -Observed significant differences in:
       - Revenue between clusters
       - Price change between clusters

### Factor Analysis
#### Exploratory Factor Analysis
- Investigated underlying latent structures in financial data
- Aid in interpreting complex financial indicators through a smaller set of meaningful factors.
- Conducted on the selected key variables, extracting four main factors representing operational scale/size, financial stability, profitability, and growth potential
- Factor loadings guided the conceptual interpretation of each latent dimension

Factor 1: Operational Scale or Size of the Company (Loadings)
  - Revenue (0.943)
  - Gross Profit (0.878)
  - Operating Income (0.610)
  - EBITDA (0.937)
  - Free Cash Flow (0.635)

Factor 2: Financial Position and Stability (Loadings)
  - Total Assets (0.997)
  - Total Liabilities (0.998)
  - Total Shareholders’ Equity (0.887)

Factor 3: Profitability (Loadings)
  - EBIT Margin (0.982)
  - EPS (0.982)
  - Profit Margin (0.694)

Factor 4: Growth Potential or Market Perception (Loadings)
  - Operating Income (0.720)
  - Gross Profit (0.379)
  - Price to Sales Ratio (-0.365)

#### Confirmatory Factor Analysis

- Test a hypothesized factor structure derived from EFA and theoretical considerations
- Validate whether proposed latent factors (e.g., operational scale, financial stability) adequately fit the observed data

- Specified a two-factor model (operational scale and financial stability)
Proposed two primary latent factors:

1. **Operational Scale** (Loadings)
  - Revenue (0.779)
  - Gross Profit (1.069)
  - Operating Income (0.798)

2. **Financial Stability** (Loadings)
  - Total Assets (0.722)
  - Net Income (1.245)

- Evaluated model fit using CFI, RMSEA, and SRMR, identifying areas for refinement

##### Model Fit Metrics
- Comparative Fit Index (CFI): 0.88
- Root Mean Square Error of Approximation (RMSEA): 0.391
- Standardized Root Mean Square Residual (SRMR): 0.057

### Multivariate Analysis of Variance (MANOVA)
- Assesses whether multiple financial metrics vary simultaneously across different sectors or groupings
- Provide a holistic test of sector-level differences rather than examining each metric individually
- Focused on inter-sector differences
- Conducted using selected financial variables as dependent measures
- Tested sector-based differences, yielding insights into how entire financial profiles differ across industry contexts
