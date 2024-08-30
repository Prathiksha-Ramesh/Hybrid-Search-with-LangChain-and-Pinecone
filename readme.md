# Hybrid Search with LangChain and Pinecone

This project demonstrates the integration of LangChain, Pinecone, and Hugging Face embeddings to create a hybrid search system. The system utilizes dense vector embeddings and sparse matrix representations (like BM25) to enable efficient and accurate retrieval of text data.

## Project Structure
project-directory/ 
│ ├── main.py 
├── bm25_values.json 
├── requirements.txt 
├── .env 
├── README.md 
├── LICENSE 
└── .gitignore


## Getting Started

### Prerequisites

Ensure you have the following installed:
- Python 3.8 or higher
- Pip (Python package installer)
- Pinecone account and API key

### Installation

1. Clone the repository:

```bash
git clone https://github.com/yourusername/hybrid-search-langchain-pinecone.git
cd hybrid-search-langchain-pinecone
```

2. Install the required Python packages:

```bash
pip install -r requirements.txt
```

3. Set up your environment variables in the `.env` file:
```bash
HF_TOKEN=your_huggingface_token
PINECONE_API_KEY=your_pinecone_api_key
```
Replace the placeholders with your actual Hugging Face and Pinecone API keys.

## Running the Application
1. Ensure your `.env` file is properly configured with your Hugging Face and Pinecone API keys.

2. Run the Python script to initialize the Pinecone index and add texts:

```bash
python main.py
```

- The script will initialize the Pinecone client, create an index if it doesn't already exist, generate vector embeddings using Hugging Face models, and encode sparse matrix representations using BM25.

- The script will also store the BM25 values to a JSON file and use them for retrieving texts based on the query.

## Example Usage
- The example sentences "In 2023, I visited Paris," "In 2022, I visited New York," and "In 2021, I visited New Orleans" are added to the Pinecone index.
- You can retrieve the most relevant text by querying the system with a question like "What city did I visit recent?"

## Integration Details

- `Pinecone`: Provides a scalable vector database service for storing and querying high-dimensional vectors.
- `LangChain`: Used to manage the retrieval process and integrate different NLP components.
- `Hugging Face Embeddings`: Generates dense vector embeddings using the all-MiniLM-L6-v2 model.
- `BM25`: A sparse matrix encoding technique used to calculate term frequency-inverse document frequency (TF-IDF) values, allowing for effective retrieval based on text relevance.

## Files

- `main.py`: The main Python script that handles the setup and interaction with Pinecone and Hugging Face models.
- `bm25_values.json`: A JSON file that stores the BM25-encoded values for the sample sentences.
- `requirements.txt`: Lists all the Python dependencies needed to run the application.
- `.env`: Contains the API keys for Hugging Face and Pinecone. This file should not be included in version control.
- `README.md`: This file, providing an overview of the project.
- `LICENSE`: The project's license, specifying how others may use the code.
- `.gitignore`: Specifies files and directories that should be ignored by Git, such as the .env file and any other sensitive information.

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## .gitignore
The following files are ignored in the version control:

```bash
.env
__pycache__/
*.pyc
*.pyo
*.pyd
bm25_values.json
```

## Contributing
Feel free to fork this repository and submit pull requests. For major changes, please open an issue first to discuss what you would like to change.

## Acknowledgments
- Thanks to Pinecone for providing a robust platform for vector database management.
- Thanks to Hugging Face for their powerful NLP models and embeddings.
- Thanks to the LangChain community for simplifying the integration of various NLP components.


