# AML-Final-Project-XGBoost-Driven-Sales-Forecasting-Promotion-Effectiveness-and-Volatility-Analysis


Summary of the project's methodology, findings, and business insights:

1.  **Feature Importance & Drivers of Sales**
    *   **XGBoost Analysis - Top drivers of sales:**
        *   `rolling_mean_4w` – most important (short-term momentum in sales)
        *   `lag_1_sales` – previous week’s sales
        *   `rolling_mean_12w` – longer-term trend
        *   `sharpe_4w` – measure of volatility-adjusted performance
    *   **Markdown features** (`MarkDown1–5`) are comparatively less influential, with `MarkDown3` having the largest impact.
    *   **Insight:** Short-term and lagged sales trends dominate sales prediction, but promotions can still contribute meaningfully.

2.  **Promotion / Markdown Analysis**
    *   **ROI (Sales Impact per $1 Spent):**
        *   **Best performing markdown:** `MarkDown3` (ROI ~ $0.10–$0.12 per $1)
        *   **Worst performing markdown:** `MarkDown2` (ROI negative, ~$-0.03 to $-0.05)

3.  **Walmart Segmented Analysis**
    *   **Store Type Segmentation:**
        *   `MarkDown3` consistently best across Store Types A and B.
        *   `MarkDown2` consistently worst.
    *   **Holiday vs Regular Periods:**
        *   Some markdowns like `MarkDown2` gain during holidays despite negative baseline ROI.
        *   `MarkDown3` drops in effectiveness during holidays.
    *   **Insight:** Tailor promotions not just by store but also by calendar period; what works normally may underperform in holidays.

4.  **Macroeconomic / Causal Impact Analysis**
    *   **Economic features:** `Fuel_Price`, `CPI`, `Unemployment`, `Temperature`
    *   **Feature importance:** `Unemployment` > `Temperature` > `Fuel_Price` > `CPI`
    *   **Correlation with sales:** All weak (`|corr| < 0.2`), indicating indirect or small linear effects.
    *   **Elasticity:**
        *   `Temperature`: +0.009% sales per 1% increase
        *   `Fuel_Price`: +0.023% sales per 1% increase
        *   `CPI`: -0.065% sales per 1% increase
        *   `Unemployment`: -0.005% sales per 1% increase
    *   **Insight:** Macroeconomic factors have measurable but modest effects on sales.

5.  **Cash Flow Stability & Volatility Analysis**
    *   **Store-level stability (CV):**
        *   60% of stores are volatile (CV>0.6)
        *   40% moderate (CV 0.3–0.6)
        *   Top 5 most stable stores: CV ~0.545–0.579
        *   Top 5 most volatile stores: CV ~0.706–0.749
    *   **Insight:** Cash flow risk is significant at store levels; planning should focus on high-CV stores/departments.

6.  **Revenue at Risk (VaR) Analysis**
    *   Type A stores have higher mean sales but slightly higher risk.
    *   **Insight:** VaR analysis complements volatility, identifying stores that could face extreme low sales, crucial for cash flow planning.

---




### Data Analysis Key Findings
*   **Sales Drivers:** Short-term sales momentum (`rolling_mean_4w`) and previous week's sales (`lag_1_sales`) are the most significant drivers of sales, followed by `rolling_mean_12w` and `sharpe_4w`. Markdown features are less influential overall, with `MarkDown3` having the largest impact among them.
*   **Promotion Effectiveness (ROI):** `MarkDown3` is the best-performing markdown with an ROI of approximately \$0.10-\$0.12 per \$1 spent, while `MarkDown2` is the worst, showing a negative ROI of approximately -\$0.03 to -\$0.05 per \$1.
*   **Segmented Promotion Performance:**
    *   `MarkDown3` consistently outperforms other markdowns across Store Types A and B.
    *   `MarkDown2` consistently underperforms across Store Types A and B.
    *   During holiday periods, `MarkDown2` shows improved effectiveness despite its negative baseline ROI, whereas `MarkDown3`'s effectiveness decreases.
*   **Macroeconomic Impact:**
    *   `Unemployment` is the most important macroeconomic feature, followed by `Temperature`, `Fuel_Price`, and `CPI`.
    *   All economic factors exhibit weak correlations with sales (absolute correlation values less than 0.2).
    *   Elasticity of sales to a 1% increase in these factors is: `Temperature` (+0.009%), `Fuel_Price` (+0.023%), `CPI` (-0.065%), and `Unemployment` (-0.005%).
*   **Cash Flow Stability:** 60% of stores are classified as volatile (Coefficient of Variation, CV > 0.6), and 40% are moderately volatile (CV 0.3–0.6). The most stable stores have a CV range of 0.545–0.579, while the most volatile stores range from 0.706–0.749.
*   **Revenue at Risk (VaR):** Type A stores, despite having higher average sales, also present a slightly higher risk as identified by VaR analysis.

### Insights or Next Steps
*   Optimize promotional strategies by tailoring them not only by store type but also by calendar period, recognizing that promotion effectiveness can shift during holidays.
*   Prioritize cash flow planning and risk mitigation for stores identified as highly volatile (high CV) and those with higher Revenue at Risk, such as Type A stores, to prepare for potential extreme low sales events.
