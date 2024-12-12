### Principal Component Analysis (PCA)
- Conducted on initial 61 variables
   - For 80% variance explained, would need 16 Principal Components
     
<img src="images/Screenshot 2024-12-11 at 6.27.00 PM.png" alt="drawing" width="600"/>

- Use 8 PC's based on Scree Plot

<img src="images/Screenshot 2024-12-11 at 6.26.53 PM.png" alt="drawing" width="600"/>

- 8 principal components explain approximately 65% of data variance

<img src="images/Screenshot 2024-12-11 at 10.36.41 PM.png" alt="drawing" width="600"/>

- The first 8 PC loadings (attached in the image above) seem to denote
   - PC1: high loadings on earnings/revenue, negative to expenditures
   - PC2: high on margins
   - PC3: high on all value metrics per share/could show value in smaller companies
   - PC4:High loadings on all cash/variants, shows liquidity perhaps
   - PC5: Similar to PC3
   - PC6: Very high on asset value metrics
   - PC7: Super high Earning readings
   - PC8: All Equity metrics


### Clustering Analysis
- Utilized Hierarchical Clustering based on PCA results, in order to try and see whether there were any significant groupings by metric
- Applied Minimax Linkage method

<img src="images/Screenshot 2024-12-11 at 10.52.19 PM.png" alt="drawing" width="600"/>

- Produced 6 uneven clusters, when plotted in PC space (PC1 and PC2)

<img src="images/Screenshot 2024-12-11 at 10.52.35 PM.png" alt="drawing" width="600"/>

- Appears that PC1 does the majority of the distinguishing between clusters 1, 2, 5, and 6
- PC2 distinguishes clusters 3 and 6 from all others


- Examined cluster means for key financial metrics, noting distinct differences in revenue and price changes across clusters
    -Observed differences in:

Revenue between clusters
  
<img src="images/Screenshot 2024-12-11 at 10.58.28 PM.png" alt="drawing" width="600"/>

Price change between clusters

<img src="images/Screenshot 2024-12-11 at 10.58.41 PM.png" alt="drawing" width="600"/>

Due to uneven cluster size, and difficult PC's to interpret, the minimax prototypes showed no real difference between clusters in a meaningful way. 


### Factor Analysis
#### Exploratory Factor Analysis
- Conducted on the selected key variables, extracting four main factors representing operational scale/size, financial stability, profitability, and growth potential
- Utilized Scree plot to determine proper number of factors

<img src="images/Screenshot 2024-12-11 at 11.07.35 PM.png" alt="drawing" width="600"/>

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

Full Loadings:

<img src="images/Screenshot 2024-12-11 at 11.07.54 PM.png" alt="drawing" width="600"/>

Uniqueness Values:

<img src="images/Screenshot 2024-12-11 at 11.08.03 PM.png" alt="drawing" width="600"/>


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
