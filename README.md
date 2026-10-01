## Hi there 👋

I'm a python developer with a huge focus on security research, data analysis and also AI development

Featured projects

🧠 Desire Axis: interpretability study of internal states in LLMs

An adaptation of The Pain Axis (Tagliabue, Dung & Berg, 2026) that asks whether language models represent sexual desire as a distinct internal state, not just sex as a topic. It extracts a linear direction from the residual stream of Qwen 2.5 7B and 32B and tests it against matched controls. Work in progress.

Controls built from failure: two rounds of results exposed confounds (first sexual content, then first-person sex without desire), and each was fixed with a new control set plus a held-out set never used to build the vector
Current result: on Qwen 2.5 32B, the direction separates desire from held-out sex-without-desire by about 1.0 z, matching the size of the original paper's key gap. Desire phrased without explicit words still scores clearly positive
Honest scope: this is evidence of a distinct concept representation, not of experience. Self-other tests, steering and behavioral experiments are next
Engineering: extraction adapted to fit a 32B model on one Colab A100 using Hugging Face forward hooks, with resumable stages that write to Drive and a mid-depth layer window to avoid fragile layer picks

PyTorch · Transformers · scikit-learn · PEFT · Colab · pytest


🤖 SupportOps Agent: AI support agent with tool calling

A customer-support agent that picks typed business tools, checks their results and returns structured answers, with a FastAPI backend and a web console that shows every tool call.

Provider-agnostic: swap between OpenAI, Anthropic or an offline mock provider with one setting
Safety boundaries: server-side permission checks stop one customer from reading another's data, and refunds, cancellations and password resets require explicit approval
Reliability: bounded agent loop, retries with exponential backoff on reads, single-attempt writes, and controlled failure injection for testing
Evaluated: scenario evals report tool-selection accuracy, unauthorized actions and confirmation violations

FastAPI · Pydantic · SQLAlchemy · OpenAI · Anthropic · pytest

🔎 SexAndRag: RAG retrieval benchmark on noisy dialogue

A retrieval pipeline and benchmark built on about 40,000 lines of messy TV subtitle data. It compares BM25, dense search (BGE-M3) and hybrid retrieval across three chunk sizes.

Data cleaning with provenance: named, recorded cleaning rules, and every chunk traces back to its exact source rows
Honest evaluation: 60 human-approved questions with row-level evidence, plus a frozen dev/test split that the code refuses to touch without an explicit flag
Reproducible: pinned corpus checksum, pinned model commit and file digests, and content-keyed caches
Engineering: one CLI, mypy --strict, four levels of tests, and CI that runs without the dataset or model

sentence-transformers · BGE-M3 · rank_bm25 · Reciprocal Rank Fusion · pytest

📦 Harvester: dataset collection for contamination-free AI benchmarks

Finds recent, niche STEM datasets for building AI coding benchmarks that models can't have memorized.

Filters by date, license and weighted relevance, and records a reason for every rejection
Size-bounded, zip-bomb-safe downloads
Reads JavaScript-rendered discussion threads with Playwright
Source-agnostic pipeline with offline tests and CI

Playwright · Kaggle API · Pydantic · pytest

Other projects
Slopster Generator: desktop creature-concept generator with weighted trait files and a CI-built Windows executable
HashNote: #100DaysOfCode project building a linked-notes app from a hand-written hash map upward
Caesar Cipher: small Tkinter app and tested library
What I build
AI agents with tool calling, permissions, approval steps and evals
RAG and search systems with measurable retrieval quality
Data pipelines and scrapers for messy, real-world sources
Python automation with tests, typing and CI
Tools

Python · FastAPI · Pydantic · SQLAlchemy · pytest · mypy · ruff · OpenAI and Anthropic APIs · sentence-transformers · Playwright · GitHub Actions
