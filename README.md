# Skyler Southern

Technical co-founder and lead AI engineer at Golden Sky Holdings, a real estate operator in Indiana with about 600 rental units under management. Since April 2026 I have built, and now operate, the multi-agent LLM platform that runs the company's back office in production: vendor payables, utility bills, construction estimating and billing, payroll evidence, multi-entity accounting, leasing, document processing and property tax.

The platform lives in a private monorepo. What it is made of:

- TypeScript, Node 24, PostgreSQL on Supabase with row-level security, a React PWA where staff review exceptions
- Hundreds of agents, each with a policy file and a risk tier from T0 (observe only) to T3 (moves money); money paths sit behind idempotent writes, dry-run gates, a kill switch and a protected-core CI guard that agents cannot edit
- One unattended payment lane that pays utility bills only when three live reads agree to the cent inside a fifteen-minute window
- 14 LLM provider adapters behind a router with budgets and cost telemetry; every model change runs in shadow first, judged by a cross-model LLM-as-judge, and passes a promotion gate before it ships
- RAG on pgvector with local embeddings and synthesis, served behind per-user auth
- Self-hosted CI runner farm, three-node Proxmox cluster, Vault, Tailscale, OpenTelemetry
- Most of the code is written by AI coding agents (Claude Code, Codex) that I direct under a lifecycle, review and evaluation system I designed

Write-ups on the way: the architecture and safety layer; an August 2026 ledger incident and its repair; why exact-match agreement is the wrong metric for promoting one model over another.

Before this: seven years of customer-facing B2B sales, five of them technical. Managing broker of the company's property management arm since 2019, so the rules the agents encode are ones I wrote and enforced first.

LinkedIn: https://www.linkedin.com/in/skyler-southern/
