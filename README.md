# Shkumbin Sherifi — AI Infrastructure Engineer

> Building local-first inference systems: model deployment, retrieval pipelines, and speech recognition for low-resource languages.
> Currently designing reproducible fine-tuning workflows and multi-model routing architectures on Apple Silicon.

---

## Systems

### AI & Simulation

**NFL Simulator Platform**
Multi-service simulation engine for player evaluation and roster analysis. Runs entirely on Apple Silicon via MLX.

- <120s full pipeline: draft generation → player embeddings → season sim → progression → contract negotiation
- DuckDB + ChromaDB for structured and vector storage across 32 teams, ~1,700 players
- PyTorch VAE for latent player representations, used in similarity search and trade valuation
- 10-season franchise sim in ~16s — full playoffs, free agency, salary cap, regression
- Tech: Next.js, Python, PyTorch, Docker, ChromaDB, MLX, DuckDB, RAG

**Albanian Speech-to-Text**
Transcription pipeline for Kosovo Albanian. Audio in → text out → human-corrected → fine-tuning loop.

- 901 curated YouTube audio sources, segment-level transcription with Faster-Whisper
- Closed-loop pipeline: user corrections feed back as fine-tuning data
- SQLite observability: inference latency, correction rates, WER/CER per model size
- Configurable model size from tiny to large-v3, language auto-detect with re-ranking
- Tech: Whisper, Python, ASR, Faster-Whisper, Audio Processing, Web UI

---

### Research

**Local-First AI on Apple Silicon** *(Active)*
- MLX inference with oMLX serving layer on M4 Pro 48GB
- Quantization tradeoffs: Q4_K_M vs Q8_0 vs F16 for local deployment
- RAG pipeline performance: chunking strategies, embedding models, retrieval latency
- Multi-model routing: cost-aware dispatch across local and cloud providers

**LoRA Fine-Tuning on Apple Silicon** *(Prototype)*
- Standardized configs: dataset formatting, training params, evaluation
- Quality tradeoffs: rank, alpha, dataset size vs output coherence
- Memory usage and training time across M-series chips

---

### Infrastructure Operations

**Local-First Infrastructure: Hermes Operator Environment**
Production-grade deployment and performance tuning of the open-source Nous Research Hermes Agent framework on local Apple Silicon. Focus: inference orchestration, provider routing, and lifecycle management — not framework development.

- Inference Orchestration: Configured local oMLX serving layer as primary backend, forcing token caching entirely into RAM to bypass quantization bottlenecks
- Provider Routing Mesh: Resilient multi-model routing with cost/latency-aware fallback paths bridging local execution to external API nodes under memory pressure
- Task & Context Management: SQLite Kanban layer for automated background cron jobs, localized context compilation with zero data leaving the host machine

---

### Production Web Systems

- **Nen Driten Islame** — E-commerce + operational admin system (Next.js, Supabase)
- **Gloweb** — Client-facing web systems and backend integrations (React, TypeScript, Node.js,)
- **Arbnori Engineering** — Multilingual business platform with deployment automation (Next.js, Node.js)

---

## Contact

Open to contract work, research collaboration, and infrastructure consulting.

**Email:** [shkumbins@protonmail.com](mailto:shkumbins@protonmail.com)

**Portfolio:** [shkumbins.dev](https://shkumbins.dev)
