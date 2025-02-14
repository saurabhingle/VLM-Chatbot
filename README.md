# VLM Chat Bot

## Overview
VLM Chat Bot is an AI-powered chatbot application built with Streamlit that allows users to interact with various types of media, including PDFs, text-based questions, and images. The chatbot leverages Large Language Models (LLMs) to provide intelligent responses based on the given inputs.

## Features
- **Chat with PDF**: Upload a PDF and ask questions related to its content.
- **Text Question Answering**: Directly input a text-based query and receive responses from the model.
- **Image Questioning**: Upload an image and ask questions related to objects, context, and background.

## Installation
### Prerequisites
Ensure you have the following installed:
- Python 3.8+
- pip

### Install Dependencies
Run the following command to install the required dependencies:
```bash
pip install -r requirements.txt
```

## Configuration
Modify `config.yaml` to update model and embedding configurations:
```yaml
llm:
  model_name: "mistral"
  embedding_model: "sentence-transformers/all-MiniLM-L6-v2"
  image_model: "llava"

paths:
  embeddings_dir: "vectorstore"
```

## Usage
Run the application using the command:
```bash
streamlit run main.py
```

### Functionality
1. **Chat with PDF**:
   - Upload a PDF file.
   - Ask questions related to the document content.
   - The chatbot retrieves relevant information from the PDF using vector embeddings and FAISS.

2. **Text Question Answering**:
   - Enter a question in the text input field.
   - The chatbot processes the query using LangChain and provides an answer.

3. **Image Questioning**:
   - Upload an image in PNG, JPG, or JPEG format.
   - Ask questions about objects, background, and context.
   - The chatbot processes the image using Ollama and provides insights.

## File Structure
```
VLM-Chat-Bot/
│── main.py                 # Main application script
│── config.yaml             # Configuration file for models
│── requirements.txt        # List of dependencies
│── modules/
│   ├── pdf_QnA.py          # PDF processing module
│   ├── text_qna.py         # Text-based QnA module
│   ├── image.py            # Image processing module
│   ├── prompt.py           # Prompt handling for LLM
│── utils/
│   ├── model_loader.py     # LLM and embedding model loader
│   ├── config_loader.py    # YAML config loader
```

## Dependencies
The project uses the following libraries:
- `streamlit` - For web-based UI
- `langchain` - For natural language processing and embeddings
- `sentence-transformers` - For text embeddings
- `openai` - LLM API integration
- `ollama` - Image processing model
- `FAISS` - Vector database for document embeddings

## Future Improvements
- Integrate more advanced LLM models for better responses.
- Improve UI/UX for better user experience.
- Optimize performance for large PDF processing.
