# RAG-Driven Generative AI with Wikipedia and LlamaIndex

## Summary

This project demonstrates the creation of a scalable knowledge-graph-based RAG (Retrieval Augmented Generation) system using the Wikipedia API and LlamaIndex.  This system is applicable to various domains, including data management, marketing, and any field requiring organized and accessible data retrieval.

## Pipelines

The system is built using three main pipelines:

**Pipeline 1: Data Collection**

- Automates retrieval of Wikipedia content using the Wikipedia API.
- Collects metadata and URLs from Wikipedia pages based on a chosen topic.

**Pipeline 2: Deep Lake Vector Store**

- Embeds and upserts retrieved data into a Deep Lake vector store.
- Enables efficient storage and retrieval of large datasets.

**Pipeline 3: Knowledge Graph Index-based RAG**

- Automatically builds a knowledge graph index from the embedded data using LlamaIndex.
- Visually maps relationships between information, providing a semantic overview.
- Queries the knowledge graph using LlamaIndex's built-in language model for optimal responses.
- Implements metrics for evaluating system performance and ensuring accurate data retrieval.


## Implementation Details

1. **Data Collection:** The code retrieves URLs from a text file (`Marketing_urls.txt`) which contains the list of wikipedia links to be used in our RAG system. It then fetches content from these URLs and saves them as text files in the `./data/` directory.
2. **Vector Store Creation:** Utilizes Deep Lake as the vector store, embedding and storing the collected data.
3. **Knowledge Graph Index:**  LlamaIndex is used to build a knowledge graph index from the embedded data in Deep Lake. This index maps relationships between different pieces of information.
4. **Query Engine:** A query engine is created from the knowledge graph index, enabling users to retrieve relevant information through natural language queries.
5. **Re-ranking:** The system re-ranks the query results based on cosine similarity with the original user query to ensure optimal response selection.
6. **Metrics:** The system includes metrics for evaluating its performance, such as measuring query execution time and using cosine similarity with sentence transformers to evaluate the quality of the response.
