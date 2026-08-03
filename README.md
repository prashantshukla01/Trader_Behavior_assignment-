# Trader Performance vs. Bitcoin Market Sentiment

Analysis of Hyperliquid historical trade data against the Bitcoin Fear & Greed Index, done as
part of a hiring assignment.

## Contents

| File | Description |
|---|---|
| `crypto_sentiment_analysis.ipynb` | Full Jupyter notebook — load, clean, merge, EDA, 8 charts, insights, recommendations. Commented and pre-executed with outputs. |
| `report.pdf` | 6-page summary report: objective, data cleaning, key visualizations, insights, recommendations, limitations. |
| `charts/` | All 8 generated charts as standalone PNGs. |
| `summary_by_sentiment.csv` | Aggregated trade count, volume, win rate, and PnL by sentiment class. |
| `account_performance.csv` | Per-account trade count, total PnL, and win rate. |

## Datasets Used

1. **`historical_data.csv`** — Hyperliquid trade-level data (account, coin, execution price,
   size, side, direction, closed PnL, fee, timestamp). 211,224 rows, 32 accounts, 246 assets,
   May 2023 – May 2025.
2. **`fear_greed_index.csv`** — Daily Bitcoin Fear & Greed Index classification (Extreme Fear →
   Extreme Greed). 2,644 daily readings, Feb 2018 – May 2025.

## How to Reproduce

1. Place `historical_data.csv` and `fear_greed_index.csv` in the same folder as the notebook.
2. Open `crypto_sentiment_analysis.ipynb` and run all cells (or use the pre-executed version
   as-is — outputs are already embedded).
3. `report.pdf` was generated separately from the same analysis; see the notebook for the
   underlying code behind every chart and number in the report.

## Headline Findings

- **Win rate is non-linear with sentiment**: highest in Extreme Greed (89.2%) and Fear (87.3%),
  lowest in Extreme Fear (76.2%) and plain Greed (76.9%).
- **Fear, not Greed, drives the most volume and total profit** in this sample.
- **Performance is concentrated**: a small number of accounts account for most realized PnL, and
  the top 10 most profitable accounts keep high win rates across every sentiment regime.
- Sell-side share of trades rises steadily from Extreme Fear (49%) to Extreme Greed (55%).

## Known Limitation

The assignment brief references a `leverage` field, but the trade data provided does not include
one — leverage-based analysis was not possible and is called out rather than estimated.
