# Multimodal RAG Chatbot for Cloud native software

## Overview

Using Streamlit application and NVIDIA 's framework this chatbot implements a Multimodal Retrieval-Augmented Generation (RAG) system. It processes different types of documents like   PDFs, PowerPoint presentations, and images. The app leverages Large Language Models and Vision Language adaptersto extract and index information from these documents, allowing users to query the processed data through an interactive chat interface.

The system utilizes LlamaIndex for efficient indexing and retrieval of information, NIM microservices for high-performance inference capabilities, and Milvus as a vector database for efficient storage and retrieval of embedding vectors. This combination of technologies enables the application to handle complex multimodal data, perform advanced queries, and deliver rapid, context-aware responses to user inquiries.

## Features

- **Multi-format Document Processing**: Handles text files, PDFs, PowerPoint presentations, and images.
- **Advanced Text Extraction**: Extracts text from PDFs and PowerPoint slides, including tables and embedded images.
- **Image Analysis**: Uses a VLM (NeVA) to describe images and Google's DePlot for processing graphs/charts on NIM microservices.
- **Vector Store Indexing**: Creates a searchable index of processed documents using Milvus vector store. This folder is auto generated on execution.
- **Interactive Chat Interface**: Allows users to query the processed information through a chat-like interface.

## Setup

Leveraged NVIDIA's multimodal RAG framework and NIM framework to build a chatbot

1. Clone the repository:
```
git clone https://github.com/Anish-100/rbfsnvidiarag

```

2. (Optional) Create a conda environment or a virtual environment:

   - Using conda:
     ```
     conda create --name multimodal-rag python=3.10
     conda activate multimodal-rag
     ```

   - Using venv:
     ```
     python -m venv venv
     source venv/bin/activate

3. Install the required packages:
```
pip install -r requirements.txt
```

4. Set up your NVIDIA API key as an environment variable:
```
export NVIDIA_API_KEY="your-api-key-here"
```

5. Refer this [tutorial](https://milvus.io/docs/install_standalone-docker-compose-gpu.md) to install and start the GPU-accelerated Milvus container:

```
sudo docker compose up -d
```


## Usage

1. Ensure the Milvus container is running:

```bash
docker ps
```

2. Run the Streamlit app:
```
streamlit run app.py
```

3. Open the provided URL in your web browser.

4. Choose between uploading files or specifying a directory path containing your documents.

5. Process the files by clicking the "Process Files" or "Process Directory" button.

6. Once processing is complete, use the chat interface to query your documents.

## File Structure

- `app.py`: Main Streamlit application
- `utils.py`: Utility functions for image processing and API interactions
- `document_processors.py`: Functions for processing various document types
- `requirements.txt`: List of Python dependencies
- `vectorstore/` : Repository to store information from pdfs and ppt


## Acknowledgements
NVIDIA's Open Source multimodal RAG development framework used as the base application

