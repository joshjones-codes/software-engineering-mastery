# AI Systems

Applied AI engineering on top of everything above — agents and RAG are distributed systems with a model in the loop.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Embeddings & Vector Search](01-embeddings-and-vector-search.md) | 🔴 must | ~2 wknds | embedding models, similarity, pgvector before dedicated DBs, hybrid search |
| [RAG Systems](02-rag-systems.md) | 🔴 must | ~2 wknds | chunking, retrieval quality, reranking, citations, when RAG is the wrong tool |
| [Agents & Tool Use](03-agents-and-tool-use.md) | 🔴 must | ~2–3 wknds | agent loops, function calling, sandboxing, failure modes, human-in-the-loop |
| [MCP](04-mcp.md) | 🟡 should | ~1 wknd | build an MCP server over the lab product's data |
| [Evals](05-evals.md) | 🔴 must | ~2 wknds | golden sets, LLM-as-judge, regression testing prompts like code |
| [Context Engineering & Memory](06-context-engineering-and-memory.md) | 🟡 should | ~2 wknds | context budgets, summarization, memory architectures |
| [Prompting & Model Routing](07-prompt-engineering-and-model-routing.md) | 🟡 should | ~1 wknd | prompt caching, cost/latency tiers, structured output |
| [Inference & Serving](08-inference-and-serving.md) | ⚪ nice | ~2 wknds | tokens/sampling, batching, quantization intuition, latency budgets |
