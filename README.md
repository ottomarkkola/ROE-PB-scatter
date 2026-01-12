# ROE-PB-scatter
Python screener that fetches P/B and 2-year average ROE from yfinance, ranks long/short candidates, exports results to CSV/XLSX, and plots a long/short chart.
## Features
- Parse tickers from a text file (e.g., S&P 500 list)
- Fetch:
  - **P/B** (`priceToBook`)
  - **ROE 2Y avg** (average of the latest two common years)
- Compute a combined **score** (high ROE + low P/B)
- Compute “reverse score” for **Top Shorts**
- Export:
  - `results.csv`
  - `results.xlsx` (sheets: `all`, `cleaned`, `top_long`, `top_short`)
- Plot:
  - Long/short boundary curves + labeled tickers
-ROE is ranked with higher ROE = better (smaller rank)

-P/B is ranked with lower P/B = better (smaller rank)

-score = rank(ROE, descending) + rank(PB, ascending)

Interpretation:
- **Lower score = better long candidate**
- **Higher score = worse candidate** → used for the **top short list**
