# Legal Document RAG Chatbot 🏛️⚖️

A sophisticated AI-powered legal document chatbot using RAG (Retrieval Augmented Generation) with Google Gemini API. This project features both Python/Streamlit and React/TypeScript interfaces for querying legal documents intelligently.

## 🌟 Features

- **RAG Technology**: Uses Retrieval Augmented Generation for accurate, context-aware responses
- **Google Gemini Integration**: Powered by Google's latest AI models
- **Dual Interface**: 
  - Python/Streamlit web interface
  - Modern React/TypeScript frontend
- **Vector Search**: FAISS-based document similarity search
- **Chat History**: Persistent conversation memory
- **Document Upload**: Support for PDF document processing
- **Real-time Responses**: Fast, streaming responses
- **User-friendly UI**: Clean, professional interface with avatars

## 🚀 Quick Start

### Prerequisites

- Python 3.8+
- Node.js 16+ (for React frontend)
- Google Gemini API key ([Get one here](https://makersuite.google.com/app/apikey))

### 1. Clone the Repository

```bash
git clone https://github.com/vigneshworkspace/legal-document-rag-chatbot.git
cd legal-document-rag-chatbot
```

### 2. Set up Python Backend

```bash
# Navigate to chatbot directory
cd chatbot

# Install dependencies
pip install -r requirements.txt

# Copy environment file and add your API key
cp .env.example .env
# Edit .env and add your GOOGLE_API_KEY
```

### 3. Process Your Legal Document

```bash
# Place your PDF in the chatbot directory and update PDF_PATH in .env
python pdf_to_rag.py
```

### 4. Start the Backend Server

```bash
# Option 1: FastAPI server (recommended)
python main.py

# Option 2: Streamlit interface
streamlit run server.py
```

### 5. Start the React Frontend (Optional)

```bash
# Navigate to React app
cd ../ragbot/legal-chatbot

# Install dependencies
npm install

# Start development server
npm run dev
```

## 📁 Project Structure

```
legal-document-rag-chatbot/
├── chatbot/                 # Python backend
│   ├── main.py             # FastAPI server
│   ├── server.py           # Streamlit interface
│   ├── rag_chatbot.py      # Core RAG implementation
│   ├── pdf_to_rag.py       # Document processing
│   ├── requirements.txt    # Python dependencies
│   ├── .env.example       # Environment variables template
│   └── vector_store/      # Generated vector database
├── ragbot/legal-chatbot/   # React frontend
│   ├── src/               # Source code
│   ├── components/        # React components
│   ├── services/         # API services
│   ├── package.json      # Node dependencies
│   └── public/           # Static assets
└── README.md             # This file
```

## ⚙️ Configuration

### Environment Variables (.env)

```env
# Google Gemini API Key
GOOGLE_API_KEY=your_api_key_here

# PDF File Path
PDF_PATH=path/to/your/document.pdf

# Vector Store Configuration
VECTOR_STORE_PATH=./vector_store
CHUNK_SIZE=1000
CHUNK_OVERLAP=200
SIMILARITY_SEARCH_K=4

# LLM Configuration
MODEL_NAME=gemini-2.0-flash-exp
TEMPERATURE=0.3
MAX_TOKENS=1000
```

## 🛠️ Usage

### Python/Streamlit Interface

1. Start the Streamlit server: `streamlit run server.py`
2. Open your browser to `http://localhost:8501`
3. Configure your API key in the sidebar
4. Initialize the chatbot
5. Start asking questions about your legal document

### React/TypeScript Interface

1. Start the FastAPI backend: `python main.py`
2. Start the React frontend: `npm run dev`
3. Open your browser to `http://localhost:5173`
4. Interact with the modern chat interface

### API Endpoints

- `GET /health` - Health check
- `POST /chat` - Send a message to the chatbot
- `GET /history` - Get chat history
- `DELETE /history` - Clear chat history

## 🔧 Features in Detail

### RAG Implementation
- **Document Chunking**: Intelligent text splitting for optimal retrieval
- **Vector Embeddings**: Google's embedding models for semantic search
- **Context Retrieval**: Relevant document sections for each query
- **Response Generation**: Context-aware answers using Gemini

### User Interface
- **Clean Design**: Professional, legal-themed interface
- **User Avatars**: Custom user profile images
- **Message History**: Persistent conversation tracking
- **Source Citations**: View source documents for each response
- **Copy Functionality**: Easy copying of responses

### Performance Optimization
- **Efficient Caching**: Reduced API calls through smart caching
- **Rate Limiting**: Built-in protection against quota limits
- **Error Handling**: Graceful handling of API errors

## 🚨 Troubleshooting

### Common Issues

1. **Quota Exceeded Error**
   - Wait for quota reset (daily/per minute limits)
   - Upgrade your Google AI Studio plan
   - Reduce `SIMILARITY_SEARCH_K` value

2. **Vector Store Not Found**
   - Run `python pdf_to_rag.py` first
   - Check PDF_PATH in .env file

3. **API Key Issues**
   - Verify API key is correctly set in .env
   - Restart the application after changing the key

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📞 Support

If you encounter any issues or have questions:

- Open an issue on [GitHub Issues](https://github.com/vigneshworkspace/legal-document-rag-chatbot/issues)
- Check the troubleshooting section above
- Review the [Google Gemini API documentation](https://ai.google.dev/docs)

## 🙏 Acknowledgments

- Google Gemini AI for powerful language models
- LangChain for RAG implementation framework
- Streamlit and React for user interfaces
- FAISS for efficient vector search

---

**Made with ❤️ for the legal tech community**