
# Multimodal RAG Search  
**Multimodal Retrieval-Augmented Generation for Image & Text Documents**

## 📋 Overview

This project implements a **multimodal Retrieval-Augmented Generation (RAG) pipeline** that can answer questions from documents containing **both text and images**.

Unlike traditional text-only systems, this project:
- ✅ Extracts **text and images** from PDFs
- ✅ Converts them into **multimodal embeddings**
- ✅ Retrieves the most relevant content using vector similarity
- ✅ Generates grounded answers using a **vision-language model (LLaVA)**

The system enables **image-aware document question answering**, bridging the gap between textual and visual information.

---

## 🎯 Problem Statement

Traditional document QA systems:
- ❌ Work only on text
- ❌ Ignore images, charts, and diagrams
- ❌ Fail when key information is visual

**Example Query:**
> "What suspicious activity is shown in the image on page 2?"

A text-only system cannot answer this question effectively.

### 💡 Solution

This project addresses these limitations by:
- Using **multimodal embeddings (CLIP)** to understand both text and images
- Retrieving relevant **text and images** based on semantic similarity
- Leveraging **LLaVA** for image-grounded reasoning and answer generation

---

## 🏗️ System Architecture
```
PDF Document
     ↓
Text & Image Extraction (PyMuPDF)
     ↓
CLIP Embeddings (Text + Image)
     ↓
FAISS Vector Search
     ↓
Relevant Text + Image Retrieval
     ↓
LLaVA (Multimodal Reasoning)
     ↓
Final Answer
```

---

## ✨ Key Features

- 🔍 **Multimodal document understanding** - Process both text and visual content
- 🖼️ **Image-aware question answering** - Answer queries about visual elements
- 📊 **Retrieval-grounded generation** - Responses backed by actual document content
- 🌐 **Open-source model pipeline** - Built entirely with open-source models
- 🧩 **Modular architecture** - Easy to customize and extend

---

## 🛠️ Tech Stack

### Core Technologies
- **Python** - Primary programming language
- **Jupyter Notebook** - Interactive development environment

### Libraries & Models

| Component | Technology |
|-----------|------------|
| Document parsing | PyMuPDF (fitz) |
| Multimodal embeddings | CLIP (ViT-B/32) |
| Vector search | FAISS |
| Vision-language model | LLaVA |
| Image processing | PIL |
| ML framework | PyTorch |
| Numerical operations | NumPy |

---

## 🔄 How It Works (Step-by-Step)

### 1️⃣ Document Processing
Extract text and images from PDFs using PyMuPDF, preserving the relationship between textual and visual content.

### 2️⃣ Multimodal Embedding
Convert both text and images into embeddings using CLIP, ensuring they exist in the same vector space for unified retrieval.

### 3️⃣ Vector Retrieval
Store embeddings in FAISS index and retrieve the most relevant text passages and images for a given query.

### 4️⃣ Answer Generation
Pass retrieved context (text) and the raw image to LLaVA to generate grounded, contextually accurate answers.

---

## 📊 Evaluation

- Achieved **82% Recall@5** on manually evaluated queries
- Demonstrated significant performance improvement for image-dependent questions
- Successfully handles multi-modal reasoning tasks

---

## 🚀 Installation

### 1. Clone the repository
```bash
git clone https://github.com/deepsaigilla/multimodal-rag-search.git
cd multimodal-rag-search
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. (Optional) Set up virtual environment
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

---

## 💻 Usage

### Run the notebook
```bash
jupyter notebook multimodal_rag.ipynb
```

### Example Query
```python
query = "What activity is shown in the image on page 3?"
```

**The system will:**
1. Retrieve relevant text and images from the document
2. Send them to LLaVA for multimodal reasoning
3. Generate a grounded answer based on both visual and textual context

---

## 📁 Project Structure
```
multimodal-rag-search/
│
├── multimodal_rag.ipynb      # Main notebook with implementation
├── data/                      # Data directory
│   └── sample_pdfs/           # Sample PDF documents
├── images/                    # Extracted images and assets
├── requirements.txt           # Python dependencies
├── README.md                  # Project documentation
└── LICENSE                    # License file
```

---

## 🌍 Real-World Use Cases

- 🔐 **Surveillance report analysis** - Extract insights from security documents
- 📚 **Research paper understanding** - Comprehend academic papers with figures
- 💼 **Financial and business reports** - Analyze reports containing charts and graphs
- 🏥 **Medical document QA** - Query medical records with diagnostic images
- 🏢 **Enterprise knowledge systems** - Build intelligent document search systems

---

## 👨‍💻 Author

**Deep Sai Gilla**

- 🐙 GitHub: [@deepsaigilla](https://github.com/deepsaigilla)
- 💼 LinkedIn: [deepsaigilla](https://linkedin.com/in/deepsaigilla)

---

## 🙏 Acknowledgments

- OpenAI CLIP for multimodal embeddings
- LLaVA for the vision-language model
- FAISS library for efficient vector search
- PyMuPDF for PDF processing capabilities

---

## 📧 Contact

For questions or feedback, please open an issue or reach out via LinkedIn.

---

<p align="center">Made by Deep Sai Gilla</p>
