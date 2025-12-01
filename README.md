# RAG with BigQuery Vector Store

This project demonstrates a simple Retrieval-Augmented Generation (RAG) pipeline using Python. It retrieves information from a PDF document, embeds the text into vectors, stores them in a BigQuery Vector Store, and uses a Generative AI model to answer questions based on the document's content.

## Description

The script performs the following steps:
1.  Loads a PDF document from a URL.
2.  Splits the document's text into smaller chunks.
3.  Generates embeddings for each chunk using a Hugging Face sentence transformer model.
4.  Stores the text chunks and their corresponding embeddings in a BigQuery Vector Store.
5.  Takes a user query and retrieves the most relevant text chunks from BigQuery.
6.  Uses a Gemini Large Language Model (LLM) to generate a response to the user's query based on the retrieved context.

## Setup and Installation

1.  **Clone the repository:**
    ```bash
    git clone <repository-url>
    cd <repository-directory>
    ```

2.  **Create a virtual environment:**
    ```bash
    python3 -m venv .venv
    source .venv/bin/activate
    ```

3.  **Install the dependencies:**
    ```bash
    pip install -r req.txt
    ```

4.  **Set up your environment variables:**
    Create a `.env` file in the root directory of the project and add the following variables:

    ```
    GEMINI_API_KEYS="YOUR_GEMINI_API_KEY"
    PROJECT_ID="YOUR_GOOGLE_CLOUD_PROJECT_ID"
    DATASET="YOUR_BIGQUERY_DATASET_NAME"
    TABLE="YOUR_BIGQUERY_TABLE_NAME"
    REGION="YOUR_BIGQUERY_DATASET_REGION"
    ```

    Replace the placeholder values with your actual credentials and configuration.

## Usage

To run the script, execute the `main.py` file:

```bash
python main.py
```

The script will then:
1.  Fetch the PDF and process it.
2.  Store the data in BigQuery.
3.  Run a sample query: "What is the main topic of the document?".
4.  Print the generated answer to the console.
