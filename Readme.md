# LearnMate - AI-powered Learning Assistant

**LearnMate** is a full-stack AI-powered learning assistant for students, designed to help them interact with their course materials effectively. With **LearnMate**, students can upload course documents (PDF, PPT, Word, Excel), receive instant document summaries, interact with an intelligent chatbot, and even generate quizzes based on the uploaded content.

This project uses **FastAPI** for the backend, **Pinecone** as the vector database, and **Langchain** for interacting with language models (LLMs) like GPT-4.

---

## Features

- **Document Summarization**: Upload documents and get instant summaries to understand key points quickly.
- **Quiz Generation**: Based on the content of the document, automatically generate a list of important questions for studying.
- **Chatbot Assistance**: Ask questions about your documents and receive real-time answers, with context retained across multiple interactions.
- **Vector-Based Search**: Use Pinecone for efficient similarity search and retrieval of document-related information.
- **History Tracking**: The chatbot retains conversation history, providing continuous context for ongoing interactions.

---

## Technologies Used

- **FastAPI**: Fast and asynchronous web framework for building APIs.
- **Pinecone**: Managed vector database for efficient similarity search and storing document embeddings.
- **Langchain**: Framework for working with language models like GPT-4 for text summarization and chat interactions.
- **OpenAI**: Used to interact with GPT-4 for natural language understanding and responses.
- **Faiss**: Optional integration for local vector search (can be used with Pinecone if needed).

---

## Project Structure

LearnMate/ │ ├── app/ │ ├── init.py │ ├── main.py # FastAPI entry point │ ├── models/ │ │ ├── document.py # Document model (for metadata) │ │ ├── quiz.py # Quiz model │ ├── services/ │ │ ├── vector_store.py # Pinecone integration for vector DB │ │ ├── summarizer.py # Document summarization logic │ │ ├── quiz_generator.py # Logic for generating quizzes │ │ ├── chatbot.py # Chatbot integration using Langchain │ ├── api/ │ │ ├── document.py # API endpoints for document handling │ │ ├── chatbot.py # API endpoints for chatbot interactions │ │ ├── quiz.py # API endpoints for quiz handling │ ├── utils/ │ │ ├── helpers.py # Utility functions (e.g., file handling, validation) │ ├── config.py # Configuration file (e.g., Pinecone API key) │ ├── tests/ │ │ ├── test_api.py # API tests (Postman-compatible) │ │ ├── test_services.py # Service logic tests (for summarizer, quiz generator) │ ├── .env # Environment variables (Pinecone API keys, etc.) ├── requirements.txt # Dependencies ├── README.md # Project description and instructions

---

## Installation & Setup

### Prerequisites

- Python 3.8+
- An active **Pinecone** account (for vector database).
- An active **OpenAI API key** (for Langchain & GPT-4 integration).
- Install dependencies using `pip`.

### Steps to Run the Application

1. Clone this repository:

   ```bash
   git clone https://github.com/yourusername/learnmate.git
   cd learnmate
   ```

2. Set up a virtual environment and activate it:

   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. Install the required dependencies:

   ```bash
   pip install -r requirements.txt
   ```

4. Create a `.env` file to store sensitive information (e.g., Pinecone API Key, OpenAI API Key):

   ```dotenv
   PINECONE_API_KEY=your_pinecone_api_key
   PINECONE_ENV=us-west1-gcp  # Change based on your region
   OPENAI_API_KEY=your_openai_api_key
   ```

5. Run the FastAPI server:

   ```bash
   uvicorn app.main:app --reload
   ```

Now your backend will be running at `http://127.0.0.1:8000`.
