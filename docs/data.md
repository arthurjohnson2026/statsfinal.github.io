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

| Financial Term | Brief Description |
|---------------|-------------------|
| Revenue | Total amount of money earned by the company from its primary business activities before any expenses are subtracted |
| Gross Profit | Total revenue minus the cost of goods sold (COGS); represents the profit a company makes after deducting the direct costs of producing its goods or services |
| Operating Income | Profit earned from a company's core business operations, calculated by subtracting operating expenses from gross profit |
| Net Income | The bottom line profit after all expenses, taxes, and costs have been deducted from total revenue |
| EPS (Earnings Per Share) | The portion of a company's profit allocated to each outstanding share of common stock |
| EBITDA | Earnings Before Interest, Taxes, Depreciation, and Amortization; a measure of a company's overall financial performance |
| EBIT Margin | Earnings Before Interest and Taxes divided by total revenue, showing profitability before accounting for interest and taxes |
| Profit Margin | Percentage of revenue that translates into profits, calculated by dividing net income by total revenue |
| Free Cash Flow | Cash a company generates after accounting for cash outflows to support operations and maintain capital assets |
| Return on Equity (ROE) | Measure of a company's profitability relative to shareholders' equity, showing how efficiently it uses shareholders' investments |
| Price to Sales Ratio | Comparison of a company's stock price to its revenues, indicating how much investors are willing to pay per dollar of sales |
| Total Assets | The total value of all resources owned by a company that have economic value |
| Total Liabilities | All financial obligations and debts owed by the company |
| Total Shareholders Equity | The total value of the company owned by shareholders, calculated as total assets minus total liabilities |
| Operating Cash Flow | Cash generated from normal business operations, excluding external investment and financing activities |
| Capex to Depreciation | Ratio of capital expenditures to depreciation, showing how much a company is investing in new fixed assets |
| Gross Profit Growth | Percentage increase in gross profit from one period to another |
| Net Income Growth | Percentage increase in net income from one period to another |
| 2015 Price Var [%] | Percentage change in stock price during the year 2015 |

### Outlier Removal

- Companies with **>500% stock price increase** were removed to reduce noise:
  - Rationale: **500%** is well above the industry average.
  - Impact: Only **21 companies** were excluded.
<img src="images/Screenshot 2024-12-11 at 6.26.01 PM.png" alt="Classification" width="600">

### Correlation Matrix:

- Correlation matrix was plotted to see if there was significant multicollinearity
  - Many variables had incredibly high correlation (due to be direct derivative ratios of one another)
      - These were removed for viability of the model

<img src="images/Screenshot 2024-12-11 at 6.26.07 PM.png" alt="Classification" width="600">



---

### Next Steps

- Perform **PCA** to reduce dimensionality and understand variance distribution.
- Utilize clustering and factor analysis to identify latent patterns in financial performance.

---
