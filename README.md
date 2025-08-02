# simple_rag

Simple RAG (Retrieval-Augmented Generation) System
Overview
This code implements a basic Retrieval-Augmented Generation (RAG) system for processing and querying PDF documents. The system encodes the document content into a vector store, which can then be queried to retrieve relevant information.

Key Components

1. PDF processing and text extraction

2. Text chunking for manageable processing

3. Vector store creation using FAISS and HuggingFace embeddings

4. Retriever setup for querying the processed documents



Method Details

Document Preprocessing

1. The PDF is loaded using PyPDFLoader.

2. The text is split into chunks using RecursiveCharacterTextSplitter with specified chunk size and overlap.

Text Cleaning

A custom function replace_t_with_space is applied to clean the text chunks. This likely addresses specific formatting issues in the PDF.

Vector Store Creation

1. HuggingFace embeddings are used to create vector representations of the text chunks.

2. A FAISS vector store is created from these embeddings for efficient similarity search.

Retriever Setup

1. A retriever is configured to fetch the top 2 most relevant chunks for a given query.

Encoding Function
The encode_pdf function encapsulates the entire process of loading, chunking, cleaning, and encoding the PDF into a vector store.

Key Features

1. Modular Design: The encoding process is encapsulated in a single function for easy reuse.

2. Configurable Chunking: Allows adjustment of chunk size and overlap.

3. Efficient Retrieval: Uses FAISS for fast similarity search.


Usage Example
The code includes a test query: "What is the main cause of climate change?". This demonstrates how to use the retriever to fetch relevant context from the processed document.


Conclusion
This simple RAG system provides a solid foundation for building more complex information retrieval and question-answering systems. By encoding document content into a searchable vector store, it enables efficient retrieval of relevant information in response to queries. This approach is particularly useful for applications requiring quick access to specific information within large documents or document collections.
