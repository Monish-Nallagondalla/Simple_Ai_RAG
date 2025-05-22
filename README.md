# Simple AI RAG Document Q&A

This repository contains a Retrieval-Augmented Generation (RAG) document Q&A system built with Streamlit, leveraging LangChain, Groq, and Llama3 for question answering. The system processes PDF research papers stored in a `research_papers` directory, creates a vector database using FAISS, and allows users to query the content. Two implementations are provided: one using HuggingFace embeddings (`app_huggingfaceembedding.py`) and another using OpenAI embeddings (`main.py`).

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [File Structure](#file-structure)
- [Setup Instructions](#setup-instructions)
- [Requirements](#requirements)
- [Usage](#usage)
- [License](#license)

## Overview
The project implements a RAG-based Q&A system that processes PDF documents and answers user queries based on their content. It uses Streamlit for the web interface, LangChain for document processing and retrieval, Groq's Llama3 model for generating answers, and FAISS for vector storage. The two versions differ in their embedding models:
- `app_huggingfaceembedding.py`: Uses HuggingFace's `all-MiniLM-L6-v2` for embeddings.
- `main.py`: Uses OpenAI embeddings.

## Features
- Web-based interface built with Streamlit for user interaction.
- Processes PDF documents from a specified directory (`research_papers`).
- Supports two embedding models:
  - HuggingFace (`all-MiniLM-L6-v2`) for open-source embeddings.
  - OpenAI embeddings for cloud-based embeddings.
- Uses Groq's Llama3-8b-8192 model for generating accurate responses.
- FAISS vector store for efficient document retrieval.
- Expandable section to view similar document chunks for each query.
- Measures and logs response time for queries.

## File Structure
```
├── .gitignore              # Git ignore file for excluding unnecessary files
├── LICENSE                 # License file (MIT)
├── README.md               # Project documentation
├── app_huggingfaceembedding.py  # RAG Q&A implementation using HuggingFace embeddings
├── main.py                 # RAG Q&A implementation using OpenAI embeddings
└── research_papers/        # Directory for storing PDF research papers (not included)
```

## Setup Instructions
1. **Clone the Repository**
   ```bash
   git clone https://github.com/Monish-Nallagondalla/Simple_Ai_RAG.git
   cd Simple_Ai_RAG
   ```

2. **Install Dependencies**
   Ensure you have Python 3.8+ installed. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

3. **Set Up Environment Variables**
   - Create a `.env` file in the project root:
     ```bash
     touch .env
     ```
   - Add the necessary API keys:
     ```plaintext
     GROQ_API_KEY=your_groq_api_key
     OPENAI_API_KEY=your_openai_api_key  # Required for main.py
     HF_TOKEN=your_huggingface_token      # Required for app_huggingfaceembedding.py
     ```
   - Obtain API keys:
     - Groq API: Sign up at [console.groq.com](https://console.groq.com).
     - OpenAI API: Sign up at [platform.openai.com](https://platform.openai.com).
     - HuggingFace Token: Generate at [huggingface.co/settings/tokens](https://huggingface.co/settings/tokens).

4. **Prepare PDF Documents**
   - Create a `research_papers` directory in the project root.
   - Place PDF research papers in this directory for processing.

5. **Run the Application**
   - For HuggingFace embeddings:
     ```bash
     streamlit run app_huggingfaceembedding.py
     ```
   - For OpenAI embeddings:
     ```bash
     streamlit run main.py
     ```

## Requirements
The dependencies are listed in `requirements.txt`. Key packages include:
```
streamlit
langchain
langchain-groq
langchain-openai
langchain-community
langchain-huggingface
faiss-cpu
pypdf
python-dotenv
```

## Usage
1. Launch the Streamlit app using the instructions above.
2. Click the "Document Embedding" button to process PDFs and create the FAISS vector database.
3. Enter a query related to the research papers in the text input field.
4. View the generated answer and response time.
5. Expand the "Document Similarity Search" section to see relevant document chunks.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
```
