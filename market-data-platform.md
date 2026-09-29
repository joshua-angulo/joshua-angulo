# Real-time market data platform

A system that records live crypto market data on AWS, trains models on it and runs those models against the live feed from an async Rust engine. I've been building it alone since early 2026. The code is private and I leave out the venue, instruments, thresholds and results. This note is about how it's built.

## Two halves that must agree

The research half is Python: a recorder on an EC2 instance writes Parquet to S3 (38.8M events and 9.3 GiB so far), and Polars and DuckDB do the analysis. Models are XGBoost, LightGBM and CatBoost tuned with Optuna. The runtime half is Rust on Tokio: it reads WebSocket feeds, rebuilds order books, scores the models and applies risk limits under a latency budget.

Because models are trained in one language and run in another, a contract test scores the same golden vectors in both and fails CI if they differ by anything. A different feature order or one rounding step would make the backtest describe something other than what runs.

## Rules I follow

Money is never an `f64`. Every price and size path uses `rust_decimal`. Floats only appear where rounding can't matter, such as aggregate limits.

Evaluation data is used once. Before I open a test window I write down which days, which frozen model hashes and which bars the model has to clear. Once I've looked at a day, it moves to training for good, and a log says whether each day is still sealed. Validation is walk-forward with purging at every boundary. Without this a backtest ends up measuring how many times you peeked.

New models go through shadow mode first: scoring live data without acting, while I compare drift and latency against what the backtest predicted. Only after that do they get a small canary.

Every safety check has a test that injects bad data and confirms the system stops, because a check that has never failed might just be switched off. The engine starts in dry-run and stays there unless the recorder is running, the book is in sync and a separate confirmation is given.

Every result links to a commit. Verdicts go in an append-only log with the evidence committed and hashed. A number that only exists in an ignored folder doesn't count.

## Outside markets

The same constraints show up anywhere money or irreversible decisions are involved: amounts you can't round, retries that must not repeat an effect, safety checks that need their own tests, and a clear line between what was measured and what was assumed. Here the mistakes just surface faster.
