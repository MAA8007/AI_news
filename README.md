# Feed Summarization and RAG Pipeline

This repository contains a Jupyter Notebook designed for retrieving, summarizing, and querying news articles from various RSS feeds. The pipeline leverages several state-of-the-art NLP models and libraries to perform these tasks efficiently. The focus is on creating structured documents from RSS feeds, summarizing their content using transformer models, and providing an interactive querying mechanism using a retrieval-based system.

## Table of Contents
1. [Installation](#installation)
2. [Usage](#usage)
3. [Pipeline Overview](#pipeline-overview)
4. [Models and Libraries](#models-and-libraries)
5. [Customization](#customization)
6. [Contributing](#contributing)
7. [License](#license)

## Installation

To set up the environment and install the necessary dependencies, execute the following commands in your terminal or directly in the notebook:

```python
!pip install accelerate transformers tokenizers
!pip install bitsandbytes einops
!pip install xformers
!pip install langchain
!pip install faiss-gpu
!pip install sentence_transformers
!pip install --upgrade torch
!pip install langchain-community langchain-core
```

## Usage

- **Loading Models and Tokenizers**: The notebook loads a pre-trained transformer model (`Nexusflow/Starling-LM-7B-beta`) for text generation and a tokenizer associated with it.

- **Setting Up RSS Feeds**: Various RSS feeds are defined and configured to fetch news articles related to sports, technology, and more.

- **Fetching and Summarizing Articles**: The pipeline fetches articles from the RSS feeds, processes the content using BeautifulSoup, and summarizes the articles using transformer models.

- **Saving Summaries**: Summarized content is saved into a CSV file to maintain a record of processed articles.

- **Querying and Retrieval**: The notebook uses LangChain to allow users to query the summarized content. A vector store (using FAISS) is created for efficient retrieval of relevant articles based on user queries.

- **Interactive Querying**: The Conversational Retrieval Chain is set up to allow for interactive querying, providing users with the latest news based on their queries.

## Pipeline Overview

1. **Loading Models and Libraries**  
   The notebook begins by loading necessary models and libraries, including `transformers`, `torch`, and `langchain`.

2. **Fetching RSS Feeds**  
   A list of RSS feeds is defined, and the `fetch_feed()` function is used to retrieve articles from these feeds. The content is then structured and prepared for summarization.

3. **Summarization**  
   Articles fetched from the RSS feeds are summarized using the BART model. The `summarize_text()` function handles the summarization process, providing concise summaries of the articles.

4. **Storing Summaries**  
   Summarized content is saved into a CSV file using the `save_to_csv()` function. This allows for the reuse and querying of summarized content later.

5. **Querying the Data**  
   The `ConversationalRetrievalChain` from LangChain is used to allow users to query the stored summaries. The pipeline uses FAISS for vector-based retrieval, making the querying process efficient and effective.

## Models and Libraries

- **Transformers**: Used for text generation and summarization tasks.
- **LangChain**: Powers the conversational querying mechanism.
- **FAISS**: Used to create a vector store for efficient document retrieval.
- **BeautifulSoup**: Used for parsing HTML and XML content from the RSS feeds.

## Customization

You can customize the pipeline by:

1. **Adding or Removing RSS Feeds**: Modify the `rss_feeds` list and corresponding details in `rss_feed_details` to change the sources of the articles.
2. **Changing Summarization Models**: Replace the BART model with any other transformer-based summarization model by modifying the `summarize_text()` function.
3. **Altering Query Parameters**: Adjust the querying behavior by modifying parameters like `temperature`, `max_new_tokens`, and `repetition_penalty` in the text generation pipeline.

## Contributing

Contributions are welcome! Feel free to submit a pull request or open an issue for any improvements or suggestions.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

