# Awesome-AI-Memory

- **Repository:** IAAR-Shanghai/Awesome-AI-Memory
- **URL:** https://github.com/IAAR-Shanghai/Awesome-AI-Memory
- **Stars:** 783 | Forks: 70 | Contributors: 25
- **License:** Apache-2.0
- **Last Updated:** 2026-04-22
- **Date Clipped:** 2026-04-26

---

## Overview

A curated, continuously updated knowledge base on AI memory for LLMs and agents. Systematically covers long-term memory, reasoning, retrieval, memory-native system design, evaluation benchmarks, and real-world application practices.

## Scale

- **349 papers** across 4 categories:
  - Survey: 8 papers
  - Framework & Methods: 242 papers
  - Datasets & Benchmark: 53 papers
  - Systems & Models: 38 papers
- **97 open-source projects** (43 in curated table)
- **20 multimedia resources** (YouTube + Bilibili)

## Core Concepts (from README)

### Memory System Architecture (4 Layers)
1. **Storage Layer** — Vector DBs (Chroma, Weaviate), graph DBs, hybrid
2. **Processing Layer** — Embedding models, summarization, segmenters
3. **Retrieval Layer** — Multi-stage retrievers, reranking, context injectors
4. **Control Layer** — Priority managers, forgetting controllers, consistency coordinators

### Memory Operations (5 Atomic)
- **Writing** — Dialogue → vectors, with summarization
- **Retrieval** — Query → Top-K relevant memories
- **Updating** — Similarity match → replace/enhance
- **Deletion** — User-instructed or automatic (privacy expiration)
- **Compression** — Merge related memories into summaries

### Memory Classification (4 Dimensions)
- **By Access Frequency:** Working → Frequent → Archived
- **By Structure:** Structured → Semi-structured → Unstructured
- **By Sharing Scope:** Personal → Team → Public
- **By Temporal Validity:** Permanent → Temporary → Time-sensitive

### Memory Types
- **Parametric Memory** — Knowledge in model weights
- **Explicit Memory** — Raw text in vector DBs
- **Short-Term Memory** — Context window (KV cache, compression, sliding window)
- **Long-Term Memory** — Persistent external (auto-summarization, context binding, multimodal)
- **Episodic Memory** — User interaction history (identity, trajectory, emotion, preference evolution)

### Memory Forgetting Mechanisms
- **Selective Forgetting (Machine Unlearning)** — Remove specific training data influence
- **Privacy-Driven** — Auto-identify/delete PII, set expiration
- **Memory Decay** — Lower priority of infrequently accessed
- **Conflict-Driven** — Update/discard when new evidence contradicts

### Memory Retrieval Pipeline
1. Semantic pre-filtering (vector similarity → Top-100)
2. Contextual reranking (current query context)
3. Temporal filtering (prioritize recent)

### Memory Compression Techniques
- Content-level: Extract core, discard redundancy
- Representation-level: Vector quantization, dimensionality reduction
- Organization-level: Clustering, hierarchical structures
- Knowledge Distillation: Transfer external → parametric memory

## Key Survey Papers

1. [2026-04-09] **Externalization in LLM Agents** — Memory externalizes cross-time state; skills externalize procedural capability; protocols externalize interaction structure
2. [2026-03-05] **Beyond the Context Window** — At 100k context, memory systems surpass long-context models in cost efficiency after ~10 turns
3. [2026-03-02] **Modular Memory is the Key to Continual Learning Agents** — Modular architecture integrating in-context learning with weight updates
4. [2026-03-02] **Emerging Human-like Strategies for Semantic Memory Foraging in LLMs** — Confirms human-like strategic memory search in LLMs
5. [2026-02-26] **Toward Personalized LLM-Powered Agents** — Taxonomy: user profile modeling, memory, planning, action execution
6. [2025-04-23] **From Human Memory to AI Memory** — Three-dimensional taxonomy: object, form, time
7. [2025-04-02] **Digital Forgetting in Large Language Models** — Unlearning methods for privacy/copyright/ethics
8. [2025-01-12] **Human-inspired Perspectives: AI Long-term Memory** — Adaptive long-term memory cognitive architecture (SALM)

## Open Source Systems (43 projects)

| System | Date | GitHub |
|--------|------|--------|
| Zep | 2023-05 | github.com/getzep/zep |
| Agentmemory | 2023-07 | github.com/elizaOS/agentmemory |
| Cognee | 2023-10 | github.com/topoteretes/cognee |
| Letta (MemGPT) | 2023-10 | github.com/letta-ai/letta |
| Supermemory | 2024-02 | github.com/supermemoryai/supermemory |
| Memary | 2024-04 | github.com/kingjulio8238/Memary |
| Second-Me | 2024-06 | github.com/mindverse/Second-Me |
| Mem0 | 2024-07 | github.com/mem0ai/mem0 |
| Memobase | 2024-10 | github.com/memodb-io/memobase |
| Puppyone | 2024-12 | github.com/puppyone-ai/puppyone |
| LangMem | 2025-01 | github.com/langchain-ai/langmem |
| A-Mem | 2025-02 | github.com/agiresearch/A-mem |
| Mirix | 2025-04 | github.com/Mirix-AI/MIRIX |
| MemEngine | 2025-05 | github.com/nuster1128/MemEngine |
| MemOS | 2025-05 | github.com/MemTensor/MemOS |
| MemoryOS | 2025-05 | github.com/BAI-LAB/MemoryOS |
| ReMe | 2025-06 | github.com/agentscope-ai/ReMe |
| Memori | 2025-07 | github.com/MemoriLabs/Memori |
| MemU | 2025-08 | github.com/NevaMind-AI/memU |
| MemMachine | 2025-08 | github.com/MemMachine/MemMachine |
| MineContext | 2025-09 | github.com/volcengine/MineContext |
| TiMem | 2025-10 | github.com/TiMEM-AI/timem |
| EverMemOS | 2025-10 | github.com/EverMind-AI/EverMemOS |
| Hindsight | 2025-12 | github.com/vectorize-io/hindsight |
| MAGMA | 2026-01 | github.com/FredJiang0324/MAMGA |
| MemClaw | 2026-03 | github.com/Felo-Inc/memclaw |
| SwarmVault | 2026-04 | github.com/swarmclawai/swarmvault |
| SkillClaw | 2026-04 | github.com/AMAP-ML/SkillClaw |
| ToolPipe | 2026-04 | github.com/COSAI-Labs/toolpipe-mcp-server |

## Paper Distribution by Year

| Year | Count |
|------|-------|
| 2015-2023 | 14 |
| 2024 | 36 |
| 2025 | 99 |
| 2026 (to Apr) | 180 |

## Top Research Tags (by paper count)

1. Long-term Memory: 90
2. Memory Framework: 53
3. Benchmark: 43
4. Model Architecture: 42
5. Memory Retrieval: 40
6. Memory Management: 37
7. Memory Systems: 37
8. Memory Mechanisms: 24
9. Multi-agent: 23
10. Graph-based: 17
