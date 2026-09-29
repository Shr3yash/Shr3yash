# Shreyash Bhatkar

**Systems and ML infrastructure.** I work on the layer where distributed systems meet machine learning — inference runtimes, multi-GPU training, and the backend services that keep both honest in production.

Currently a graduate researcher at **SSAIL (Supercomputing Systems & AI Lab)** at UIUC, working on agentic RL systems and LLM inference. Previously **2.5 years at Oracle** building telecom billing infrastructure that moved 10M+ transactions a day.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/shr3yash)
[![Portfolio](https://img.shields.io/badge/Portfolio-000000?style=flat-square&logo=vercel&logoColor=white)](https://shr3yash.github.io)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:bhatkar3@illinois.edu)

---

## What I'm working on

**Distributed RL post-training @ SSAIL** — Running GRPO post-training for agentic coding models across NCSA DeltaAI and AWS, with SWE-Bench Verified evaluation in persistent Docker sandboxes. Recent work: traced a reproducible NCCL weight-synchronization hang through controlled topology tests, and found an asymmetric GPU allocation hiding behind an apparent 3.8× framework speedup.

**LLM inference optimization** — Continuous batching, PagedAttention, KV-cache profiling, and adaptive decoding strategies. Mostly interested in the gap between a benchmark number and what actually happens under concurrent load.

---

## Selected projects

### [Distributed LLM Inference Engine](https://github.com/Shr3yash)
`Python` `CUDA` `PyTorch` `vLLM` `Ray Serve`

Continuous batching and PagedAttention for Llama-3-8B serving. **2.4× throughput** over naive batching with **P99 under 800ms** at 100+ concurrent requests. Multi-GPU Ray Serve deployment with CUDA and KV-cache profiling cut peak GPU memory **22%**.

### [Adaptive LLM Inference Runtime](https://github.com/Shr3yash)
`Python` `PyTorch` `vLLM` `Model Evaluation`

Decoding runtime that routes between single- and multi-token generation using entropy, probability margin, and n-best agreement signals. **2.3× fewer decoding steps**, **28% lower** long-form latency. Batched LLM-as-judge evaluation took the experiment loop from 90s to 3.3s per sample.

### [Scalable Distributed File System (ScDFS)](https://github.com/Shr3yash)
`C++` `Cassandra` `PostgreSQL` `Multithreading`

Consistent hashing with 3× replication and node-recovery protocols, built to hold availability and replica consistency across simulated failures. Multithreaded hash-ring lookups and indexed metadata cut query latency **40%**.

### [Synchronized Code Editor](https://github.com/Shr3yash)
`TypeScript` `React` `Node.js` `WebSockets` `WebRTC` `Redis`

Real-time collaborative editor using conflict-safe operational transforms. **Sub-100ms sync latency**, load-tested to **300+ concurrent users** at 99.9% uptime, with Jest coverage for the disconnect and concurrent-edit paths that break these systems in practice.

### [Real-Time Fraud Detection Pipeline](https://github.com/Shr3yash)
`Python` `PySpark` `Kafka` `MLflow` `Docker`

Streaming ETL and ML scoring at **10K+ transactions/sec** with sub-second risk decisions per micro-batch and MLflow experiment tracking.

---

## Stack

**Languages** — Python · C++ · Java · Go · Kotlin · TypeScript · Rust · SQL

**ML & Inference** — PyTorch · vLLM · SGLang · TRL/GRPO · FSDP2 · CUDA · Ray · TensorRT-LLM · quantization · LangChain · FAISS

**Backend & Distributed** — Spring Boot · FastAPI · Node.js · React · gRPC · REST · GraphQL · Kafka · Redis · PostgreSQL · Cassandra

**Infrastructure** — AWS · GCP · OCI · Kubernetes · Docker · Terraform · Airflow · Spark · Slurm/HPC · Prometheus · Grafana · CI/CD

---

## Experience

**Oracle** — Software Engineer (Associate Consultant), Jul 2023 – Jan 2026
Client engagements: Batelco Telecom, PPC Retail

Built 8 Java/Kotlin microservices and 20+ REST APIs for subscription, billing, and account-lifecycle workflows processing **10M+ daily transactions** at **99.95% correctness** under concurrent load. Traced gRPC HTTP/2 stream exhaustion through Prometheus and tuned Istio connection pools for **37% higher throughput** and **12% lower P95**. Led a 4-person team building a LangChain + Cohere documentation assistant used by **500+ engineers**, cutting hallucinations 41%.

**Nibha Tech Solutions** — AI Research Intern, Dec 2022 – May 2023

Engineered 30,000+ features from 25 years of market data across 15GB+ datasets; SARIMA forecasting with SHAP attribution reached **96.2% accuracy** in normal conditions, 76% under stress-test simulation.

---

## Education

**University of Illinois Urbana-Champaign** — Master of Computer Science, GPA 4.0/4.0
**Vishwakarma Institute of Technology, Pune** — B.Tech, Electronics & Telecommunication, CGPA 8.82/10

**Certifications** — Oracle Certified Generative AI Professional · Oracle Certified Data Science Professional · Oracle Certified Machine Learning (Autonomous Database)

---

## Elsewhere

Chess ([chess.com](https://www.chess.com/member/jujutsucarlsen) · [lichess](https://lichess.org/@/sndstrm)), powerlifting, cooking, drawing.

Open an issue or email me if you'd like to talk about inference systems, distributed training, or anything above.
