# **End-to-End RAG App with Groq and Qdrant**

This project demonstrates how to build an end-to-end Retrieval-Augmented Generation (RAG) application using Groq, Qdrant, and LangChain. The application processes and retrieves information from a PDF document, and answers questions using both the document and a language model.

## **Installation**

To run the code, you need to install the required Python libraries. You can do this by running:

```bash
!pip install langchain openai tiktoken qdrant-client langchain_openai pypdf langchainhub langchain_community langchain-groq langchain-huggingface
```

## **Usage**

1. **Loading the Document:**
   - The PDF document is loaded using `PyPDFLoader`, and the content is split into chunks for efficient processing.

2. **Text Splitting:**
   - The document is split into manageable chunks using `RecursiveCharacterTextSplitter`.

3. **Embedding and Indexing:**
   - The text chunks are embedded using `HuggingFaceEmbeddings`.
   - The embeddings are then stored in a Qdrant vector store for efficient retrieval.

4. **Retrieving Relevant Documents:**
   - The Qdrant vector store is used to retrieve documents relevant to a given query.

5. **Generating Answers:**
   - The retrieved documents are passed through a prompt template to generate a concise, logical answer using the Groq language model.

## **Key Components**

- **LangChain:** A framework for developing applications with language models.
- **Qdrant:** An open-source vector search engine used for efficient similarity search.
- **Groq:** An open-source language model used to generate responses based on retrieved context.
- **HuggingFace Embeddings:** Used to convert text chunks into embeddings.
- **PyPDFLoader:** Loads and processes PDF documents.

## **Example Queries**

You can use the `rag_chain.invoke()` method to ask questions or summarize the document:

```python
rag_chain.invoke("Who was Marium?")
rag_chain.invoke("Summarize the key points of the document")
rag_chain.invoke("Who was Laila?")
```

## **Customization**

- **Change Model:** You can change the language model by modifying the `groq_llm` instantiation.
- **Adjust Retrieval:** Customize the `search_kwargs` parameter to change the number of documents retrieved.
- **Document Loader:** Replace `PyPDFLoader` with other loaders available in LangChain for different document types.

## **Acknowledgments**

Special thanks to the open-source community for providing the tools and libraries used in this project.
