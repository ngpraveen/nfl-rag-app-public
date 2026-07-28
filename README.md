## RAG Application Demo

A RAG-base chat application is created for a toy problem, but with real production features. 
The application is hosted [here](http://www.praveenng.com:5001/).

Features include:
- ✅ Multitenancy ([details](#multitenancy))
- ✅ Short term (in-session) memory
- ✅ Responsible AI and AI Governance ([complete list](#responsible-ai-and-ai-governance)) 
- 🔲 Observability and monitoring
- 🔲 Automated pipeline 
- 🔲 Hybrid search
- 🔲 Logging
- 🔲 Rate-limiting

Some of the features not included are:
- ❌ Authentication
- ❌ Autoscaling

The knowledge base for this application is formed using Wikipedia articles of the 32 NFL teams, downloaded as markdown files.
For your reference, they are included in the [input_data](https://github.com/ngpraveen/nfl-rag-app-public/tree/master/input_data) directory. 

The RAG was built using:
- [LlamaIndex](https://www.llamaindex.ai/) for workflow
- [Pinecone](https://www.pinecone.io/) as vector database
- [Amazon Titan Text Embeddings V2](https://docs.aws.amazon.com/bedrock/latest/userguide/titan-embedding-models.html) for embedding
- [Nova 2 Lite](https://aws.amazon.com/nova/models/) as language model 
- [Streamlit](https://streamlit.io/) for building the frontend 

### Multitenancy
Multitenancy refers to the ability of an application to serve multiple independent customers (tenant), 
providing isolation of their data. It is natively added to this app by 
storing each tenant's data in a separate namespace within Pinecode vectorstore. 
This not only allows a tenant-based access to the data when they use it, 
but also isolates each tenant's data. 

During the embedding (input) workflow metadata is added to the data and 
it is later used to store vectors within the proper namespace. 


### Responsible AI and AI Governance

The following policies and contorls are added to ensure responbile and safe use of AI. 
 - Harmful content including hate, insults, sexual, violance
 - Denied topics (investment advice in this demo)
 - Profanity
 - Custom words (for the demo purpose, **Mr. Irrelevant**, **O. J. Simpson**, **Gillette** (stadium) and **RCA Dome** are not allowed)
 - Personally identifiable information (PII) such as **phone number**, **email**, **username**, **password**, **drivers id**, **credit card number** and **bank account number** will be masked. 


