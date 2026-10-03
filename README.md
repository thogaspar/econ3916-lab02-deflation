# econ3916-lab02-deflation
ECON 3916 Lab 02 - Measurement and Indexes - Deflating History
## Deflating Economic Data: Nominal vs. Real

### Objective
Demonstrate how adjusting nominal economic series for inflation using the Consumer Price Index (CPI) changes the interpretation of long-run trends in wages and consumer prices.

### Methodology
- **Data acquisition:** Retrieved CPI and average hourly earnings series directly from FRED (Federal Reserve Economic Data) through its public endpoints, so no API key was required.
- **Deflation function:** Implemented a reusable `deflate_series()` routine that rebases any nominal series to a chosen base year by scaling it with the ratio of base-period CPI to observation-period CPI.
- **Real wage conversion:** Converted average hourly earnings to constant 2020 dollars to allow valid comparison of purchasing power across decades.
- **Cross-validation on a second series:** Applied the same deflation procedure to the US Big Mac price and compared nominal change, real change, and CPI change over identical start and end dates.
- **Interactive exploration:** Built a deflation explorer with a base-year slider, letting users see how the choice of base year shifts the level of the real series without changing its underlying trend.

### Key Findings
- **Nominal wage growth overstates gains in purchasing power.** Average hourly earnings rose from $2.50 to $32.60 in nominal terms, roughly a thirteen-fold increase. In constant 2020 dollars, the same series rose from $20.92 to $25.20, a gain of about 20%.
- **Inflation absorbed most of the nominal increase.** The gap between the nominal and real trajectories shows that most of the apparent wage growth reflected a rising price level rather than improved living standards.
- **The Big Mac series shows the same pattern.** The nominal price rose 178%, against a 95% rise in CPI over the same period. After deflation, the real price increase falls to 43%, meaning the burger became modestly more expensive in real terms, but far less so than the sticker price suggests.
- **Base-year choice affects levels, not conclusions.** The explorer shows that changing the base year rescales the real series, while relative changes and the nominal-versus-real divergence remain intact.

### Takeaway
