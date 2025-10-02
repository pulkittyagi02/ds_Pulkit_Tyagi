# ds_Pulkit_Tyagi
Quantitative study linking Bitcoin Fear &amp; Greed sentiment to trader performance. Includes data cleaning, daily alignment, correlation analysis, ML classification, and a baseline sentiment strategy with visual outputs.

This study quantifies how Bitcoin market sentiment (Fear & Greed Index) moves with trader outcomes to make insights on correlations, behavior shifts across sentiment types, and the efficacy of a simple sentiment-driven signal.

Total volume has a negative correlation with sentiment at approximately −0.264, indicating activity tends to rise when sentiment is lower.

Unique traders also correlate negatively with sentiment at approximately −0.278, consistent with greater participation during fearful periods.

Profit ratio shows a modest positive correlation with sentiment at approximately +0.152.

Average PnL is higher in Extreme Greed (≈ 56.74) than in Extreme Fear (≈ 38.43).

A sentiment strategy (buy on Extreme Fear, sell on Extreme Greed, next‑day PnL proxy) underperformed the market benchmark.

Correlation between sentiment and trading volume −0.264 (negative correlation).

Best performing sentiment category Extreme Greed (higher average PnL = 56.74 vs 38.43 in Extreme Fear).

Strategy performance vs market Strategy cumulative return: −963,009.85; Market benchmark cumulative return: 10,254,486.95; result is about 109.4% underperformance relative to the benchmark.Showcasing that basic ML models wont fir well on this diverse data.

Data Sources Historical Trader Data: Hyperliquid exchange data (Dec 2024) as summarized in the analysis outputs.

Bitcoin Fear & Greed Index: Alternative.me historical series as reflected in the sentiment metrics used.

Methodology Data preprocessing and cleaning: parsed timestamps, coerced numeric fields, dropped invalid rows, and engineered features such as profit ratio and daily aggregates.

Temporal alignment of datasets: merged daily trading aggregates with daily sentiment (value and classification).

Statistical correlation analysis: computed Pearson/Spearman correlations between sentiment and performance/behavior metrics.

Sentiment-based performance segmentation: compared PnL, volume, participation, and trade frequency across sentiment categories (Fear/Greed/Extreme regimes).

Machine learning predictive modeling: trained a classifier to predict profitable days and extracted feature importance (volume, average trade size, sentiment value, unique traders).

Trading strategy development and backtesting: simple rules tied to Extreme Fear/Greed with next‑day PnL proxy, then benchmarked to market cumulative PnL.

Files Structure notebook_1.ipynb: Main analysis notebook covering cleaning, EDA, correlation, ML, and strategy.

csv_files/: Processed datasets and analysis outputs (e.g., correlation tables, segment summaries, strategy results).

outputs/: Visualizations such as EDA plots, correlation heatmaps, ML diagnostics, and strategy curves.

ds_report.pdf: Final report consolidating methods, results, and recommendations.

Key Technologies Python, Pandas, NumPy for data processing and feature engineering.

Matplotlib, Seaborn for visual exploration and reporting charts.

Scikit-learn for classification and feature importance.

Statistical analysis with SciPy for correlations and tests.

Results Summary Market activity (volume and participant count) increases as sentiment declines, suggesting fear-induced trading surges; meanwhile, profit ratio improves slightly with higher sentiment.

Extreme Greed days exhibit the strongest average profitability, but the simplistic rule tested did not generalize to positive returns. A more complex model that can incorporate better training on multiple variable data should make better predicitions for the same

A production strategy should therefore combine sentiment with microstructure and position context instead of relying on standalone sentiment thresholds.
