# Document-Based Chatbot with FastAPI and DeepSeek-R1

This is a simple **document-based chatbot** built using **FastAPI**. It allows users to upload documents (PDF, DOCX, or TXT) and ask questions based on the document's content. The chatbot leverages the **DeepSeek-R1 (1.5B)** model via **Ollama** to generate responses.

## Features
- **Upload Documents**: Supports **PDF, DOCX, and TXT** file formats.
- **Extracts Text**: Automatically extracts text from uploaded documents.
- **Chat with Documents**: Users can ask questions, and the chatbot responds based on the uploaded document.
- **Interactive Web Interface**: A simple frontend built using HTML & JavaScript.
- **FastAPI Backend**: Lightweight and scalable API using FastAPI.
- **LLM Integration**: Calls DeepSeek-R1 (1.5B) via **Ollama API** for text generation.

## Installation
1. **Clone the Repository**
   ```sh
   git clone https://github.com/your-username/document-chatbot.git
   cd document-chatbot
   ```

2. **Install Dependencies**
   ```sh
   pip install fastapi uvicorn requests PyPDF2 python-docx
   ```

3. **Run Ollama (Ensure it's installed)**
   ```sh
   ollama serve
   ollama pull deepseek-r1:1.5b
   ```

4. **Start the FastAPI Server**
   ```sh
   uvicorn main:app --reload
   ```

5. **Access the Chatbot**
   - Open your browser and go to: `http://127.0.0.1:8000/`

## API Endpoints
- `POST /upload`: Uploads a document and extracts text.
- `POST /chat`: Accepts a user query and returns a response based on the document.
- `GET /`: Serves the chatbot UI.

## How It Works
1. **Upload a document** (`PDF, DOCX, TXT`).
2. The text is extracted and stored.
3. Ask questions related to the document.
4. The chatbot processes the query and responds using **DeepSeek-R1**.

## Example Usage
```python
import requests

url = "http://127.0.0.1:8000/chat"
data = {"message": "What is this document about?"}
response = requests.post(url, json=data)
print(response.json())  # {"response": "This document discusses..."}
```
