# RAG Knowledge Assistant

Working local retrieval demo · LLM generation is a documented extension

Explore a transparent retrieval prototype that finds relevant passages and prepares a cited prompt for an LLM.

## Run
Serve this package directory with any static web server, then open projects/rag-knowledge-assistant.html. No install, API key, or backend is required.

## Architecture
Sample documents → Text chunks → Keyword ranking → Cited context → LLM prompt

## Implementation plan
1. Ingest documents and retain a stable document ID, source URL, access labels, and update timestamp.
2. Split documents into sections with overlap; retain parent document metadata on every chunk.
3. For production, replace this keyword baseline with embeddings, a vector index, and optional reranking.
4. Filter retrieved context by user permissions before assembling the prompt.
5. Call a server-side LLM endpoint and validate that output citations refer to retrieved evidence.

## Acceptance criteria
- Known question retrieves the correct source passage.
- Unrelated questions return no supporting evidence.
- Prompt includes source IDs and tells the model to abstain when evidence is insufficient.
- Production extension: measure retrieval recall, citation correctness, latency, and response faithfulness.

## Limitations
Synthetic data only. Browser prototype, not a production Foundry/AIP deployment. The retrieval demo uses keyword ranking, not embeddings or LLM generation. No real underwriting decision is made.

## Official documentation
- [Amazon Bedrock Knowledge Bases](https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base.html)