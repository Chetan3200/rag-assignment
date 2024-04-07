# Mindcase ML Assignment
I tried 3 different approach

## Standard approach
Used Langchain, Gemini-pro model and FAISS vector store. Experimented with two embedding models: "mixedbread-ai/mxbai-embed-large-v1" and "jinaai/jina-embeddings-v2-base-en". Since the queries required more information which was not available in the provided context, it failed to answer most of the questions. 

## Using ColBERTv2
ColBERT is a fast and accurate retrieval model, enabling scalable BERT-based search over large text collections. Since, the queries require more information which was not available in the provided context, it failed to answer most of the questions as well.

## Corrective RAG
Corrective Retrieval Augmented Generation (CRAG) is a method designed to enhance the robustness of language model generation by evaluating and augmenting the relevance of retrieved documents through a an evaluator and large-scale web searches, ensuring more accurate and reliable information is used in generation.
The code uses Tavily Search to obtain more information after the query is modified when the knowledge base does not contain sufficient information. 
This is the best approach among the three and is able to answer 5 out of the 9 queries asked.

## Future Scope
From experimentation, it is evident that the problem statement requires intellient use of the knowledge base as well as a search API like Tavily search. LangGraph can be used to implemented such a pipeline with the usage of conditional nodes to decide when to use retriever or search API, generate the answer and score it's relevance to the input query. However, LangGraph is still in developmental stage with lack of proper documentation. Also, it requires LLMs with the ability of function calling and example code avaiable has integration with OpenAI but not with Gemini or Mistral, so this method could not be tested. 
