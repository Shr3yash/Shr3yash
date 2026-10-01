# Shreyash Bhatkar

MCS @ UIUC (GPA 4.0). Graduate researcher at SSAIL under Prof. Minjia Zhang. Before that, ~2.5 years at Oracle on telecom billing systems that handled 10M+ transactions a day.

I spend most of my time on LLM serving and RL post-training infra: speculative decode correctness, LoRA/weight-sync edge cases, and the places where train and serve disagree under load.

[LinkedIn](https://linkedin.com/in/shr3yash) · [Portfolio](https://shr3yash.github.io) · [bhatkar3@illinois.edu](mailto:bhatkar3@illinois.edu)

---

## Right now

**SSAIL** — GRPO post-training for agentic coding models on NCSA DeltaAI and AWS, with SWE-Bench Verified eval in Docker sandboxes. Recent debugging: an NCCL weight-sync hang that only showed up under certain topologies, and a fake 3.8× "speedup" that was really asymmetric GPU allocation.

**Upstream contributions** (vLLM, SGLang, verl) — correctness fixes on the serving/RL path:
- vLLM: reject chat turns the Jinja template silently drops instead of returning 200 with a truncated prompt
- vLLM: Model Runner V2 LoRA + speculative decode (logits / lm_head row alignment)
- vLLM: skip plain draft speculation past an independent draft model's `max_model_len` instead of CUDA-IMA'ing
- verl: FSDP hybrid-engine sleep/wake sync for merged LoRA (level-1 path)
- SGLang: Falcon-H1 tied LM-head — avoid in-place `.float()` on the shared head

---

## Selected projects

### Distributed LLM inference
`Python` · `CUDA` · `PyTorch` · `vLLM` · `Ray Serve`

Continuous batching + PagedAttention for Llama-3-8B. About **2.4×** throughput vs naive batching, P99 under **800ms** at 100+ concurrent requests. Multi-GPU Ray Serve with CUDA/KV profiling cut peak GPU memory ~**22%**.

### Adaptive decoding runtime
`Python` · `PyTorch` · `vLLM`

Routes between single- and multi-token generation using entropy, margin, and n-best agreement. ~**2.3×** fewer decoding steps and ~**28%** lower long-form latency in the setups I measured. Batched LLM-as-judge cut the eval loop from ~90s to ~3.3s per sample.

### ScDFS (distributed file system)
`C++` · `Cassandra` · `PostgreSQL`

Consistent hashing, 3× replication, recovery under simulated node failure. Indexed metadata + multithreaded ring lookups cut query latency ~**40%** in that setup.

### Synchronized code editor
`TypeScript` · `React` · `Node` · `WebSockets` · `Redis`

OT-based collab editor. Sub-100ms sync in testing, load-tested past 300 concurrent users. Tests focused on disconnect and concurrent-edit paths.

### Fraud detection pipeline
`Python` · `PySpark` · `Kafka` · `MLflow`

Streaming ETL + scoring at 10K+ txn/sec with sub-second micro-batch decisions.

---

## Stack

**Languages** — Python, C++, Java, Go, Kotlin, TypeScript, Rust, SQL

**ML / inference** — PyTorch, vLLM, SGLang, TRL/GRPO, FSDP2, CUDA, Ray, TensorRT-LLM

**Backend** — Spring Boot, FastAPI, Node, gRPC, Kafka, Redis, Postgres, Cassandra

**Infra** — AWS, GCP, OCI, K8s, Docker, Terraform, Slurm/HPC, Prometheus, Grafana

---

## Experience

**Oracle** — Software Engineer, Associate Consultant, Jul 2023 – Jan 2026 (Batelco Telecom, PPC Retail)

Eight Java/Kotlin microservices and 20+ REST APIs for subscription/billing/account flows at 10M+ daily transactions. Tracked down gRPC HTTP/2 stream exhaustion via Prometheus and retuned Istio pools (~37% higher throughput, ~12% lower P95 in that engagement). Led a 4-person team on a LangChain + Cohere docs assistant used by 500+ engineers.

**Nibha Tech Solutions** — AI Research Intern, Dec 2022 – May 2023

Feature engineering on 15GB+ / 25 years of market data; SARIMA + SHAP for forecasting under normal and stress regimes.

---

## Education

**UIUC** — MCS, GPA 4.0/4.0

**VIT Pune** — B.Tech Electronics & Telecommunication, CGPA 8.82/10

Oracle certs: Generative AI Professional, Data Science Professional, Machine Learning (Autonomous Database).

---

## Elsewhere

Chess ([chess.com](https://www.chess.com/member/jujutsucarlsen) · [lichess](https://lichess.org/@/sndstrm)), powerlifting, cooking, drawing.

Email or open an issue if you want to talk about serving systems, RL infra, or anything above.
