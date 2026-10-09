# Joshua Angulo

TypeScript and Python for most things, Rust when it has to be exact or fast. Over the last three years I built software for a California city and two systems of my own. Looking for a team to join, remote or in site.

**LuckAgents** (2024 to 2026). An AI assistant on a small business's WhatsApp number. It answers customers and books appointments, and it can take a payment through Stripe or Mercado Pago. Next.js and React apps, an Express API, Postgres with row-level security, Redis with 20 BullMQ workers, LLM agents with tool calling and RAG. Meta approved it as a WhatsApp Tech Provider. I audited the whole thing myself and fixed what I found. The code is private; [how it's built and what the audit turned up](https://github.com/joshua-angulo/joshua-angulo/blob/main/luckagents.md).

**Market data platform** (2026, ongoing). A recorder on EC2 and S3 for live market data, gradient-boosting and PyTorch models validated walk-forward on that data for HFT-Quant Markets, and an async Rust engine that scores them on live feeds. Also private; [notes](https://github.com/joshua-angulo/joshua-angulo/blob/main/market-data-platform.md).

**City of Lynwood, California** (2024, contract). A chat and phone assistant for residents in Python, FastAPI, Twilio and GPT, with handoff to staff.

Public: [pg-tenant-rls](https://github.com/joshua-angulo/pg-tenant-rls). The tenant isolation from LuckAgents cut down to about 300 lines of SQL and TypeScript and 16 tests, most of which try to read another tenant's rows. `docker compose up`, `npm test`, two minutes.

joshuaangulo10@gmail.com · [LinkedIn](https://www.linkedin.com/in/joshuaangulogonzalez/)

Hablo español; escríbeme en el idioma que prefieras.
