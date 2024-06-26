# Key Terms
- Retrieval augmented generation (RAG): A technique in AI where a LLM accesses new or recent data outside its training set to provide better answers and improved results.
- Vector database: A search engine or database that stores vectorized documents, enabling more accurate information retrieval for AI models.
- Embeddings: Representations of text data as vectors in a high-dimensional space, allowing similarity comparisons between different pieces of text.
- Azure AI Search: Microsoft's cloud-based search service that offers retrieval augmentation capabilities for LLMs.
- Comma separated value (CSV)
- Pandas library
- Qdrant: Software used for creating an in-memory vector database search, enabling efficient text retrieval and embedding storage.
- Sentence transformers: A tool to encode sentences into numerical representations (embeddings) that can be compared using cosine similarity or other distance metrics.
- Cosine distance: A measure of similarity between two non-zero vectors in a multi-dimensional space, often used in text analysis and information retrieval.

# Mangage Data for embeddings
- import the data into panda df
- transform the df into dict ```df.to_dict('records')```

https://github.com/alfredodeza/learn-retrieval-augmented-generation/blob/main/examples/1-managing-data/example.ipynb

# Verifying embeddings and search
- Some software needed in order to have this vector db search
- import the needed libraries

```
from qdrant_client import models, QdrantClient
from sentence_transformers import SentenceTransformer
```
- The 'SentenceTransformer' will give us the ability to do the encoding.
- The encoding is needed and we'll use the 'all-MiniLM-L6-V2', and this will automatically downlaod the machine learning model locally so that we can do the tokenization to cretae the embeddings so that it goes into the vector db.
- The 'QdrantClient' is an instance of the db
- ```QdrantClient('memory')``` We're going to be able to use in memory database. We don't need to create a file based db or a netword based db.
- Create collection: The collections will be able to reside within the db and when passing ceratin parameters.
  + THe distance is to basically do a comparison and find what phrases frim what I'm searching will be closer to that data, the information that I'm going to be storing.
- Vectorize: Upload everything into our vector db.
- Search

https://github.com/alfredodeza/learn-retrieval-augmented-generation/blob/76fa13c3ae059fb5f8a8e45450fdd3cdf9a3c8e9/examples/2-embeddings/embeddings.ipynb

# Using RAG with an LLM

https://github.com/alfredodeza/learn-retrieval-augmented-generation/blob/76fa13c3ae059fb5f8a8e45450fdd3cdf9a3c8e9/examples/3-applied-rag/embeddings.ipynb

# Create and use Embeddings
https://hub.labs.coursera.org/connect/sharedtowtmdqw?forceRefresh=false&path=%2Fnotebooks%2Flearn-retrieval-augmented-generation%2Fexamples%2F2-embeddings%2Fcoursera-lab.ipynb&isLabVersioning=file-prep

# External lab
The examples for the Applied Rag notebook requires either an OpenAI API endpoint with a key or using a local LLM with Llamafile
Recommend: using the Phi-2 model, which is about 2GB in size. You can download the model from the Llamafile repository and run it in your system:
![螢幕擷取畫面 (710)](https://github.com/FionaYuY/Introduction-to-RAG/assets/151610467/f4337096-b6c6-42c5-b18f-f6011cda549a)
![螢幕擷取畫面 (711)](https://github.com/FionaYuY/Introduction-to-RAG/assets/151610467/c652ed5f-3818-4b08-801a-47c7c70dddcc)
requirements.txt : https://github.com/alfredodeza/learn-retrieval-augmented-generation/blob/76fa13c3ae059fb5f8a8e45450fdd3cdf9a3c8e9/requirements.txt

# Quiz
- Why is converting data to a dictionary format useful when creating a vector database for retrieval augmented generation?
  + Converting to a dictionary maps fields like "text" to vectors needed for retrieval.
