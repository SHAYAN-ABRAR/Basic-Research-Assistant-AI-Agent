# Research Assistant AI Agent

## Overview
This project implements a **Research Assistant AI Agent** that processes PDF documents, answers user queries, and leverages both short-term and long-term memory. Built with **LangGraph**, **ChromaDB**, and **Grok (llama-3.3-70b)**, this agent extracts text from PDFs, stores insights, and provides intelligent responses.

## Features
- **PDF Processing**: Extracts and chunks PDF content using **PyPDF2** and **RecursiveCharacterTextSplitter**.
- **Short-term Memory**: Uses **LangGraph's MemorySaver** to retain conversation state during a session.
- **Long-term Memory**: **ChromaDB** stores conversation messages, PDF chunks, and summaries for retrieval across sessions.
- **Summarization**: Automatically generates concise PDF summaries for long-term memory storage.
- **Query Handling**: The agent answers queries and integrates PDF content, providing context from both short-term and long-term memory.

## Architecture
- **LLM**: Grok (llama-3.3-70b-versatile) from xAI for intelligent querying and summarization.
- **PDF Processing**: Text extraction with **PyPDF2** and chunking with **RecursiveCharacterTextSplitter**.
- **Memory**:
  - **Short-term**: MemorySaver stores session states.
  - **Long-term**: ChromaDB stores conversation messages and PDF chunks.
- **Graph**: A single node (`query_handling_llm`) processes queries, integrates PDF content, and retrieves context from ChromaDB.
