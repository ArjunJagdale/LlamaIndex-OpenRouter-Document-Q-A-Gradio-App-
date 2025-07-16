# 🧠 LlamaIndex + OpenRouter Document Q&A (Gradio App)
This project is a simple but powerful **document question-answering app**

## You can access the demo here
[LlamaIndex Doc reader](https://huggingface.co/spaces/ajnx014/LlamaIndex_Document_Reader)


## Demo video - 

https://github.com/user-attachments/assets/2b846d45-732f-41df-92dd-aff0497fef8c

---

This project is a simple but powerful **document question-answering app** built using:

- [LlamaIndex](https://github.com/jerryjliu/llama_index) – for document parsing, embedding, and retrieval
- [Gradio](https://gradio.app) – for the web-based UI
- [OpenRouter](https://openrouter.ai) – as the backend LLM provider (e.g. Mistral)

---

## 🚀 What does it do?

> Upload a `.txt` document → It indexes the content using LlamaIndex → You ask natural language questions → It returns intelligent answers powered by Mistral via OpenRouter.

---

## 🧰 How it works

1. **File Upload**:
   - You upload a `.txt` or `.pdf` document.
   - The app saves the file locally in a temporary `data/` directory.

2. **Indexing (LlamaIndex)**:
   - Uses `SimpleDirectoryReader` to read the uploaded file.
   - Embeds the document using `sentence-transformers/all-MiniLM-L6-v2`.
   - Builds a `VectorStoreIndex` using LlamaIndex.

3. **Querying**:
   - Uses `OpenRouter` with Mistral (`mistralai/mistral-small-3.2-24b-instruct:free`) to process your natural language questions.
   - The `query_engine` from LlamaIndex retrieves relevant content and sends the prompt to the LLM.

---

## 🧪 Technologies Used

| Tool              | Purpose                            |
|-------------------|------------------------------------|
| LlamaIndex        | Document ingestion and retrieval   |
| Gradio            | Interactive web UI                 |
| OpenRouter        | Language model provider (LLM API)  |
| HuggingFace Datasets | Optional data handling (future)  |

---

## 🛠️ How to Run (Locally or on HF Spaces)

### 1. Setup Requirements

Install dependencies:
```bash
pip install -r requirements.txt
````

Or manually:

```bash
pip install gradio llama-index llama-index-embeddings-huggingface llama-index-llms-openrouter llama-index-readers-file
```

### 2. Add API Key

If you're using **Hugging Face Spaces**, go to **Settings > Secrets** and add:

```
OPENROUTER_API_KEY = sk-or-xxxxxxxxxxxxxxxxxxxx
```

If you're running locally, set the environment variable:

```bash
export OPENROUTER_API_KEY=sk-or-xxxxxxxxxxxxxxxxxxxx
```

### 3. Run the App

```bash
python app.py
```

---

## 📁 Example `.txt` Document

You can upload any plain `.txt` file. Example content:

```
John completed the AWS Certified Solutions Architect course in 2023.
This certification focuses on designing scalable cloud infrastructure.
```

> Then ask: **"What certification is mentioned?"** ✅

---

## ✅ Future Improvements

* Support for PDF and DOCX using LlamaIndex readers
* Multi-file upload
* Long document chunking and section tagging
* Diagram generation using extracted entities (TechGraph / SpecSketch style)

---

## ✨ Credits

* Built using [LlamaIndex](https://github.com/jerryjliu/llama_index)
* UI with [Gradio](https://gradio.app)
* LLM via [OpenRouter](https://openrouter.ai)
