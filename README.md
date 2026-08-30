<h1 align="center">Hi, I'm Sai Dheeraj Gollu 👋</h1>
<p align="center"><b>Systems engineer who gets uneasy when things merely <i>look</i> fine.</b></p>

<p align="center">
  <a href="https://linkedin.com/in/sai-dheeraj-gollu"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="https://saidheerajgollu.com"><img src="https://img.shields.io/badge/Portfolio-000000?style=flat&logo=vercel&logoColor=white" alt="Portfolio"></a>
  <a href="mailto:gollusaidheeraj@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white" alt="Email"></a>
</p>

---

### About Me

Most of my career has been chasing the bug that only shows up on fire #6,670 — a log row that quietly rewrites itself into a 14MB JSON blob, a Kafka message that vanishes once in ten thousand, a single third-party API outage that shouldn't have taken the whole pipeline down with it but did. I build backend and distributed systems for a living, and then, mostly for fun, I go find the same disease living in other people's codebases.

Right now that means shipping fintech infrastructure at **Altrion**, sustaining over a million points a second with zero data loss in a C++ engine I'm building from scratch, and finishing an M.S. in Software Engineering at San José State University. In between, I read production code that isn't mine and occasionally fix what's wrong with it — four merged PRs into Andrew Ng's `openworker`, an accessibility fix into a 30k★ UI library, and a diagnosis + credited fix for a data-loss bug in an agent harness with 14k stars.

---

### Right Now

- 🏗️ Building the multi-provider data layer at **Altrion** — Plaid, Coinbase, Stripe, Moralis DeFi, 200+ financial instruments, sub-200ms under concurrent load
- ⚙️ Pushing **1.1M points/sec** through [TSDLite](https://github.com/Saidheerajgollu/tsdlite) with zero data loss under 8x burst overload
- 🎓 Finishing an M.S. in Software Engineering at San José State University — May 2026
- 🔍 Reading other people's production code and occasionally fixing what's silently broken in it

---

### Stack

| | |
|---|---|
| **Languages** | Python · Java · C++ · TypeScript · JavaScript · Go · SQL |
| **Backend & Systems** | FastAPI · Spring Boot · Node/Express · Apache Kafka · Concurrency & Multithreading · Unix/Linux |
| **AI / NLP** | LangChain · Claude API · RAG (BM25 + embeddings + RRF) · HuggingFace · BGE-large · ModernBERT |
| **Data** | PostgreSQL (composite indexing) · Redis · MongoDB · Neo4j · Elasticsearch |
| **Cloud & DevOps** | AWS EC2 · GCP (Vertex AI, A100s) · Docker · Kubernetes · GitHub Actions · Jenkins |
| **Frontend** | React 19 · TypeScript · Vite · Tailwind CSS · Recharts · Socket.IO |

---

### Featured Projects

**[TSDLite](https://github.com/Saidheerajgollu/tsdlite)** — large-scale time-series ingestion engine in C++20
Bounded ring buffer, concurrent data access, batched PostgreSQL writes. Sustains **1.1M points/sec** wire acceptance with zero data loss under 8x burst overload, **141k rows/sec** sustained DB throughput (35x faster than naive writes), 64 automated tests, full CI/CD, Docker/K8s.

**Thrilochana** — information retrieval & NLP platform, live on the App Store
A 6-stage hybrid retrieval pipeline (BM25, embeddings, Reciprocal Rank Fusion) hitting **95%+ accuracy** across 100+ document catalogs, plus a Plan-Execute-Reflect agentic harness spanning 54 tool integrations that cut processing time **97%** against a ground-truth evaluation layer.

**[job-hunter-project](https://github.com/Saidheerajgollu/job-hunter-project)** — self-hosted job aggregator
Polls ATS boards directly — Greenhouse, Lever, Ashby, Workday, SmartRecruiters, Workable, Recruitee — so matching roles arrive by push before they ever hit the big job boards. Next.js, Node/Express, Supabase Postgres.

---

### Professional Experience

**Software Engineer · Altrion** — Jul 2026 – Present, San Jose, CA
Full-stack fintech infrastructure in Python/FastAPI and React 19/TypeScript, shipped weekly to AWS EC2 via GitHub Actions. Designed a resilient integration layer across 10+ third-party APIs (Plaid, Coinbase, Stripe, Moralis DeFi) with per-step error isolation, so a single provider outage never fails the broader pipeline. Cursor-based incremental sync with per-source partial-failure handling — zero unplanned downtime across weekly releases.

**Software Engineer · Aviac Technologies** — Jan 2022 – Dec 2023, India
Distributed Java/Spring Boot microservices; cut API response time **30%** across 500+ daily requests with connection pooling and async processing. Diagnosed a silent Kafka message-drop defect via structured log analysis and fixed it with idempotent consumers and dead-letter routing, restoring **99.9%** event delivery across 3 services. Took test coverage from 40% to **90%**, ran 50+ code reviews, zero unplanned outages across 20+ Kubernetes releases.

---

### Open Source Contributions

**[andrewyng/openworker](https://github.com/andrewyng/openworker)** ★17k · Andrew Ng's agent harness — 4 merged PRs, listed contributor
- [#55](https://github.com/andrewyng/openworker/pull/55) rejected path-traversal session IDs in the conversation store
- [#56](https://github.com/andrewyng/openworker/pull/56) made the conversation loader tolerate one corrupt line instead of losing the whole `.jsonl`
- [#379](https://github.com/andrewyng/openworker/pull/379) fixed a race where a scheduled task could fire twice if an approval landed mid-tick
- [#24](https://github.com/andrewyng/openworker/pull/24) fixed inbox reply-intent parsing to key off the leading word instead of substring matching

**[heroui-inc/heroui](https://github.com/heroui-inc/heroui)** ★30k — [#6741](https://github.com/heroui-inc/heroui/pull/6741) merged, approved by a core maintainer
Removed stray `aria-label`s left on `aria-hidden` decorative icons — an accessibility fix.

**[yc-software/qm](https://github.com/yc-software/qm)** ★14k agent harness — credited co-author on a merged fix
Found that the Postgres-backed durable map JSON-stringifies into `jsonb`, which rejects NUL bytes and lone surrogate pairs — the exact kind of string the system's *own* truncation helpers manufacture when a clamp lands mid-emoji. Wrote the ADR describing the failure and the fix; the maintainer folded it into a merged batch PR crediting me as co-author.

**In review**
- [stanfordnlp/dspy #10301](https://github.com/stanfordnlp/dspy/pull/10301) — `configure_cache()` had no fallback when disk-cache init failed; added one
- [run-llama/llama_index #22857](https://github.com/run-llama/llama_index/pull/22857) — traced an nltk 3.10.3 hardlink guard that silently broke `punkt_tab`/RAKE keyword extraction, fixed it at the root instead of patching call sites

---

### Certifications

🎓 **Claude Certified Developer – Foundations**, Anthropic (Aug 2026)

---

<p align="center"><i>Always up for talking distributed systems, retrieval pipelines, or why your logs are lying to you.</i></p>
