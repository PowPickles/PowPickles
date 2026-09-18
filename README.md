# Skyler Southern

Technical co-founder and head of AI at Golden Sky Holdings, a real estate operator in Indiana with about 600 rental units under management. Since April 2026 I have led the build of, and now operate, the multi-agent LLM platform that runs the company's back office in production: vendor payables, utility bills, construction estimating and billing, payroll evidence, multi-entity accounting, leasing, document processing and property tax.

The platform lives in a private monorepo. What it is made of:

- PostgreSQL on Supabase with row-level security, and a React PWA where staff review exceptions with the evidence attached
- About 240 agents that declare a risk tier from T0 (observe only) to T3 (moves money); money paths sit behind idempotent writes, dry-run defaults, fail-closed validation, a kill switch and a protected-core CI guard that agents cannot edit
- One utility-payment lane without per-payment approval that pays only when three live reads agree to the cent inside a fifteen-minute window
- Eight LLM providers behind one router with budgets and cost telemetry; model challengers run in shadow, judged by a cross-model LLM-as-judge, before a promotion gate
- RAG on pgvector with local embeddings and synthesis, served behind per-user access control
- Self-hosted git, CI and database, secrets management, OpenTelemetry
- Most of the code is written by AI coding agents, mainly Claude Code, that I direct under a work-tracking, review and evaluation system I designed

Write-ups on the way: the architecture and safety layer; an August 2026 ledger incident and its repair; why exact-match agreement is the wrong metric for promoting one model over another.

Before this: seven years of customer-facing B2B sales, five of them technical. Managing broker of the company's property management arm since 2019, so the rules the agents encode are ones I wrote and enforced first.

LinkedIn: https://www.linkedin.com/in/skyler-southern/
