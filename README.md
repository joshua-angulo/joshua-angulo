# Joshua Angulo

Software engineer in Culiacán, Mexico (UTC-7). TypeScript, Python and Rust. I've spent the last three years building two systems on my own, and I'm now looking for a team to build with.

## What I've built

**LuckAgents** (2024 to now, pre-launch). A SaaS that puts an AI assistant on a small business's WhatsApp number. It answers customers, books appointments and takes payments. Next.js and React apps, an Express/TypeScript API, Postgres with row-level security per customer, MongoDB, Redis with 20 BullMQ workers, Stripe and Mercado Pago, LLM agents with tool calling and RAG. Meta approved it as a WhatsApp Tech Provider. The code is private; [how it's built](https://github.com/joshua-angulo/joshua-angulo/blob/main/luckagents.md).

**A real-time market data platform** (2026 to now). A recorder on AWS EC2 and S3 that has captured 38.8M live crypto market events, a research stack in Polars, DuckDB and gradient boosting with walk-forward validation, and an async Rust engine that runs the models on live feeds. Private; [how it's built](https://github.com/joshua-angulo/joshua-angulo/blob/main/market-data-platform.md).

**City of Lynwood, California** (2023 to 2024, contract). A chat and phone assistant for residents in Python, FastAPI, Twilio and GPT, with handoff to city staff.

## Public code

[pg-tenant-rls](https://github.com/joshua-angulo/pg-tenant-rls): the tenant isolation from LuckAgents cut down to about 200 lines of SQL and TypeScript, with 16 tests, most of which try to read or write another tenant's data. Runs in two minutes with Docker.

## Contact

joshuaangulo10@gmail.com · [LinkedIn](https://www.linkedin.com/in/joshuaangulogonzalez/)

Hablo español; escríbeme en el idioma que prefieras.
