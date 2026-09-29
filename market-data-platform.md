# Market data platform

Records live crypto market data on AWS, trains models on it, and runs those models on the live feed from a Rust engine. I started it in early 2026 and it's still going. The code is private, and I leave out the venue, instruments, thresholds and any results. This is about how it's built.

The research half is Python. A recorder on an EC2 instance writes Parquet to S3, 38.8M events and 9.3 GiB so far, and Polars and DuckDB do the analysis. Models are XGBoost, LightGBM and CatBoost, tuned with Optuna and validated walk-forward with purging at every boundary.

The runtime half is Rust on Tokio. It reads WebSocket feeds, rebuilds order books, scores the models and applies risk limits inside a latency budget.

Training in one language and running in another is the obvious place to get burned, so a contract test scores the same golden vectors in both and fails CI on any difference. One rounding step or a different feature order would make the backtest describe a system that doesn't exist.

Some rules I ended up with.

Money is never an `f64`. Every price and size path uses `rust_decimal`. Floats only show up where rounding can't matter, like aggregate limits.

Evaluation data gets used once. Before I open a test window I write down which days, which frozen model hashes and which bars the model has to clear. Once I've looked at a day it moves to training for good, and a log says which days are still sealed. Without this a backtest ends up measuring how many times you peeked.

New models score live data in shadow mode first, without acting, while I compare drift and latency against what the backtest predicted. Only after that does one get promoted.

Every safety check has a test that feeds it bad data and confirms the system stops. A check that has never failed might just be switched off. The engine starts in dry-run and stays there unless the recorder is running, the book is in sync and it gets a separate confirmation.

Every result points to a commit. Verdicts go in an append-only log with the evidence committed and hashed. A number that only exists in an ignored folder doesn't count.

None of this is specific to markets. Amounts you can't round, retries that must not repeat an effect, safety checks that need their own tests, and a clear line between what was measured and what was assumed show up in any system that touches money. Here the mistakes just surface faster.
