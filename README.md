# Project Name: AI based News Retriever

## Overview

This project is designed to fetch RSS feeds from various sources, extract the main content, summarize it using OpenAI's GPT models, and store the summarized content in a structured format. The system also includes a retrieval mechanism using FAISS, enabling users to search for specific information across the summarized content. Additionally, Jina AI is used for scraping content from specific sources, enhancing the overall efficiency and scalability of the system.

## Features

- **RSS Feed Fetching:** The system fetches RSS feeds from multiple sources, extracts relevant data, and stores it for further processing.
- **Content Summarization:** Uses OpenAI's GPT models to summarize the fetched articles, ensuring that only the core content is preserved.
- **Data Storage:** Summarized content is stored in a CSV file, making it easy to manage and update.
- **Vector Store with FAISS:** The summarized content is embedded and stored using FAISS, allowing for efficient similarity-based searches.
- **Custom Retrieval-Augmented Generation (RAG):** A custom RAG pipeline is implemented to answer user queries based on the stored summaries.
- **Jina AI Scraping:** Integrated Jina AI for scraping, providing an efficient and scalable method to retrieve content from specific sources.

## Techniques Used

1. **BeautifulSoup:** For parsing and extracting data from RSS feeds.
2. **Jina AI:** For scraping content from specific sources, improving scraping efficiency and handling large-scale data.
3. **OpenAI GPT Models:** For text summarization and question-answering tasks.
4. **FAISS (Facebook AI Similarity Search):** For creating a vector store that enables fast and accurate retrieval of relevant documents.
5. **Recursive Character TextSplitter:** For splitting long documents into smaller, manageable chunks.
6. **LangChain:** For building the RAG pipeline, allowing the integration of retrieval and generation processes.

## Setup and Installation

### Prerequisites

- Python 3.8 or higher
- Install required packages using `pip`:
  ```bash
  pip install requests beautifulsoup4 langchain pandas faiss-cpu jina

## API Keys

This project requires API key for OpenAI.

## Running the Project

### Fetch and Summarize RSS Feeds:

- The script fetches RSS feeds from various sources and stores them in a CSV file.
- Summarization is performed on the fetched articles, and the results are stored in `structured_documents.csv`.

### Scraping with Jina AI:

- Jina AI is used for scraping content from specific sources, ensuring efficient and scalable content retrieval.

### Search and Retrieval:

- After summarizing, the content is split and embedded using FAISS.
- You can then query the system to retrieve specific information.

## Example Queries

### Retrieve all transfer news on Liverpool FC:

```python
answer = rag_chain.invoke("Provide me all of the transfer news on Liverpool FC in bullets")
print(answer)
```

# Retrieve the Latest News in Pakistan

```python
# Example Python code using a custom RAG pipeline to retrieve the latest news
answer = rag_chain.invoke("latest pakistani news, in bullets")
print(answer)
```

## Summary of the Process

- **RSS Feed Fetching**: The system iterates through a list of RSS feed URLs, extracting titles, links, publication dates, and categories.

- **Content Summarization**: Each article's content is fetched and summarized using OpenAI's GPT model.

- **Scraping with Jina AI**: Jina AI is utilized for efficiently scraping content from specific sources.

- **Storage and Retrieval**: The summarized content is stored in a CSV file, embedded using FAISS, and made available for similarity-based retrieval.

- **RAG Pipeline**: The custom RAG pipeline processes user queries, retrieves relevant documents, and generates concise answers.

## Contributing

Feel free to open issues or submit pull requests if you have suggestions or improvements.

## License

This project is licensed under the MIT License - see the LICENSE file for details.



