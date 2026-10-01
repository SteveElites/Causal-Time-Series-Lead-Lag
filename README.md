# Causal-Time-Series-Lead-Lag
Does daily lead-lag structure in liquid ETFs survive out of sample? No — and the failure is the finding.

Sparse causal structure did not beat a univariate AR baseline. On vol-standardised returns, median OOS R² was −1.11% for CAUSAL, −0.71% for AR, and −4.82% for the dense VAR. The Diebold–Mariano test confirms CAUSAL is significantly less accurate than AR (stat −3.37, p = 0.001), and 0/14 assets produced a positive R². Conditioning on selected parents removed more signal than noise at the daily horizon.

The discovered graph is too unstable to trade: 3.8 edges selected per window on average, 58/165 windows selecting nothing, mean Jaccard similarity 0.52, and the most persistent edge (XLF → XLI) appearing in only 15% of windows. A structure that flickers this much is estimation noise, not lead-lag.

Economically, the edge does not survive frictions. The sign strategy earns 0.35 gross Sharpe and 0.17 net of 1 bp, with daily turnover 0.64; net Sharpe turns non-positive by 2 bp — a realistic cost for 14 liquid ETFs.

The one signal worth noting is regime-dependent: the causal model delivered 0.42 net Sharpe during the COVID crash versus −0.11 for AR, but underperformed AR in calm 2023–2025 (0.70 vs 0.89) and lost in the 2022 rate shock (−1.15 vs −0.74). Lead-lag appears to be a liquidity-stress phenomenon, not a persistent edge — and one stress episode is not enough to build on.

The synthetic control explains why: on data with a known graph, the selector found only 2/14 edges at precision 1.00 and recall 0.14. It is conservative — what it finds is usually real — but a 504-day window with fat tails lacks the power to recover weak links, and real ETF lead-lag is weaker than the simulation's.

Bottom line: daily lead-lag between liquid ETFs is too heavily arbitraged for sparse causal structure to exploit at this horizon with this sample size. The honest result is a negative one, and it argues for intraday data, non-linear conditional independence tests (PCMCI), and regime-switching models rather than more feature engineering on daily closes.
