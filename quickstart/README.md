# Assistant quickstart

This n8n workflow template lets you chat with files downloaded via HTTP (.docx, .json, .md, .txt, .pdf) using OpenAI and Pinecone Assistant. It retrieves relevant context from your files in real time so you can get accurate, context-aware answers about your proprietary data—without the need to train your own LLM.

### What is Pinecone Assistant?

[Pinecone Assistant](https://docs.pinecone.io/guides/assistant/overview) allows you to build production-grade chat and agent-based applications quickly. It abstracts the complexities of implementing retrieval-augmented (RAG) systems by managing the chunking, embedding, storage, query planning, vector search, model orchestration, reranking for you.

## Try it out

### Prerequisites

* A [Pinecone account](https://app.pinecone.io/) and [API key](https://app.pinecone.io/organizations/-/projects/-/keys)
* An [Open AI account](https://auth.openai.com/create-account) and [API key](https://platform.openai.com/settings/organization/api-keys)
### Setup

1. Create a Pinecone Assistant in the Pinecone Console [here](https://app.pinecone.io/organizations/-/projects/-/assistant/-/files) 
	1. Name your Assistant `n8n-assistant` and create it in the `United States` region
	2. If you use a different name or region, update the related nodes to reflect these changes
	3. No need to configure a Chat model or Assistant instructions
2. Setup Pinecone API key credential in n8n
	1. In the Upload file to assistant node -> PineconeApi section, select Create new credential
	2. Paste in your Pinecone API key in the API Key field
3. Setup Pinecone MCP Bearer auth credential in n8n
	1. In the Pinecone Assistant node -> Credential for Bearer Auth section, select Create new credential
	2. Set the Bearer Token field to your Pinecone API key used in the previous step
4. Setup the Open AI credential in n8n
	1. In the OpenAI Chat Model node -> Credential to connect with, select Create new credential
	2. Set the API Key field to your OpenAI API key
5. Activate the workflow or test it with a manual execution to ingest the documents
6. Chat with your docs!

### Ideas for customizing this workflow

- Change the urls in Set file urls node to use your own files
- Customize the System Message on the AI Agent node to your use case to indicate what kind of knowledge is stored in Pinecone Assistant
- Make the [chat node publicly available](https://docs.n8n.io/integrations/builtin/core-nodes/n8n-nodes-langchain.chattrigger/#make-chat-publicly-available) or [create your own chat interface](https://docs.n8n.io/integrations/builtin/core-nodes/n8n-nodes-langchain.chattrigger/#mode) that calls the chat webhook URL

### Need help?

You can find help by asking in the [Pinecone Discord community](https://discord.gg/tJ8V62S3sH), asking on the [Pinecone Forum](https://community.pinecone.io/), or [filing an issue](https://github.com/pinecone-io/n8n-templates/issues/new/choose) on this repo.