# Joshua Angulo

Culiacán, Mexico (UTC-7). TypeScript and Python for most things, Rust when it has to be exact or fast. Over the last three years I built two systems on my own and I'm now looking for a team to join, remote or here in Mexico.

**LuckAgents** (2024 to 2026, shelved). An AI assistant on a small business's WhatsApp number. It answers customers and books appointments, and it can take a payment through Stripe or Mercado Pago. Next.js and React apps, an Express API, Postgres with row-level security, Redis with 20 BullMQ workers, LLM agents with tool calling and RAG. Meta approved it as a WhatsApp Tech Provider. In July I audited the whole thing, fixed what I found, and decided not to launch it. The code is private; [how it's built and what the audit turned up](https://github.com/joshua-angulo/joshua-angulo/blob/main/luckagents.md).

**Market data platform** (2026, ongoing). A recorder on EC2 and S3 that has logged 38.8M live crypto market events, gradient-boosting models validated walk-forward on that data, and an async Rust engine that scores them on live feeds. Also private; [notes](https://github.com/joshua-angulo/joshua-angulo/blob/main/market-data-platform.md).

**City of Lynwood, California** (2023 to 2024, contract). A chat and phone assistant for residents in Python, FastAPI, Twilio and GPT, with handoff to staff.

Public: [pg-tenant-rls](https://github.com/joshua-angulo/pg-tenant-rls). The tenant isolation from LuckAgents cut down to about 300 lines of SQL and TypeScript and 16 tests, most of which try to read another tenant's rows. `docker compose up`, `npm test`, two minutes.

joshuaangulo10@gmail.com · [LinkedIn](https://www.linkedin.com/in/joshuaangulogonzalez/)

Hablo español; escríbeme en el idioma que prefieras.
