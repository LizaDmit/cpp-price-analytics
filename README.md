# Price analytics CLI (C++)

A command-line tool that reads a daily price series from a CSV file and reports basic return and risk statistics.

## What it reports
- Average daily return and daily volatility (sample standard deviation)
- Annualised return (× 252) and annualised volatility (× √252)
- Best and worst day
- Maximum drawdown (largest fall from a running peak) and its date
- Peak 20-day rolling volatility and its date

## Build and run
```bash
g++ -std=c++17 -O2 src/main.cpp src/functions.cpp -o finance
./finance                      # uses data/prices.csv
./finance path/to/prices.csv   # or your own file
```
Input format: a header row, then `Date,Close` on each line.

<!-- Optional: once you have a year of real data in data/prices.csv, paste a run here:
## Example
```text
(output)
```
-->

## Design
- `functions.cpp` holds one function per statistic, each a single pass over the data.
- No external libraries; standard C++17 only.
