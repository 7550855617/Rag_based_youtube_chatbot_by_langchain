# 🎥 YouTube Chatbot using LangChain + RAG

This project builds an interactive **YouTube video chatbot** that allows users to ask questions about the content of a video. It uses **LangChain**, **Retrieval-Augmented Generation (RAG)**, and **OpenAI embeddings** (or HuggingFace alternatives) to enable natural language queries over YouTube transcripts.

---

## 🚀 Features

* 🔍 Extracts YouTube transcript automatically
* 🤖 Answers user questions based on video content
* 🧠 Uses vector search (FAISS) and LLMs via LangChain
* 📆 Lightweight and easy to run

---

## 🛠️ Installation

Make sure you're using a Python environment (e.g., conda or venv). Then install the required dependencies:

```bash
pip install -q youtube-transcript-api langchain-community langchain-openai \
             faiss-cpu tiktoken python-dotenv
```

---

## 🧰 Project Structure

```
youtube-chatbot/
│
├── .env                        # Store your OpenAI API key
├── main.py                     # Main script to run the chatbot
├── utils.py                    # Utility functions for transcript, chunking, etc.
├── requirements.txt            # (optional) Same packages as above
└── README.md                   # This file
```

---

## 📅 Environment Setup

Create a `.env` file in the root directory and add your OpenAI API key:

```
OPENAI_API_KEY=your_openai_api_key_here
```

---

## 🧑‍💻 Usage

1. Choose a YouTube video.
2. Run the script:

```python
python main.py
```

3. The chatbot will:

   * Download the transcript
   * Split and embed the text
   * Build a FAISS vector store
   * Let you ask questions!

---

## 🧠 How It Works (RAG Pipeline)

1. **Transcript Extraction**: Uses `youtube-transcript-api` to pull video text.
2. **Chunking**: Splits transcript into manageable pieces.
3. **Embedding**: Converts chunks into vector form using OpenAI or HuggingFace.
4. **FAISS Vector Store**: Stores embeddings for fast similarity search.
5. **LangChain QA**: Retrieves relevant chunks and generates answers using an LLM.

---

## 🧪 Example

```text
> Enter YouTube URL:
https://www.youtube.com/watch?v=dQw4w9WgXcQ

> Ask a question:
What is the main topic of the video?

> Bot:
The video discusses...
```

---

## 📌 Notes

* If you get a **RateLimitError**, check your OpenAI usage and consider using HuggingFace embeddings instead.
* You can extend this to support multi-video search, memory, or even use local LLMs.

---

## 📚 References

* [LangChain Documentation](https://docs.langchain.com/)
* [YouTube Transcript API](https://pypi.org/project/youtube-transcript-api/)
* [OpenAI API Reference](https://platform.openai.com/docs/)

---

## 🤝 License

MIT License. Use freely and build upon it!

---

## ✨ Future Ideas

* Add Streamlit interface
* Cache vector stores per video
* Multi-language support
