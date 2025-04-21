---
layout: post
published: true
title: Building a Yoga Knowledge Assistant with Google GenAI and RAG
subtitle: Ask any question on the Yoga book of your choice
---

## Introduction

In this project, we've built a Retrieval-Augmented Generation (RAG) system that can answer questions about yoga by processing and understanding yoga-related PDF documents. The system combines Google's Generative AI capabilities with traditional document processing to create an intelligent yoga knowledge assistant.

## Goals

The primary goals of this project were to:

1. Demonstrate the practical application of Google's GenAI products in a real-world use case
2. Create a system that can understand and answer questions about yoga from authoritative sources
3. Implement a complete RAG pipeline from document processing to answer generation
4. Showcase how AI can make complex yoga knowledge more accessible

## Methods

The system implements a complete RAG pipeline with the following components:

1. **Document Processing**:
   - PDF text extraction using PyPDF2
   - OCR processing for scanned documents using Tesseract
   - Text chunking for manageable document segments

2. **Embedding Generation**:
   - Using Google's Gemini Embeddings API (`models/text-embedding-004`)
   - Creating vector representations of text chunks
   - Enabling semantic search capabilities

3. **Vector Database**:
   - Storing embeddings in ChromaDB
   - Implementing similarity-based retrieval
   - Managing document metadata and IDs

4. **Answer Generation**:
   - Using Gemini Pro (`gemini-2.0-flash`)
   - Implementing context-aware responses
   - Generating natural language answers

## Key Functions

The system is built around several key functions:

```python
def extract_text_from_pdf(pdf_path: str, chunk_size: int = 1000) -> List[str]:
    """Extracts text from PDF, using OCR if necessary, and splits into chunks."""
    # Implementation details...

def create_database(pdf_path: str, db_name: str = "yogadb") -> chromadb.Collection:
    """Creates a ChromaDB collection with embeddings from the PDF."""
    # Implementation details...

def query_database(db: chromadb.Collection, query: str, n_results: int = 3) -> List[str]:
    """Queries the database and returns relevant passages."""
    # Implementation details...

def generate_answer(query: str, passages: List[str]) -> str:
    """Generates an answer using the Gemini model."""
    # Implementation details...
```

## Datasets

The system was tested with two authoritative yoga resources:

1. **Yoga Anatomy by Leslie Kaminoff**
   - Source: [samadhiyogaashram.com](https://samadhiyogaashram.com/pdf/LeslieKaminoffYogaAnatomyzliborg-200817-225010.pdf)
   - Focus: Detailed anatomical explanations of yoga poses
   - Content: Comprehensive guide to yoga anatomy and physiology

2. **Yoga eBook from NCCIH - National Institutes of Health**
   - Source: [nccih.nih.gov](https://files.nccih.nih.gov/s3fs-public/Yoga-eBook-2020_06_FINAL_508.pdf)
   - Focus: Scientific research and health benefits of yoga
   - Content: Evidence-based information about yoga's health effects

## Example Queries and Answers

Here are some example interactions with the system:

### Example 1: Anatomy Question
**Query:** "What are the key muscles involved in downward facing dog pose?"

**Answer:**
"The downward facing dog pose primarily engages several muscle groups. The hamstrings and gastrocnemius (calf muscles) are actively stretched, while the deltoids and trapezius in the shoulders work to support the upper body. The core muscles, including the rectus abdominis and obliques, help maintain stability. The pose also strengthens the arms and shoulders while providing a gentle stretch for the spine."

### Example 2: Health Benefits
**Query:** "What are the proven health benefits of regular yoga practice?"

**Answer:**
"Research has shown that regular yoga practice offers numerous health benefits. It can improve flexibility, strength, and balance. Studies indicate that yoga may help reduce stress, anxiety, and symptoms of depression. It has also been shown to improve sleep quality and may help manage chronic pain conditions. Additionally, yoga practice has been associated with improved cardiovascular health and better management of conditions like hypertension and type 2 diabetes."

### Example 3: Technical Question
**Query:** "How does yoga affect the nervous system?"

**Answer:**
"Yoga has a profound impact on the nervous system through several mechanisms. The practice activates the parasympathetic nervous system, promoting relaxation and reducing stress responses. Specific breathing techniques (pranayama) can directly influence the autonomic nervous system. The combination of physical postures, breathing exercises, and meditation helps regulate the hypothalamic-pituitary-adrenal axis, leading to reduced cortisol levels and improved stress management."

## Conclusion

This project demonstrates how modern AI technologies can be combined to create intelligent systems that make complex information more accessible. By leveraging Google's GenAI products and implementing a RAG architecture, we've created a system that can understand and explain yoga concepts in a natural, conversational way.

The system's ability to process and understand authoritative yoga resources makes it a valuable tool for both yoga practitioners and instructors. Future improvements could include:
- Support for more document types
- Enhanced context awareness
- Integration with additional yoga resources
- More sophisticated answer generation

## Technical Requirements

- Python 3.7+
- Google API key for Gemini
- Required Python packages:
  - google-generativeai==1.7.0
  - chromadb==0.6.3
  - PyPDF2==3.0.1
  - pdf2image==1.17.0
  - pytesseract==0.3.10
  - Pillow==10.2.0

## Acknowledgments

Special thanks to:
- [Leslie Kaminoff for the comprehensive yoga anatomy resource](https://samadhiyogaashram.com/pdf/LeslieKaminoffYogaAnatomyzliborg-200817-225010.pdf)
- [NCCIH for the evidence-based yoga research](https://files.nccih.nih.gov/s3fs-public/Yoga-eBook-2020_06_FINAL_508.pdf)
- Google for providing the GenAI tools and Kaggle that made this project possible 
