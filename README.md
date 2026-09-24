# Index Integrity — Deflation, Substitution Bias & Goodhart

**Objective:** This project develops and validates a rigorous pipeline for deflating nominal economic time series, quantifying substitution bias in official price indices, and detecting metric gaming through correlation-based diagnostics.

**Methodology:**
- Diagnosed and corrected four defects in a nominal-to-real deflation function, including a critical unit-labeling error that reported 1982–84-dollar-denominated output as though it were expressed in 2020 dollars
- Constructed a reusable, tested utility module (`deflation_utils.py`) implementing a validated `deflate_series()` function for constant-dollar conversion
- Quantified upper-level substitution bias by comparing compound annual growth rates of CPI-U and Chained CPI-U (C-CPI-U), converting the comparison from a non-standard index-point-per-year gap into the economically meaningful percentage-points-per-year unit used by the Boskin Commission and BLS
- Diagnosed a Goodhart's Law regime shift by detecting a sign flip in the rolling correlation between a primary engagement metric (DAU/MAU) and a counter-metric (time per session) before and after the metric became an optimization target
- Extended the analysis into an interactive monitoring dashboard (ipywidgets + Plotly) enabling real-time exploration of substitution-bias sensitivity to start date and seasonal-adjustment basis, alongside a rolling-window correlation alert system

**Key Findings:**
- The deflation pipeline's original unit-mislabeling bug, if left uncorrected, would have systematically misrepresented real wage levels relative to their stated base year
- Upper-level substitution bias, measured as the gap between CPI-U and C-CPI-U compound annual growth rates, was found to be **[YOUR VALUE] percentage points per year** — a figure below the naive index-point-based estimate of **[YOUR VALUE] index points per year**, underscoring why compounding-based units are the economically correct basis for cost-of-living comparisons
- The DAU/MAU vs. time-per-session correlation shifted from **[YOUR VALUE]** (positive, organic phase) to **[YOUR VALUE]** (negative, post-optimization phase), providing quantitative evidence consistent with Goodhart's Law once the primary metric became a formal target
