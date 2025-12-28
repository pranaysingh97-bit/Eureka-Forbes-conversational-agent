
* **Semantic Chunking:** I split the raw corpus into Q&A pairs. **Why?** To ensure retrieved context is focused and fits perfectly within the LLM’s context window without losing relevant detail.
* **Vector Embeddings:** Used Google’s `text-embedding-004` to project text into a 768-dimensional space. **Why?** To capture the mathematical "meaning" of the text, allowing for semantic search rather than brittle keyword matching.
* **FAISS Indexing:** Leveraged **FAISS (Facebook AI Similarity Search)** to store vectors and perform L2 distance calculations. **Why?** To enable millisecond-latency retrieval across high-dimensional data.
* **Retrieval-Augmented Prompting:** The user query is embedded in real-time to pull the top *k* most relevant chunks, which are then injected into a "Query-First" system prompt.
* **Gemini 1.5 Flash Generation:** Used the Flash model for the final synthesis. **Why?** It provides the perfect balance of low latency and high reasoning capability to generate professional, context-grounded answers.
* **Conversational Memory:** Implemented stateful chat sessions. **Why?** So the bot understands follow-up questions like "Does it cover filters?" by maintaining the history of the "it" (the purifier).
actual output!
* **Tag the Tech:** You might want to tag **Google Cloud** or **Google AI** since you used the Gemini API.

Summary: How Gemini is used twice

Think of it like a library:

The Embedding AI: Is the expert librarian who has read every book and knows exactly where every idea is located, even if the titles are different.

FAISS: Is the physical shelf where the librarian stores the books. (This is math, not AI).

The LLM AI: Is the research assistant who takes the books the librarian found, reads the relevant pages, and writes a summary report for you.

So, while FAISS is just a fast filing cabinet, the process of turning text into locations and turning data into answers both require high-level AI!
