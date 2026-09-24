# Joshua Angulo González

Machine learning engineer and data scientist in Culiacán, Mexico (UTC-7).

Most of my work sits between data and production: collecting real-time data, training models on it, and writing the code that runs those models live. I also build LLM products, mainly agents and RAG.

## What I'm working on

**Quantitative research on crypto-market data** (2026 to present). A recorder on AWS EC2 has captured 38.8M live market events, stored as Parquet on S3. I train XGBoost, LightGBM and CatBoost models on that data with walk-forward, purged validation and tune them with Optuna. Models reach a Rust engine in stages: shadow mode first, then a small canary, with drift monitoring and a test that checks Python and Rust produce the same scores.

**LuckAgents** (2024 to present). A multi-tenant SaaS where AI agents answer a business's customers on WhatsApp, book appointments and take payments. I built it alone: agents with tool calling, RAG on pgvector, 20 background workers, idempotent payments with Stripe and Mercado Pago, and 1,066 automated tests. Meta approved it as a WhatsApp Tech Provider. Before launch I audited the code myself and fixed an account-takeover risk and 31 access-control gaps.

Both codebases are private. Two things you can read today:

- [case-studies](https://github.com/joshua-angulo/case-studies): how each system is built, the decisions behind it and what I would change.
- [multi-tenant-rls](https://github.com/joshua-angulo/multi-tenant-rls): a small, runnable version of the tenant-isolation pattern from LuckAgents, with 16 tests, most of them negative.

## Tools

Python, SQL, pandas, Polars, DuckDB · scikit-learn, XGBoost, LightGBM, CatBoost, PyTorch, Optuna · AWS (EC2, S3), Docker, GitHub Actions · TypeScript, Node.js, React, Rust · LLM agents, RAG, pgvector

I use Claude Code, Codex and Cursor every day. I plan the work, review every change they make and test it.

## Contact

I'm looking for a long-term role in machine learning, data science or AI engineering, remote on US hours or on-site in Mexico.

joshuaangulo10@gmail.com · [LinkedIn](https://www.linkedin.com/in/joshuaangulogonzalez/)

---

Soy ingeniero de machine learning y científico de datos en Culiacán, Sinaloa. Trabajo con datos en tiempo real, con los modelos que se entrenan sobre ellos y con los sistemas que los llevan a producción. También construyo productos con LLM. Busco un puesto de largo plazo, remoto o presencial.
