# Medical Chatbot

An AI-powered medical assistant built with Retrieval-Augmented Generation (RAG) architecture. The chatbot answers medical questions by retrieving relevant information from medical textbooks and using GPT-4o to generate accurate responses.

## Features

- RAG-based architecture for accurate medical Q&A
- Processes medical PDF textbooks (USMLE guides, medical diagnosis references)
- Semantic search using Pinecone vector database
- Real-time chat interface
- Context-aware responses based on retrieved medical literature

## Tech Stack

**Backend:**
- Python
- Flask
- LangChain
- OpenAI GPT-4o
- Pinecone (vector database)
- HuggingFace Transformers

**Data Processing:**
- PyPDF
- Sentence Transformers
- Recursive Character Text Splitter

**Frontend:**
- HTML5
- CSS3
- JavaScript
- Bootstrap 4

## Setup

1. Clone the repository:
```bash
git clone https://github.com/frostedonut2812/medical-chatbot.git
cd medical-chatbot
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Set up environment variables:
Create a `.env` file with:
```
PINECONE_API_KEY=your_pinecone_api_key
OPENAI_API_KEY=your_openai_api_key
```

4. Populate the vector database:
```bash
python store_index.py
```
Note: Place your medical PDF files in the `Data/` directory before running this script.

5. Run the application:
```bash
python app.py
```

6. Open your browser and navigate to `http://localhost:8080`

## Project Structure

```
medical-chatbot/
├── Data/              # Medical PDF textbooks
├── src/               # Source code
│   ├── helper.py      # PDF processing and embeddings
│   └── prompt.py      # System prompts
├── static/            # CSS files
├── templates/         # HTML templates
├── app.py             # Flask application
├── store_index.py     # Vector database setup
└── requirements.txt   # Python dependencies
```

## How It Works

1. **Data Processing**: Medical PDFs are loaded and split into text chunks
2. **Embedding Generation**: Text chunks are converted to vector embeddings using HuggingFace models
3. **Vector Storage**: Embeddings are stored in Pinecone for fast similarity search
4. **Query Processing**: User queries are embedded and matched against the vector database
5. **Response Generation**: Retrieved context is passed to GPT-4o to generate accurate medical responses

## License

This project is for educational purposes.
