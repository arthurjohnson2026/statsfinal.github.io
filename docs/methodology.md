# Methodology

## Data Collection and Preprocessing
### Data Source
- Financial metrics sourced from SEC 10-K filings via Financial Modeling Prep API
- Comprehensive dataset spanning 5 years (2014-2018)
- Initial dataset characteristics:
 - 226 financial metrics/ratios
 - 3,786 companies
 - 11 different sectors

### Data Cleaning and Variable Selection
#### Missing Value Treatment
- Applied quantile-based thresholding for variable removal:
 - Removed columns with >5.9% N/A values (50th percentile threshold)
 - Removed columns with >7.5% zero values (60th percentile threshold)
- Reduced initial 226 variables to 61, subsequently focusing on 15 key variables

#### Outlier Removal
- Eliminated companies with >500% price increase
 - Removed 21 companies to reduce data noise
 - Justified by being well above industry average price variations

## Analytical Approaches

### Principal Component Analysis (PCA)
- Conducted to reduce dimensionality of financial metrics
- Conducted on initial 61 variables
   - For 80% variance explained, would need 16 Principal Components
   - This is too many to interpret
- Opted to use 8 PC's based on Scree Plot elbow, and for best interpretability
- Key finding: 8 principal components explain approximately 65% of data variance

### Clustering Analysis
- Utilized Hierarchical Clustering based on PCA results
- Applied Minimax Linkage method
- Produced 6 uneven clusters
- Observed significant differences in:
   - Revenue between clusters
   - Price change between clusters

### Factor Analysis
#### Exploratory Factor Analysis
- Investigated underlying latent structures in financial data

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
Proposed two primary latent factors:

1. **Operational Scale** (Loadings)
  - Revenue (0.779)
  - Gross Profit (1.069)
  - Operating Income (0.798)

2. **Financial Stability** (Loadings)
  - Total Assets (0.722)
  - Net Income (1.245)

##### Model Fit Metrics
- Comparative Fit Index (CFI): 0.88
- Root Mean Square Error of Approximation (RMSEA): 0.391
- Standardized Root Mean Square Residual (SRMR): 0.057

### Multivariate Analysis of Variance (MANOVA)
- Conducted to explore variations across different financial metrics
- Focused on inter-sector differences


## Limitations and Considerations
- High data complexity and noise in stock/financial datasets
- Challenges in clustering and factor analysis due to data structure
- Potential benefits of sector-specific analysis

## Proposed Future Directions
- Sector-specific focused analysis
- Year-to-year comparative analysis
- Implementation of panel data with fixed effects models
- Hotelling T^2 test to compare statistical metrics between price-increasing and price-decreasing stocks
