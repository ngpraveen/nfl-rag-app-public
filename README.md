## RAG Application Demo

A RAG application is created for a toy problem, but with real production features. 
The application is hosted [here](http://www.praveenng.com:5001/).

Features include:
- ✅ Multi-tenancy 
- ✅ Short term (in-session) memory
- ✅ Responsible AI and AI Governance ([complete list](#responsible-ai-and-ai-governance)) 
- 🔲 Automated pipeline 
- 🔲 Hybrid search
- 🔲 Logging
- 🔲 Rate-limiting

The knowledge base for this application is formed using Wikipedia articles of the 32 NFL teams, downloaded as markdown files.

### Responsible AI and AI Governance

The following policies and contorls are added to ensure responbile and safe use of AI. 
 - Harmful content including hate, insults, sexual, violance
 - Denied topics (investment advice in this demo)
 - Profanity
 - Custom words (for the demo purpose, Mr. Irrelevant, O. J. Simpson, Gillette (stadium) and RCA Dome are not allowed)
 - Personally identifiable information (PII) such as phone number, email, username, password, drivers id, credit card numbers and bank account number will be masked. 


