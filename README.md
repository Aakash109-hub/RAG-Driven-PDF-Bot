# SmartPDF AI: A Retrieval-Augmented Generation (RAG) Application  

## Overview  

SmartPDF AI is a Retrieval-Augmented Generation (RAG) application that lets you seamlessly interact with your PDF documents. It processes uploaded files, retrieves relevant information, and generates intelligent answers to your questions. Built on the LangChain framework, SmartPDF AI ensures efficient data handling and insightful conversational capabilities by leveraging modern embedding techniques and conversational models.  

---

## Core Components of RAG  

SmartPDF AI follows the typical RAG application structure with two main workflows:  

### 1. **Indexing (Offline)**  
The indexing pipeline processes raw PDF data to create a searchable database of document chunks.  

- **Load**: Extract content from PDFs using document loaders (e.g., PyPDF2).  
- **Split**: Break the text into manageable chunks with LangChain’s `RecursiveCharacterTextSplitter`. This helps optimize search and model input handling.  
- **Store**: Use a VectorStore (FAISS) to store these chunks after embedding them with a language model.  

**Indexing Workflow Diagram**  
```
PDF File → Extract Text → Split into Chunks → Vector Embedding → Store in Vector Database
```

---

### 2. **Retrieval and Generation (Online)**  
At runtime, SmartPDF AI retrieves relevant indexed chunks based on user queries and generates context-aware answers.  

- **Retrieve**: Use a retriever to fetch relevant chunks from the vector database based on semantic similarity to the user query.  
- **Generate**: Pass the retrieved chunks along with the user query to a ChatModel/LLM (e.g., Gemini-pro) for answer generation.  

**Retrieval and Generation Workflow Diagram**  
```
User Query → Retrieve Relevant Chunks → Combine Context with Query → Generate Answer with LLM
```

---

## Features  

- **Efficient PDF Text Processing**: Extract and process text from multiple PDF files.  
- **Dynamic Question Answering**: Generate detailed and accurate answers to user queries.  
- **Seamless RAG Integration**: Combines offline indexing and online retrieval/generation workflows.  
- **User-Friendly Interface**: Built with Streamlit for an intuitive and responsive user experience.  

## Usage  

1. Open the application in your browser (local URL provided by Streamlit).  
2. **Upload PDFs**: Use the sidebar to upload multiple PDF files.  
3. **Process PDFs**: Click **Submit & Process** to create an index of the PDFs.  
4. **Ask Questions**: Input queries in the main section and receive AI-generated answers based on the content of your documents.  

---

## Folder Structure  

```
smartpdf-ai/  
|-- app.py                 # Main Streamlit application  
|-- requirements.txt       # Dependencies  
|-- .env.example           # Example API key setup  
|-- README.md              # Project documentation  
```

---

## Future Enhancements  

- **Support for Additional File Types**: Extend support to Word documents and plain text files.  
- **Multi-Language PDFs**: Enable question answering in non-English documents.  
- **Improved UI**: Add visual aids for extracted document content.  
- **Cloud Deployment**: Deploy on AWS, Azure, or GCP for wider accessibility.  

---

## Acknowledgments  

- **LangChain**: For providing tools to streamline RAG workflows.  
- **FAISS**: For efficient vector-based search and retrieval.  
- **Streamlit**: For simplifying the creation of a user-friendly UI.  

For further insights, refer to LangChain’s official [RAG Tutorial](https://python.langchain.com/docs/tutorials/rag/).  

---

## License  

This project is licensed under the MIT License. See the `LICENSE` file for more details.  

---

## Contributing  

Contributions are welcome! Please submit issues or pull requests to enhance the project.  

Enjoy seamless interaction with your documents through **SmartPDF AI**! 🚀  
