# 1. Load the PDF

You start by loading a PDF using PyPDFLoader. This breaks the document into smaller chunks - usually paragraphs or sections - so they can be processed individually.

Think of this like slicing a book into digestible pages.

# 2. Create Embeddings

Each chunk is converted into a numerical vector using Azure OpenAI’s embedding model. These vectors capture the meaning of the text in a way that allows for semantic search.

It’s like turning each chunk into a fingerprint of its meaning.

# 3. Store Embeddings in Chroma

The vectors are stored in a vector database called Chroma. This lets you search for chunks that are most relevant to a user’s question.

Chroma is your searchable memory bank.

# 4. User Asks a Question

Now the user types a question — for example, “What is the main topic of the document?”

This is where the magic begins.

# 5. Retriever Finds Relevant Chunks

LangChain’s retriever takes the user’s question and searches Chroma for the most relevant chunks. It does this by embedding the question and comparing it to the stored vectors.

It’s like asking: “Which parts of the document are most similar to this question?”

# 6. Prompt Template Frames the Answer

The retrieved chunks are inserted into a prompt template. This template tells the language model: “Here’s some context. Now answer the question based on this.”

It’s like giving GPT-4 a cheat sheet before it answers.

# 7. Azure OpenAI Generates the Answer

The prompt is sent to GPT-4 via Azure OpenAI. The model reads the context and the question, then generates a natural-language answer.

Now the chatbot responds — intelligently and accurately.