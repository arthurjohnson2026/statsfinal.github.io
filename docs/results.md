
- [Data Description](data.md)
- [Methodology](methodology.md)
- [Results](results.md) **YOU'RE HERE**
- [Conclusion](conclusions.md)



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
- Utilized Scree plot to determine proper number of factors, which ended up being 6; however, based on model complexity and interpretability, 4 factors were ultimately used for analysis.

<img src="images/Screenshot 2024-12-11 at 11.07.35 PM.png" alt="drawing" width="600"/>

- These were the interpretations of the latent factors.

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

<img src="images/Screenshot 2024-12-11 at 11.08.03 PM.png" alt="drawing" width="400"/>


#### Confirmatory Factor Analysis

- Based on our original factors, wanted to test whether company size and financials were valid theories for latent dimensions
Proposed two primary latent factors:

1. **Operational Scale** (Loadings)
  - Revenue (0.779)
  - Gross Profit (1.069)
  - Operating Income (0.798)

2. **Financial Stability** (Loadings)
  - Total Assets (0.722)
  - Net Income (1.245)

These factors were run against four variables (\lambda), which were revenue, gross profit, operating income, total assets, net income.

The flow chart shows the directionality and strength of the latent relationships.

<img src="images/Screenshot 2024-12-12 at 11.14.33 AM.png" alt="drawing" width="400"/>

Also, the simplified equation relationships are shown below:

<img src="images/Screenshot 2024-12-12 at 11.28.07 AM.png" alt="drawing" width="400"/>

##### Model Fit Metrics and Analysis
- Comparative Fit Index (CFI): 0.88
- Root Mean Square Error of Approximation (RMSEA): 0.391
- Standardized Root Mean Square Residual (SRMR): 0.057

- The CFA model explains relationships among financial metrics but shows room for improvement in fit (low CFI, high RMSEA)
- Good fit in SRMR metric
- Strong loadings for latent variables suggest good construct validity
- Negative residual variances highlight potential concerns requiring further investigation
- Also, it seems that there may be multicollinearity between the latent factors


### Multivariate Analysis of Variance (MANOVA)
- Conducted using selected financial variables as dependent measures

<img src="images/Screenshot 2024-12-12 at 11.16.17 AM.png" alt="drawing" width="400"/>

Groups were statistically significantly different (p<.05) across all financial metrics other than: 
- Gross_Profit_Growth
- EPS
- returnOnEquity 
- Capex_to_Depreciation

This indicates that some sectors do substantially differ when it comes to revenue, costs, assests, and total profit. 



