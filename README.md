# 🤖 Groq-Powered PDF Chatbot with Gradio UI

This is a Google Colab-based document chatbot powered by **Groq’s LLaMA 3 model**, built with **LangChain**, **ChromaDB**, and a clean **Gradio interface**. You can upload any PDF and interact with it intelligently — even view diagrams, extract metadata.

---

## 🚀 Live Notebook

👉 **[Open in Google Colab](https://colab.research.google.com/github/Danwhoosh/NovelOffice_Groq_ChatBot/blob/main/Novel_Office.ipynb)**

---

## 📁 Project Structure

```bash
Groq_PDF_Chatbot/
├── Groq_PDF_Chatbot.ipynb         # Full working Colab notebook
├── README.md                      # This file
└── docs/
    └── FluidMechanics.pdf         # Sample document used for testing
```
----

## 🛠️ Tools & Libraries Used
| Tool Library            | Purpose                                        | 
|-------------------------|------------------------------------------------|
| Lang Chain              | Load a document for processing                 |
| Groq AI                 | Query the LLM about the document               |
| Gradio                  | Save chat history                              |
| HuggingFace Embeddings  |Converts text into embeddings for vector search |
| ChromaDB                |Stores and retrieves vectorized PDF content     |
| pdf2image               |Converts xource PDF pages into images           |
| PyPDf2                  |Extracts PDF metadata (title, author)           |
| Google Colab            |Cloud-based notebook runtime                    |

----

## ⚙️ Setup Instructions
Paste this into the first cell of the Colab notebook to install all dependencies:

!pip install gradio langchain langchain-community langchain-groq chromadb pdf2image PyPDF2 sentence-transformers
!apt install poppler-utils -y

----

##(NOTE: Might not be needed since ipynb file already has all code available just run from start and the last code cell being the main interface)

----

## 🧠 Architecture Overview

                 ┌────────────────────┐
                 │    PDF Upload      │
                 └─────────┬──────────┘
                           ▼
                   PyPDFLoader + Splitter
                           ▼
              HuggingFace Embeddings (MiniLM-L6-v2)
                           ▼
              ┌──── ChromaDB Vector Store ────┐
              ▼                               ▼
     Metadata Extraction               Diagram Rendering
              ▼                               ▼
           LangChain                     pdf2image + PIL
           (Groq LLM)
              ▼
    Retrieval-Augmented Chat
              ▼
    Gradio Frontend UI (Colab-based)

----

## ✨ Features

✅ Upload any PDF

✅ Automatically extract title and author

✅ Ask natural language questions about the PDF

✅ "Explain Like I'm 5" mode toggle

✅ View source diagrams extracted from cited PDF pages

✅ Chat history display

✅ Copy-to-clipboard for answers

✅ Clear chat history button

✅ (Optional) Export entire chat session

✅ Google Colab–friendly interface

----

## 📥 Sample Document

The folder Documents/FluidMechanics.pdf contains a sample file. You can replace it with any other PDF of your choice.

----

## 🧪 Example Use Cases
Reading engineering textbooks and viewing formulas/figures

Legal document review with AI Q&A

Research paper summarization + citation image preview

ELI5 explanations for complex topics

----

## 📌 Notes

Groq API key is required. You can get yours at https://console.groq.com

Model used: llama3-70b-8192 (you can change this in the notebook)

PDF metadata relies on what's embedded in the file; not all PDFs contain this info.

----

### Built by Dhanush Rajashekar using:

OpenAI's LangChain

Groq LLMs

Gradio

Google Colab






