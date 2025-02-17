# Expert Knowledge Worker - RAG-Based Chatbot

## Overview

This project implements a Retrieval-Augmented Generation (RAG) chatbot that serves as an expert knowledge worker. The chatbot is designed to be:

- Accurate: Uses a vector database for retrieving relevant information.

- Cost-effective: Utilizes a low-cost OpenAI model (GPT-4o-mini).

- Efficient: Built with LangChain, ChromaDB, and Gradio for seamless deployment.

## Features

- Document Ingestion: Loads markdown documents from a structured knowledge base.

- Text Chunking: Splits documents into smaller chunks to optimize retrieval.

- Vector Database: Stores document embeddings using ChromaDB.

- Conversational Memory: Remembers past interactions for a better user experience.

- Interactive UI: Integrated with Gradio for easy user interaction.

- Debugging Tools: Includes utilities for analyzing vector dimensions and retrieval performance.

## Installation

### Prerequisites

Ensure you have Python installed (>=3.8). You also need an OpenAI API key for embeddings and chat functionalities.

### Setup

- 1. Clone this repository:

git clone https://github.com/fretaabrish/LLM_RAG.git

- 2. Install dependencies:

pip install -r requirements.txt

- 3. Set up environment variables:

- Create a .env file in the root directory.

- Add the following line with your OpenAI API key:

      OPENAI_API_KEY=your-api-key

## Usage

### Running the Chatbot

To start the chatbot, run:

python main.py

This will launch the Gradio interface in your default web browser.

### Querying the Chatbot

- Ask questions related to the documents stored in the knowledge base.

- The chatbot will retrieve the most relevant context and generate an accurate response.

### Debugging Incorrect Responses

If the chatbot provides incorrect answers, consider:

- Adjusting chunk size and overlap.

- Increasing the number of retrieved contexts (k value).

- Reviewing document metadata and embeddings.

## Architecture

### 1. Document Processing

- Loads markdown files from the knowledge-base/ directory.

- Adds metadata (document type) for better categorization.

- Splits documents into manageable text chunks.

### 2. Vector Database

- Converts text chunks into embeddings using OpenAIEmbeddings (or HuggingFace if preferred).

- Stores embeddings in ChromaDB.

- Enables fast retrieval of relevant information during chat sessions.

### 3. Conversational Chain

- Uses GPT-4o-mini as the language model.

- Implements ConversationalRetrievalChain from LangChain.

- Maintains conversation memory using ConversationBufferMemory.

### 4. Deployment with Gradio

- Wraps the chatbot in a simple UI using Gradio's ChatInterface.

- Runs locally and can be easily deployed to cloud platforms.

## Future Improvements

- Support for Additional File Formats (PDF, CSV, JSON, etc.).

- Integration with FAISS for alternative vector database storage.

- Deployment as an API using FastAPI or Flask.
