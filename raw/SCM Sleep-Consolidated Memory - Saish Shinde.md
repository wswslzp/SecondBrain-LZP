# SCM: Sleep-Consolidated Memory with Algorithmic Forgetting for Large Language Models

- **Author:** Saish Shinde (Clyrai IP Studio)
- **Date:** 2026-04-22
- **URL:** https://arxiv.org/abs/2604.20943
- **HTML:** https://arxiv.org/html/2604.20943v1

---

## Abstract & Core Contribution

SCM is a **brain-inspired memory architecture for LLMs** that implements five neuroscience-derived components:
1. **Limited-capacity working memory** (7 items, per Miller's Law)
2. **Multi-dimensional importance tagging** (4D: novelty, emotional valence, task relevance, repetition)
3. **Offline sleep-stage consolidation** (distinct NREM and REM phases)
4. **Intentional value-based forgetting**
5. **Computational self-model** for introspection

**Key results:** Perfect recall (22/22 facts) over 10-turn conversations, **90.9% memory noise reduction**, sub-millisecond search latency with hundreds of stored concepts.

---

## Problem Statement

Current LLM memory approaches all have critical shortcomings:

- **Context windows:** Bounded by token budgets; degradation when relevant info is mid-sequence ("Lost in the Middle" problem)
- **RAG/Vector DBs:** Grow indefinitely with no importance prioritization, consolidation, or forgetting
- **MemGPT:** OS-metaphor tiered storage but no biological memory processes (no sleep consolidation, no synaptic pruning)
- **Mem0:** Extracts facts and retrieves by similarity but is "awake-only" — never consolidates offline or intentionally forgets

> "The human memory system is not an append-only database. It is a dynamic, self-organizing architecture composed of multiple interacting subsystems."

---

## Feature Comparison

| Feature | MemGPT | Mem0 | WSCL | **SCM** |
|---|---|---|---|---|
| Working memory limit | ✗ | ✗ | ✗ | **✓ (7 items)** |
| Multi-dimensional importance | ✗ | △ (1D) | ✗ | **✓ (4D)** |
| NREM consolidation | ✗ | ✗ | ✓ | **✓** |
| REM dreaming | ✗ | ✗ | ✓ | **✓** |
| Intentional forgetting | ✗ | ✗ | ✗ | **✓** |
| Self-model | ✗ | ✗ | ✗ | **✓** |
| Multi-agent sync | ✗ | ✗ | ✗ | **✓** |

---

## Architecture & Methods

### System Overview

Five interconnected modules process input during **wake phases** and reorganize memory during **sleep phases**:

1. **MeaningEncoder** → structured concepts with typed relations
2. **ValueTagger** → multi-dimensional importance scores
3. **WorkingMemory** → fast, limited-capacity buffer (7 items)
4. **LongTermMemory** → persistent semantic graph (NetworkX)
5. **SleepCycle** → NREM consolidation, REM dreaming, intentional forgetting

### MeaningEncoder

- Uses **Llama 3.2** (2B params, Q4_K_M quantized) locally via Ollama for concept extraction
- **384-dimensional embeddings** from `all-MiniLM-L6-v2`
- Concept types: person, preference, fact, event, object, location, abstract
- Relation types: `has_property`, `prefers`, `related_to`, `contradicts`, `causes`, `part_of`
- Falls back to regex heuristics if LLM unavailable
- **All inference is local** — no user data leaves the machine

### ValueTagger (4D Importance Vector)

**Novelty** — how unexpected relative to existing memory:
$$v_{\text{novelty}}(c) = 1 - \max_{c' \in \mathcal{M}} \frac{\mathbf{e}_c \cdot \mathbf{e}_{c'}}{\|\mathbf{e}_c\| \|\mathbf{e}_{c'}\|}$$

**Emotional valence** — sentiment mapped from LLM output ∈ [-1, 1]

**Task relevance** — cosine similarity with current conversational goal embedding

**Repetition** — normalized access frequency

**Composite importance score:**
$$I(c) = 0.30\,v_{\text{novelty}} + 0.20\,|v_{\text{emotional}}| + 0.35\,v_{\text{task}} + 0.15\,v_{\text{repetition}}$$

> Task relevance weighted highest (0.35) because it most strongly correlates with recall accuracy.

### WorkingMemory (Hippocampal Analog)

- **Capacity: 7 items** (Miller's Law)
- Stores Episode objects: timestamp, concept IDs, raw text, composite value vector
- FIFO displacement when full; recency boosts importance
- Creates natural **memory pressure** forcing consolidation

### LongTermMemory (Cortical Analog)

- **NetworkX directed graph** with concepts as nodes, typed relations as edges
- Each node stores: embedding, value vector, timestamps, access count, connection strength
- Persistence via **SQLite** (optional PostgreSQL for production)
- **Retrieval combines three strategies:**
  1. Semantic search (cosine similarity)
  2. Graph traversal (relation edges)
  3. Importance ranking (composite value score)
  - Final result: ranked fusion of all three

### SleepCycle

**Trigger conditions** (any one suffices):
- Memory entropy > θ_e = 0.9
- Conflict density > θ_c = 0.3
- Elapsed time > τ = 1 hour
- Manual forcing

**NREM Consolidation** — Replays working memory episodes:
- **Hebbian strengthening:** Δs_ij = η · I(c_i) · I(c_j), where η = 0.1
- **Proportional synaptic downscaling:** s_ij ← α · s_ij, where α = 0.8 (20% reduction per cycle)
- Decay rate λ = 0.01 → concept accessed 1 hour ago retains ~96% recency score

**REM Dreaming** — Random walks on memory graph:
- Transition probability: P(c_i → c_j) = s_ij / Σ_k s_ik
- Walk length = 5; top-k seeds (k=3)
- Valid sequences (non-contradicting) integrate as new `related_to` edges
- Creates novel cross-concept associations not present in original input

**Intentional Forgetting** — Value-based pruning:
- Retention score: S(c) = 0.8 · I(c) + 0.2 · (1 − δ(c)) where δ(c) = exp(−λ·Δt), λ = 0.01
- Adaptive threshold: θ_f = μ_I − σ_I · (|G| / target_size)
- Concepts below threshold are pruned from the graph
- Target: maintain graph at manageable size while preserving important concepts

---

## Self-Model (Computational Introspection)

SCM maintains a **self-model** — a meta-representation of the agent's own memory state:

- Current working memory load (items / 7)
- Long-term memory graph statistics (node count, edge density, entropy)
- Sleep cycle history (last trigger, consolidation effectiveness)
- Retrieval confidence estimates

This enables the agent to reason about its own memory limitations and communicate uncertainty.

---

## Evaluation Results

### Memory Noise Reduction

| Scenario | Initial Concepts | After Forgetting | Noise Pruned | Noise Reduction |
|---|---|---|---|---|
| 10-turn conversation | 72 | 24 | 45/50 noise | **90.9%** |
| Graph size reduction | — | — | — | **3× smaller** |

### Recall Accuracy

- **22/22 facts** correctly recalled over 10-turn conversation
- All 8 benchmark tests: **perfect 1.00 score**
- Sub-millisecond search latency with 360 stored concepts

### vs. Existing Systems

- Outperforms raw context window (which loses mid-sequence info)
- Outperforms append-only RAG (which accumulates noise)
- Adds biological mechanisms missing from MemGPT and Mem0

---

## Technical Stack

- **LLM:** Llama 3.2 (2B, Q4_K_M quantized via Ollama) — all local inference
- **Embeddings:** all-MiniLM-L6-v2 (384-dim)
- **Graph:** NetworkX directed graph
- **Persistence:** SQLite (default) / PostgreSQL (optional)
- **Language:** Python
- **Privacy:** No user data leaves the machine

---

## Limitations & Future Work

- Evaluated on synthetic benchmarks, not real-world deployment
- Single-agent evaluation (multi-agent sync described but not benchmarked)
- Code not yet publicly released (planned after peer review)
- Forgetting thresholds are manually tuned, not learned
- REM dream quality depends on graph connectivity

---

## Key Neuroscience Analogies

| Brain Structure | SCM Component | Function |
|---|---|---|
| Hippocampus | WorkingMemory | Fast, limited-capacity encoding |
| Neocortex | LongTermMemory | Slow, high-capacity storage |
| NREM Sleep | SleepCycle.consolidate() | Replay + strengthen + downscale |
| REM Sleep | SleepCycle.dream() | Random walk associations |
| Synaptic Pruning | SleepCycle.forget() | Value-based concept removal |
| Prefrontal Cortex | Self-Model | Metacognition + introspection |
