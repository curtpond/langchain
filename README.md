# langchain
Trying out different GenAI solutions using LangChain, Pinecone, etc.

### Set Up
* Follow the steps here [gpt4-pdf-chatbot-langchain](https://github.com/mayooear/gpt4-pdf-chatbot-langchain). 
* Need to install NODEJS/NPM/Yarn. Command for NPM global install: *sudo npm i -g npm*. 
* Add OpenAI environment variables (OPENAI API KEY). [Tips on adding environment variables](https://help.openai.com/en/articles/5112595-best-practices-for-api-key-safety)
* Add Pinecone environment variables (PINECONE_API_KEY, PINECONE_ENVIRONMENT, PINECONE_INDEX_NAME)

### Ingestion Part 1
* Convert PDF Doc(s) to text.
* Split the text into chunks using LangChain.
* Each chunk is a certain number of characters.
* Create embeddings with chunks (number representation of text).
* Store embeddings in a Pinecone vector store.

### User Query Part 2
* User asks a question (combine with chat history).
* Send to LLM (GPT 3.5).
* Create stand alone question.
* Convert the question text to embeddings.
* Compare the embeddings to relevant documents in vector store (embedded chunks).
* Figure out which chunks are most similar to the question asked.
* Combine stand alone question with relevant docs to provide context.
* Send to LLM (GPT 3.5) and get an answer.