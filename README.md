# YouTube Video Caption Summarizer using Streamlit and Ollama

This project allows users to input a YouTube video URL and receive a summarized version of the video's transcript. It supports automatic and manual captions, processes them into readable text, and uses the Ollama LLM models for summarization.

## 🚀 Features

* Extracts video metadata (title, uploader, etc.)
* Downloads and parses both auto-generated and manual subtitles (captions)
* Converts `.vtt` captions into cleaned `.txt` transcripts
* Splits transcripts into chunks and summarizes them using various Ollama models
* Interactive UI built with Streamlit

## 📦 Requirements

* Python 3.7+
* [yt-dlp](https://github.com/yt-dlp/yt-dlp) (for downloading captions)
* [Ollama](https://ollama.com/) (for running LLMs locally)
* [Streamlit](https://streamlit.io/)
* Other dependencies (install via `requirements.txt`):

  ```bash
  pip install -r requirements.txt
  ```

## 🧠 Supported Ollama Models

* phi3
* llama3
* mistral
* gemma:2b
* deepseek-coder
* deepseek-r1

Make sure to pull the model before use:

```bash
ollama pull <model_name>
```

## 🛠️ How It Works

1. **Input URL**: User enters a YouTube video URL.
2. **Metadata**: The app fetches the video metadata (title, uploader).
3. **Captions**: It downloads and checks for `.vtt` subtitles (auto/manual).
4. **Clean-up**: Converts `.vtt` to clean `.txt`, removing noise.
5. **Chunking**: Splits the transcript into 4000-character chunks.
6. **Summarization**: Sends chunks to the selected Ollama model.
7. **Output**: Displays the summarized content.

## 📂 File Structure

```bash
├── app.py                  # Main Streamlit application
├── requirements.txt        # Python dependencies
├── .env                    # Environment variables (optional)
└── README.md               # Project documentation
```

## 📋 Example Usage

```bash
streamlit run app.py
```

Paste the video URL, select the model (e.g., `phi3`), and view the summary!

## ❗ Notes

* Ensure that `yt-dlp` and `ollama` commands are available in your PATH.
* Large videos may take longer due to caption parsing and LLM inference.
* Captions must be available in the language selected (default is English).

## 💡 Future Improvements

* Add support for multi-language caption summarization
* Integrate with external LLM APIs (OpenAI, Gemini, Claude)
* Save summaries as downloadable PDFs
* Add keyword extraction and topic clustering

## 🧑‍💻 Author

Developed by Atishay Jain — contributions welcome!
