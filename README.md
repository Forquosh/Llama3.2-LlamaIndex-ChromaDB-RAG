# RAG with LLaMA 3.2 1B and LlamaIndex + ChromaDB

This repository provides a Jupyter Notebook that uses the LLaMA 3.2 1B model along with LlamaIndex and ChromaDB for Retrieval-Augmented Generation (RAG). The bot is designed to answer questions based on information extracted from PDF documents. The notebook demonstrates an open-source, GPU-compatible approach for conversational AI on specific data.

## Features
- *Q&A on Data*: Query information directly from the contents of PDF files using a custom dataset and get contextually relevant answers generated by an LLM. For this example I used my results report on the Understand Myself personality test.
- *Document Processing*: Load and split PDF files stored in the `docs` directory, then create embeddings for document sections to enable targeted retrieval.
- *Conversational Retrieval*: Utilizes RAG to dynamically combine LLaMA’s responses with relevant content from your PDF data.
- *ChromaDB for Vector Storage*: Efficient document retrieval is achieved using ChromaDB for storing and indexing vector embeddings.

## Requirements
- Python 3.8 or higher
- Install the dependencies: `pip install -r requirements.txt`
- **Hardware**: 8GB VRAM, 16GB RAM

## How to Use

### 1. Setup PDF Data
Add your PDF files to a directory named `docs`. The notebook loads and processes these PDFs, creating embeddings to enable contextually accurate retrieval. In the example, it processes reports or documents for personalized insights.

### 2. Run the Notebook
Load the notebook and run each code cell in sequence. This will load the LLaMA 3.2 1B model, initialize embeddings, and set up the RAG system using ChromaDB.

### 3. Ask Questions
In the designated cells, input questions about the contents of your PDF files. The bot will reference the document embeddings stored in ChromaDB to find relevant information and generate informed answers.

## Code Overview
- *Model Loading*: The notebook loads the LLaMA 3.2 1B model as the primary language model for response generation.
- *Document Loading*: PDF files are processed using `SimpleDirectoryLoader` from LlamaIndex.
- *Vector Store Creation*: The processed text chunks are converted to embeddings and stored in ChromaDB for efficient document retrieval.
- *Question Answering*: Answers your questions based on the retrieved context (the data from the documents).
  
## Known Limitations
- **Some Unpredictable Results**: While my testing has been mostly successful, there is some margin of error that I was not yet able to eliminate.
- **System Requirements**: Running the LLaMA 3.2 1B model may require significant memory resources; ensure adequate RAM or perform a quantization.

## Future Improvements
- **Enhanced Performance**: The next step is removing any misinformed answers or incorrect retrievals.
- **Advanced Document Processing**: Refining the chunking and embedding techniques could improve retrieval accuracy, especially for larger documents.
